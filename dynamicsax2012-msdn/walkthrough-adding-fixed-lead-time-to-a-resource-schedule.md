---
title: 'Walkthrough: Adding Fixed Lead Time to a Resource Schedule'
TOCTitle: 'Walkthrough: Adding Fixed Lead Time to a Resource Schedule'
ms:assetid: a0449f5f-521d-494b-ac98-1cd43dee8fc9
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh830900(v=AX.60)
ms:contentKeyID: 45260820
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Walkthrough: Adding Fixed Lead Time to a Resource Schedule 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

You can customize the resource scheduling code so that for a given operation, a fixed lead time is used as a lower bound for the number of days an operation can span. Fixed lead time is the amount of time required to complete an operation. In this walkthrough, we will demonstrate the following scenario

You have operations: 10 and 20.

Operation 10 has 2 jobs: Setup and Process. Each job requires six hours of capacity and loads the resource 100 percent.

Operation 20 has only one job: Setup.

To simplify, both operations require the resource R which has a 24-hour calendar (open always).

The fixed lead time applied is one day.

The scheduling for this is scheduled forward from a user-supplied date. Forward scheduling plans the tasks from the date resources become available to determine the shipping date or the due date. Since fixed lead time is not supported out of the box by Microsoft Dynamics AX, you add a temporary job for each operation. The temporary job guarantees a minimum of time expires between the end of the first operation and the start of the second and will not be saved to the database.

![Operations Scheduling Using Fixed Lead Time](images/Hh830900.OperationsSchedulingUsingFixedLeadTime(en-us,AX.60).png "Operations Scheduling Using Fixed Lead Time")

If operation 10 would start in the middle of the day, the fixed lead time should still enforce that operation 20 starts at the start of the next day.

![Operation scheduled in middle of the day](images/Hh830900.ResourceSchedulingOperationScheduledinMiddleofDay(en-us,AX.60).png "Operation scheduled in middle of the day")

You also set an option to toggle whether the fixed lead time uses information from a calendar definition.

![Implement an option to use a calendar definition](images/Hh830900.ResourceSchedulingUsingACalendarOption(en-us,AX.60).png "Implement an option to use a calendar definition")

You assign a calendar to the temporary job that is used to enforce the lead time.

![Add a temporary job to enforce the lead time](images/Hh830900.ResourceSchedulingAddingTemporaryJob(en-us,AX.60).png "Add a temporary job to enforce the lead time")

## Prerequisites

  - A Microsoft Dynamics AX installation with a developer license.

  - Visual Studio 2008 or 2010 that includes Visual C\#.

## Implementing the C\# engine constraint

The constraint is code you write to ensure there is a minimal time gap between the two operations. It will return false if no time gap exists. To create a new constraint, you inherit from the abstract class SchedulingConstraint. For more information on the Resource Scheduling class structure, see [Microsoft.Dynamics.AX.Planning.JobScheduling Namespace](http://msdn.microsoft.com/en-us/library/microsoft.dynamics.ax.planning.jobscheduling.aspx). Several methods must be implemented in order to have a functional constraint. The following table lists the methods you use in this scenario.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Method</p></th>
<th><p>Definition</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Propagate</p></td>
<td><p>Ensures that the actual constraint is enforced. If it is violated, propagate must return false. In this example, the constraint is the code that enforces the fixed lead time gap between the two operations.</p></td>
</tr>
<tr class="even">
<td><p>AddToJobActivationList</p></td>
<td><p>Specifies at which point during the propagation the constraint becomes active. Each constraint must add itself to the activation list of at least one job. In this example, you call AddToLastJobInSequence(StartJob, EndJob, this); where StartJob is the start of the operation job and EndJob is the temporary job implemented in the X++ pre-processing code.</p></td>
</tr>
<tr class="odd">
<td><p>JobList</p></td>
<td><p>Property that exposes a list of jobs that are affected by the constraint. This allows the engine to determine when the constraint must be re-propagated.</p></td>
</tr>
</tbody>
</table>


## Next Steps

1.  Open Visual Studio.

2.  Select File-\>New-\>Project.

3.  Select Visual C\# as the project type.

4.  Select Class Library as the template

5.  Name it FixedLeadTimeEngine. Change the location of the solution if desired. Click OK.

6.  In Solution Explorer, rename Class1.cs to FixedLeadTimeEngine.cs.

7.  Add a reference in the project to Microsoft.Dynamics.AX.Planning.JobScheduling.dll and Microsoft.Dynamics.Ax.Planning.JobSchedulingInterop.dll. They can be located in the bin folder of the Microsoft Dynamics AX client or server installation.

8.  Copy or paste the following code, replacing the existing code.

<!-- end list -->

    //-----------------------------------------------------------------------
    // <copyright file="FixedLeadTimeEngine.cs" company="Microsoft Corporation">
    //     Copyright (c) Microsoft Corporation. All rights reserved.
    // </copyright>
    //-----------------------------------------------------------------------
    
    using System.Threading;
    
    namespace FixedLeadTimeEngine
    {
        using System;
        using System.Collections.Generic;
        using System.Linq;
        using System.Text;
        using Microsoft.Dynamics.AX.Planning.JobScheduling;
    
        using JobId = System.Int64;
        using Seconds = System.Int64;
    
        /// <summary>
        /// The FixedLeadTimeEngine class extends the scheduling engine with a method that adds a fixed lead time constraint.
        /// </summary>
        public class FixedLeadTimeEngine : JobSchedulingEngine
        {
            /// <summary>
            /// Initializes a new instance of the FixedLeadTimeEngine class.
            /// </summary>
            public FixedLeadTimeEngine()
            {
            }
    
            /// <summary>
            /// Initializes a new instance of the FixedLeadTimeEngine class.
            /// </summary>
            /// <param name="engineDataProvider">An engine data provider instance</param>
            /// <param name="dataWriter">IScheduledDataWriter instance that can be used for saving scheduled jobs data.</param>
            public FixedLeadTimeEngine(IEngineDataProvider engineDataProvider, IScheduledDataWriter dataWriter) :
                base(engineDataProvider, dataWriter)
            {
                Logger.Sinks.Add(new CrimsonLoggingSink());
    
                Logger.Sinks.Add(new FileLoggingSink() { LogPath = Logger.LogPath });
            }
    
            /// <summary>
            /// Adds a fixed lead time constraint that forces the time gap between the start of a job and the end of another job to at least a certain number of seconds.
            /// </summary>
            /// <param name="startJobId">The start job ID</param>
            /// <param name="endJobId">The end job ID</param>
            /// <param name="fixedLeadTime">The fixed lead time in days</param>
            /// <param name="useWorkingTimes">Should the constraint use working times?</param>
            public void AddConstraintFixedLeadTime(JobId startJobId, JobId endJobId, int fixedLeadTime, bool useWorkingTimes)
            {
                // validate that the 2 jobs exist in the scheduling engine pool
                this.CheckJobIdDoesExist(startJobId);
                this.CheckJobIdDoesExist(endJobId);
    
                // validate that the fixed lead time is positive
                if (fixedLeadTime < 0)
                {
                    throw new ArgumentException("fixedLeadTime");
                }
    
                // add the custom constraint to the engine
                this.AddSchedulingConstraint(new FixedLeadTimeConstraint(JobSchedulingData.Jobs[startJobId], JobSchedulingData.Jobs[endJobId], fixedLeadTime, useWorkingTimes));
            }
        }
    }

1.  Add a new class to your Visual Studio project and name it FixedLeadTimeConstraint.cs.

2.  Add a reference in the project to Microsoft.Dynamics.AX.Planning.JobScheduling.dll and the Microsoft.Dynamics.Ax.Planning.JobSchedulingInterop.dll. They can be located in the bin folder of the Microsoft Dynamics AX client or server installation.

3.  Copy or paste the following code, replacing the existing code:

<!-- end list -->

``` 
//-----------------------------------------------------------------------
// <copyright file="FixedLeadTimeConstraint.cs" company="Microsoft Corporation">
//     Copyright (c) Microsoft Corporation. All rights reserved.
// </copyright>
//-----------------------------------------------------------------------

namespace FixedLeadTimeEngine
{
    using System;
    using System.Collections.Generic;
    using System.Globalization;
    using System.Linq;
    using System.Text;
    using Microsoft.Dynamics.AX.Planning.JobScheduling;

    using Seconds = System.Int64;

    /// <summary>
    /// The class FixedLeadTimeConstraint implements a simple fixed lead time algorithm.
    /// </summary>
    internal class FixedLeadTimeConstraint : SchedulingConstraint
    {
        protected Job StartJob { get; private set; }
        protected Job EndJob { get; private set; }
        protected int FixedLeadTime { get; private set; }
        protected bool UseWorkingTimes { get; private set; }

        /// <summary>
        /// Initializes a new instance of the FixedLeadTimeConstraint class.
        /// </summary>
        /// <param name="startJob">The reference job</param>
        /// <param name="endJob">The second date endpoint</param>
        /// <param name="fixedLeadTime">Fixed lead time in days</param>
        /// <param name="useWorkingTimes">Is the constraint using working times?</param>
        internal FixedLeadTimeConstraint(Job startJob, Job endJob, int fixedLeadTime, bool useWorkingTimes)
        {
            StartJob = startJob;
            EndJob = endJob;
            FixedLeadTime = fixedLeadTime;
            UseWorkingTimes = useWorkingTimes;
        }

        /// <summary>
        /// Replay the constraint using the supplied scheduling engine.
        /// </summary>
        /// <param name="engine">Engine to replay the constraint on.</param>
        public override void Replay(ISchedulingEngine engine)
        {
            throw new NotImplementedException();
        }

        /// <summary>
        /// Adds the constraint instance to the constraint activation list of a job
        /// </summary>
        protected override void AddToJobActivationList()
        {
            AddToLastJobInSequence(StartJob, EndJob, this);
        }

        /// <summary>
        /// Adds the constraint instance to all variable wakeup lists that should trigger a new propagation
        /// of the constraint
        /// </summary>
        /// <param name="variables">The updated variables are added to the supplied hashset</param>
        protected override void UpdateVariableWakeupLists(HashSet<SchedulingVariable> variables)
        {
            StartJob.JobVariables.StartTimeVar.AddConstraintToWakeupList(this);
            EndJob.JobVariables.StartTimeVar.AddConstraintToWakeupList(this);
            variables.Add(StartJob.JobVariables.StartTimeVar);
            variables.Add(EndJob.JobVariables.StartTimeVar);
        }

        /// <summary>
        /// Gets the jobs affected by the constraint
        /// </summary>
        protected override ICollection<Job> JobList
        {
            get
            {
                return new List<Job> { StartJob, EndJob };
            }
        }

        /// <summary>
        ///  Propagates a constraint where the firstDate less or equal to secondDate + delayInSeconds
        /// </summary>
        /// <param name="firstDate">The first date</param>
        /// <param name="secondDate">The second date</param>
        /// <param name="delayInDays">Delay in days between the first and the second date</param>
        /// <returns>true on sucess otherwise false</returns>
        public static bool PropagateLessOrEqual(DateTimeVariable firstDate, DateTimeVariable secondDate, double delayInDays, bool useWorkingTimes)
        {
            bool result = true;

            if (firstDate == null)
            {
                throw new ArgumentNullException("firstDate");
            }

            if (secondDate == null)
            {
                throw new ArgumentNullException("secondDate");
            }

            // firstDate <= secondDate.Date.AddDays(delayInDays)

            // guard against underflow
            double availableDays = (secondDate.UpperBound.Date - DateTime.MinValue).TotalDays;

            // Perform Upper bound restriction
            if (availableDays >= delayInDays)
            {
                result = result && firstDate.RestrictUpperBound(secondDate.UpperBound.Date.AddDays(-delayInDays));
            }

            // guard against overflow
            availableDays = (DateTime.MaxValue - firstDate.LowerBound.Date).TotalDays;

            // Perform Lower bound restriction
            if (availableDays >= delayInDays)
            {
                result = result && secondDate.RestrictLowerBound(firstDate.LowerBound.Date.AddDays(delayInDays));
            }

            return result;
        }

        /// <summary>
        /// Walks through the working times starting at a given date
        /// </summary>
        /// <param name="engine">The scheduling engine instance</param>
        /// <param name="startDate">The enumeration start date</param>
        /// <param name="forward">Direction: true = forward; false = backward</param>
        /// <returns>A DateTime object with the date representing the startDate +/- the fixed lead time days; null is returned if there are not enough slots to be examined</returns>
        protected DateTime? GetRestrictDate(JobSchedulingEngine engine, DateTime startDate, bool forward)
        {
            DateTime? result;

            // get the resource for which we are to walk the calendar
            Resource resource = engine.JobSchedulingData.Resources[EndJob.ResourceId];

            // get a slots enumerator for the resource
            IEnumerator<CapacitySlot> capacitySlotsEnumerator;

            if (forward)
            {
                capacitySlotsEnumerator = resource.GetForwardEnumerator(startDate);
            }
            else
            {
                capacitySlotsEnumerator = resource.GetBackwardEnumerator(startDate);
            }

            DateTime? lastDate = null;
            int leadTimeDays = FixedLeadTime + 1;

            // while we are getting slots and we have not exceeded the lead time days count
            while (capacitySlotsEnumerator.MoveNext() && leadTimeDays > 0)
            {
                CapacitySlot currentSlot = capacitySlotsEnumerator.Current;
                if (currentSlot.StartTime.Date != lastDate)
                {
                    lastDate = currentSlot.StartTime.Date;
                    leadTimeDays--;
                }
            }

            if (leadTimeDays > 0)
            {
                result = null;
            }
            else
            {
                result = lastDate;
            }

            return result;
        }

        /// <summary>
        /// Propagation of the constraint
        /// </summary>
        /// <param name="engine">Job scheduling engine</param>
        /// <returns>true on success false otherwise</returns>
        protected override bool Propagate(JobSchedulingEngine engine)
        {
            bool result = true;

            Logger.Log(string.Format(CultureInfo.InvariantCulture, "PropagateConstraint {0}", this.ToString()));

            if (!UseWorkingTimes)
            {
                result = PropagateLessOrEqual(StartJob.JobVariables.StartTimeVar, EndJob.JobVariables.StartTimeVar, FixedLeadTime, false); // date1<=date2+delay
            }
            else
            {
                // only walk the working times if the resource is bound and there is a fixed lead time to apply
                if (StartJob.JobVariables.ResourceVar.IsBound() &&
                    FixedLeadTime > 0)
                {
                    // walk forward starting from the lower bound of the start time variable of the first (start) job
                    DateTime? restrictDate = GetRestrictDate(engine, StartJob.JobVariables.StartTimeVar.LowerBound, true);
                    if (restrictDate == null)
                    {
                        return false;
                    }

                    // restrict the lower bound on the EndJob StartTime variable
                    result = EndJob.JobVariables.StartTimeVar.RestrictLowerBound(restrictDate.Value.Date);

                    // walk backward starting from the upper bound of the end time variable of the second (end) job
                    DateTime enumerationStartDate = EndJob.JobVariables.EndTimeVar.UpperBound.Date;
                    if (EndJob.JobVariables.EndTimeVar.UpperBound.Date != DateTime.MaxValue.Date)
                    {
                        enumerationStartDate = enumerationStartDate.AddDays(1);
                    }
                    restrictDate = GetRestrictDate(engine, enumerationStartDate, false);
                    if (restrictDate == null)
                    {
                        return false;
                    }

                    if (restrictDate > EndJob.JobVariables.StartTimeVar.UpperBound)
                    {
                        // restrict the upper bound on the EndJob EndTime variable
                        result = result && EndJob.JobVariables.EndTimeVar.RestrictUpperBound(restrictDate.Value.Date);
                    }
                }
            }

            return result;
        }
    }
}

```

Build the project.

Copy the FixedLeadTimeEngine.dll to your bin folder of the Server and Client installation. A typical location for the server bin folder is c:\\Microsoft Dynamics AX\\60\\Server\\Microsoft\\bin. Since the scheduling runs on the server, the newly built assembly must exist either in the bin folder of the server or in the Global Assembly Cache. The assembly also must be copied to the client folder, where it is loaded by the client and used during compiling of the X++ code that is referencing it. The client bin folder is typically located at C:\\Microsoft Dynamics AX\\60\\Client\\Bin.

### ![Hh830900.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Hh830900.collapse_all(en-us,AX.60).gif")Referencing the Custom Engine and Constraint

In order to use the newly built custom engine code, follow these steps:

  - Start Microsoft Dynamics AX development workspace.

  - Right-click the **References** node and then click **Add reference**.

![Adding a reference to the custome engine](images/Hh830900.Addingareferencetothecustomeengine(en-us,AX.60).png "Adding a reference to the custome engine")

  - Browse to the bin folder of the client, select the FixedLeadTimeEngine.dll, and then click **Open**.

![Select the assembly](images/Hh830900.AddingaReferencetotheCustomEngine(en-us,AX.60).png "Select the assembly")

  - Click OK and then restart both the client and the server. You can now use the constraint from the X++ code.

### ![Hh830900.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Hh830900.collapse_all(en-us,AX.60).gif")Adding an Instance of the Constraint to the C\# Engine for the Temporary Job of Each Operation

To enforce the custom constraint on the temporary job created for each operation, you change the type of the C\# engine used by the X++ pre-processor.

1.  In the **Classes** node of the AOT, find the WrkCtrSchedulerJobSchedulingEngine class.

2.  Open the classDeclaration and locate the member variables. Change the type of scheduleEngine. The following code changes the schedule engine type to FixedLeadTimeEngine.

        class WrkCtrSchedulerJobSchedulingEngine implements WrkCtrSchedulerEngineInterface.

            {
  
            // Fixed lead time - AAA
            // Microsoft.Dynamics.AX.Planning.JobScheduling.ISchedulingEngine scheduleEngine;
            FixedLeadTimeEngine.FixedLeadTimeEngine scheduleEngine;

Update the init method of the WrkCtrSchedulerJobSchedulingEngine class.

    // Fixed lead time - AAA
            //scheduleEngine = Microsoft.Dynamics.AX.Planning.JobScheduling.JobSchedulingEngineInteropFactory::CreateJobSchedulingEngine(engineDataProvider, scheduledDataWriter);
            scheduleEngine = new FixedLeadTimeEngine.FixedLeadTimeEngine(engineDataProvider, scheduledDataWriter);

To modify the X++ to C\# interface of the scheduler, add a new method to the WrkCtrSchedulerEngineInterface class. You use the method to emit a fixed lead time constraint to the C\# engine. To add a new method, right-click the WrkCtrSchedulerEngineInterface class, click New Method and replace the method contents with the following:

    /// <summary>
    /// Defines the fixed lead time constraint.
    /// </summary>
    /// <param name="_startJobId">
    /// The start job identifier.
    /// </param>
    /// <param name="_endJobId">
    /// The end job identifier.
    /// </param>
    /// <param name="_fixedLeadTime">
    /// An integer value that specifies the fixed lead time in days.
    /// </param>
    /// <param name="_useWorkingTimes">
    /// A Boolean that indicates whether calendar information (working times) are taken into account during fixed lead time calculations.
    /// </param>
    public void addConstraintFixedLeadTime(int64    _startJobId,
                                           int64    _endJobId,
                                           Integer  _fixedLeadTime,
                                           Boolean  _useWorkingTimes)
    {
    }

You must also add this method to the proxy class WrkCtrSchedulerJobSchedulingEngine. This class emits all the constraints to the actual C\# engine object. To add a new method, right-click the WrkCtrSchedulerJobSchedulingEngine class, click New Method and replace the method contents with the following:

    /// <summary>
    /// Defines the fixed lead time constraint.
    /// </summary>
    /// <param name="_startJobId">
    /// The start job identifier.
    /// </param>
    /// <param name="_endJobId">
    /// The end job identifier.
    /// </param>
    /// <param name="_fixedLeadTime">
    /// An integer value that specifies the fixed lead time in days.
    /// </param>
    /// <param name="_useWorkingTimes">
    /// A Boolean that indicates whether calendar information (working times) are taken into account during fixed lead time calculations.
    /// </param>
    public void addConstraintFixedLeadTime(int64    _startJobId,
                                           int64    _endJobId,
                                           Integer  _fixedLeadTime,
            Boolean  _useWorkingTimes)
    {
        this.flushCommands();
        scheduleEngine.AddConstraintFixedLeadTime(_startJobId, _endJobId, _fixedLeadTime, _useWorkingTimes);
    }


> [!NOTE]
> <P>The flushCommands() call makes sure that all jobs, resources and constraints that were emitted previously and were cached are flushed to the engine.</P>



Add the constraint for the temporary jobs in the loadJobsDetail method of the WrkCtrScheduler\_Prod class. The code example below shows the changes that must be made to the loadJobsDetail method.


> [!NOTE]
> <P>A complete implementation of the loadJobsDetails method, including the changes made in the following code sample, can be found at the bottom of this topic. The following section illustrates what changes are necessary to implement the scheduling customization.</P>



``` 
protected container loadJobsDetail(WrkCtrParmSchedule           _wrkCtrParmSchedule,
                                   ProdTable                    _prodTable,
                                   BOMCalcData                  _bomCalcData,
                                   ProdRoute                    _prodRoute,
                                   WrkCtrActivityRequirementSet _wrkCtrActivityRequirementSet,
                                   InventSiteId                 _siteId,
                                   ProdTable                    _prodTableNext,
                                   OprNum                       _prodTableNextOprNum,
                                   BOMLevel                     _startCollectRefLevel,
                                   BOMLevel                     _maxCollectRefLevel,
                                   RecId                        _jobNumNextOprFirst,
                                   RecId                        _jobNumNextOprLast,
                                   OprNum                       _oprNumPrev)
{
    // Fixed lead time - AAA
    #define.LeadTimeInDays(2)
    #define.LeadTimeCalendar('24Hours')

    int64                       fixedLeadTimeJob;
    // Fixed lead time - ZZZ

    WrkCtrSchedulerGoal         goal;

...

    this.insertParallelJobsConstraints(jobTypePrev,
                                       _jobNumNextOprFirst,
                                       SchedJobLink::FS,
                                       routeLinkType,
                                       _wrkCtrParmSchedule.schedMethod());

    // Fixed lead time - AAA
    fixedLeadTimeJob = this.insertEmptyJob(_wrkCtrParmSchedule,
                                       prodTable.ProdId,
                                       _startCollectRefLevel,
                                       prodTable.CollectRefLevel,
                                       _wrkCtrParmSchedule.schedDate(),
                                       _wrkCtrParmSChedule.schedTime(),
                                       #LeadTimeCalendar);

    // insert constraints for parallel jobs for a specific job type
    this.insertParallelJobsConstraints(jobTypePrev,
                                       fixedLeadTimeJob,
                                       SchedJobLink::FS,
                                       SchedJobLinkType::Soft,
                                       _wrkCtrParmSchedule.schedMethod());

    if (_jobNumNextOprFirst)
    {
        scheduleEngine.addJobLink(fixedLeadTimeJob,
                                  _jobNumNextOprFirst,
                                  SchedJobLink::FS,
                                  prodRoute.LinkType);
    }

    scheduleEngine.addConstraintFixedLeadTime(jobNumFirst,
                                              fixedLeadTimeJob,
                                              #LeadTimeInDays,
                                              true);

    jobNum = fixedLeadTimeJob;
    // Fixed lead time - ZZZ

    // Return the first job and last job of this operation, which will be used in the next loop
    // for linking the previous operation to this operation
    return [jobNumFirst, jobNum];
}
 
```

### ![Hh830900.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Hh830900.collapse_all(en-us,AX.60).gif")Testing the Fixed Lead Time Customization

You can test your changes by adding a new project to your Visual Studio solution. Below are the steps you can use to create the test project:

1.  Open Visual Studio and open the FixedLeadTimeEngine solution.

2.  Right-click the solution, click **Add**, and then click **New Project**.

3.  Select Visual C\# as project type.

4.  Select **Class Library** as the template.

5.  Name the project FixedLeadTimeEngineTest and then click **OK**.

6.  Rename Class1.cs to FixedLeadTimeEngineTest.cs and copy or paste the following code.

7.  Add a reference in the project to Microsoft.Dynamics.AX.Planning.JobScheduling.Dll (can be located in the bin folder of the Microsoft Dynamics AX client or server installation. Add a reference to the FixedLeadTimeEngine assembly, which can found in the bin directory of your Visual Studio project folder. Also add a reference to Microsoft.VisualStudio.QualityTools.UnitTestFramework.dll, which can be located in your Visual Studio folder. For example, in 2010, it is located under Program Files (x86)\\Microsoft Visual Studio 10.0\\Common7\\IDE\\PublicAssemblies.

<!-- end list -->

    //-----------------------------------------------------------------------
    // <copyright file="FixedLeadTimeEngineTest.cs" company="Microsoft Corporation">
    //     Copyright (c) Microsoft Corporation. All rights reserved.
    // </copyright>
    //-----------------------------------------------------------------------
    
    namespace FixedLeadTimeEngineTest
    {
        using System;
        using System.Text;
        using System.Collections;
        using System.Collections.Generic;
        using System.Globalization;
        using System.Linq;
        using Microsoft.VisualStudio.TestTools.UnitTesting;
        using Microsoft.Dynamics.AX.Planning.JobScheduling;
        using FixedLeadTimeEngine;
    
        /// <summary>
        /// Summary description for UnitTest1
        /// </summary>
        [TestClass]
        public class FixedLeadTimeEngineTest
        {
            /// <summary>
            /// Default value for allowed sequence schedule runtime
            /// </summary>
            private const int SequenceScheduleRuntimeLimit = -1;
    
            /// <summary>
            /// Default value for sequence optimization runtime
            /// </summary>
            private const int SequenceOptimizationRuntimeLimit = 0;
    
            /// <summary>
            /// Empty properties list
            /// </summary>
            private static readonly Hashtable EmptyProperties = new Hashtable();
    
            #region Additional test attributes
            //
            // You can use the following additional attributes as you write your tests:
            //
            // Use ClassInitialize to run code before running the first test in the class
            // [ClassInitialize()]
            // public static void MyClassInitialize(TestContext testContext) { }
            //
            // Use ClassCleanup to run code after all tests in a class have run
            // [ClassCleanup()]
            // public static void MyClassCleanup() { }
            //
            // Use TestInitialize to run code before running each test 
            // [TestInitialize()]
            // public void MyTestInitialize() { }
            //
            // Use TestCleanup to run code after each test has run
            // [TestCleanup()]
            // public void MyTestCleanup() { }
            //
            #endregion
    
            /// <summary>
            /// Find job in scheduled job list.
            /// Notice this method scales as O(n) where n=scheduledJobs.count
            /// Throws an ArgumentOutOfRangeException if job does not exist
            /// </summary>
            /// <param name="scheduledJobs">list of scheduled jobs</param>
            /// <param name="jobNum">job number to find</param>
            /// <returns>A JobData instance containing the results of the scheduling for the specified job.</returns>
            public JobSchedulingResult GetScheduledJob(ICollection<JobSchedulingResult> scheduledJobs, int jobNum)
            {
                foreach (JobSchedulingResult job in scheduledJobs)
                {
                    if (job.JobId == jobNum)
                    {
                        return job;
                    }
                }
    
                throw new ArgumentOutOfRangeException("jobNum", jobNum, string.Format(CultureInfo.InvariantCulture, "Could not find job {0}", jobNum));
            }
    
            /// <summary>
            /// 2 Operations: Op 10 and Op 20
            /// 3 jobs:
            /// 0 = (10 Process) - requires 1s of capacity
            /// 1 = (10 FixedLeadTimeTemporaryJob) - 0s
            /// 2 = (20 Process) - 1s of capacity
            /// 
            /// 0, 1 and 2 are all on the same resource (R0 which has 1h available every day)
            /// Links: 0->1->2
            /// Between 0 and 1 there is a fixed lead time constraint that enforces that the start of 1 can not be earlier than the lead time
            /// The fixed lead time is 2 days
            /// All jobs have a goal of EarliestEndTime, the sequence starts at StartDate
            /// 
            /// Expected:
            /// Job 0 is scheduled on [StartDate, StartDate + 1s]
            /// Job 1 is scheduled on [StartDate + 2d, StartDate + 2d]
            /// Job 2 is scheduled on [StartDate + 2d, StartDate + 2d + 1s]
            /// </summary>
            [TestMethod]
            public void TestFixedLeadTime()
            {
                FixedLeadTimeEngine jobSchedulingEngine = new FixedLeadTimeEngine();
    
                jobSchedulingEngine.AddResource("R0", true, 1, 1, 0, false, false);
    
                jobSchedulingEngine.AddJobInfo(0, JobGoal.EarliestEndTime, true, true);
                jobSchedulingEngine.AddJobInfo(1, JobGoal.EarliestEndTime, false, false);
                jobSchedulingEngine.AddJobInfo(2, JobGoal.EarliestEndTime, true, true);
    
                DateTime startDate = new DateTime(2020, 1, 1);
                jobSchedulingEngine.AddJobResourceCapacity(0, "R0", 1, 1, startDate.AddYears(1), EmptyProperties, true);
                jobSchedulingEngine.AddJobResourceRuntime(1, "R0", 0);
                jobSchedulingEngine.AddJobResourceCapacity(2, "R0", 1, 1, startDate.AddYears(1), EmptyProperties, true);
                jobSchedulingEngine.AddConstraintOnSameResource(0, 1);
                jobSchedulingEngine.AddConstraintOnSameResource(1, 2);
    
                for (int i = 0; i < 10; i++)
                {
                    jobSchedulingEngine.AddWorkingTime("R0", startDate.AddDays(i), startDate.AddDays(i).AddHours(1), 1, EmptyProperties);
                }
    
                // fixed lead time constraint of 2 days
                jobSchedulingEngine.AddConstraintFixedLeadTime(0, 1, 2, false);
                jobSchedulingEngine.AddJobLink(0, 1, (int)JobLinkRelation.FinishStart, (int)JobLinkType.Soft);
                jobSchedulingEngine.AddJobLink(1, 2, (int)JobLinkRelation.FinishStart, (int)JobLinkType.Soft);
    
                jobSchedulingEngine.Run(SequenceScheduleRuntimeLimit, SequenceOptimizationRuntimeLimit);
    
                Assert.AreEqual(3, jobSchedulingEngine.ScheduledJobs.Count);
                JobSchedulingResult job0 = GetScheduledJob(jobSchedulingEngine.ScheduledJobs, 0);
                JobSchedulingResult job1 = GetScheduledJob(jobSchedulingEngine.ScheduledJobs, 1);
                JobSchedulingResult job2 = GetScheduledJob(jobSchedulingEngine.ScheduledJobs, 2);
                Console.WriteLine(startDate.AddSeconds(1).ToString());
                Console.ReadLine();
                Assert.AreEqual(startDate, job0.JobStartTime);
                Assert.AreEqual(startDate.AddSeconds(1), job0.JobEndTime);
                Assert.AreEqual(startDate.AddDays(2), job1.JobStartTime);
                Assert.AreEqual(startDate.AddDays(2), job1.JobEndTime);
                Assert.AreEqual(startDate.AddDays(2), job2.JobStartTime);
                
            }
    
            /// <summary>
            /// 2 Operations: Op 10 and Op 20
            /// 3 jobs:
            /// 0 = (10 Process), requires 3601s of capacity
            /// 1 = (10 FixedLeadTimeTemporaryJob) - 0s
            /// 2 = (20 Process) - 1s of capacity
            /// 
            /// 0, 1 and 2 are all on the same resource (R0 which has 1h available every day)
            /// Links: 0->1->2
            /// Between 0 and 1 there is a fixed lead time constraint that enforces that the start of 1 can not be earlier than the lead time
            /// The fixed lead time is 2 days
            /// All jobs have a goal of EarliestEndTime, the sequence starts at StartDate
            /// 
            /// Expected:
            /// Job 0 is scheduled on [StartDate, StartDate + 1s]
            /// Job 1 is scheduled on [StartDate + 2d, StartDate + 2d]
            /// Job 2 is scheduled on [StartDate + 2d, StartDate + 2d + 1s]
            /// </summary>
            [TestMethod]
            public void TestFixedLeadTimeOperation1SpanscompleteDay()
            {
                FixedLeadTimeEngine jobSchedulingEngine = new FixedLeadTimeEngine();
    
                jobSchedulingEngine.AddResource("R0", true, 1, 1, 0, false, false);
    
                jobSchedulingEngine.AddJobInfo(0, JobGoal.EarliestEndTime, true, true);
                jobSchedulingEngine.AddJobInfo(1, JobGoal.EarliestEndTime, false, false);
                jobSchedulingEngine.AddJobInfo(2, JobGoal.EarliestEndTime, true, true);
    
                DateTime startDate = new DateTime(2020, 1, 1);
                jobSchedulingEngine.AddJobResourceCapacity(0, "R0", 3601, 1, startDate.AddYears(1), EmptyProperties, true);
                jobSchedulingEngine.AddJobResourceRuntime(1, "R0", 0);
                jobSchedulingEngine.AddJobResourceCapacity(2, "R0", 1, 1, startDate.AddYears(1), EmptyProperties, true);
                jobSchedulingEngine.AddConstraintOnSameResource(0, 1);
                jobSchedulingEngine.AddConstraintOnSameResource(1, 2);
    
                for (int i = 0; i < 10; i++)
                {
                    jobSchedulingEngine.AddWorkingTime("R0", startDate.AddDays(i), startDate.AddDays(i).AddHours(1), 1, EmptyProperties);
                }
    
                // fixed lead time constraint of 2 days
                jobSchedulingEngine.AddConstraintFixedLeadTime(0, 1, 2, false);
                jobSchedulingEngine.AddJobLink(0, 1, (int)JobLinkRelation.FinishStart, (int)JobLinkType.Soft);
                jobSchedulingEngine.AddJobLink(1, 2, (int)JobLinkRelation.FinishStart, (int)JobLinkType.Soft);
    
                jobSchedulingEngine.Run(SequenceScheduleRuntimeLimit, SequenceOptimizationRuntimeLimit);
    
                Assert.AreEqual(3, jobSchedulingEngine.ScheduledJobs.Count);
                
                JobSchedulingResult job0 = GetScheduledJob(jobSchedulingEngine.ScheduledJobs, 0);
                JobSchedulingResult job1 = GetScheduledJob(jobSchedulingEngine.ScheduledJobs, 1);
                JobSchedulingResult job2 = GetScheduledJob(jobSchedulingEngine.ScheduledJobs, 2);
    
                Assert.AreEqual(startDate, job0.JobStartTime);
                Assert.AreEqual(startDate.AddDays(1).AddSeconds(1), job0.JobEndTime);
                Assert.AreEqual(startDate.AddDays(2), job1.JobStartTime);
    
              
               
                Assert.AreEqual(startDate.AddDays(2), job1.JobEndTime);
                Assert.AreEqual(startDate.AddDays(2), job2.JobStartTime);
            }
    
            /// <summary>
            /// 2 Operations: Op 10 and Op 20
            /// 3 jobs:
            /// 0 = (10 Process), requires 3601s of capacity
            /// 1 = (10 FixedLeadTimeTemporaryJob) - 0s
            /// 2 = (20 Process) - 1s of capacity
            /// 
            /// Job 1 uses the calendar
            /// 
            /// 0, 1 and 2 are all on the same resource (R0 which has 1h available every day, except for StartDate + 1)
            /// Links: 0->1->2
            /// Between 0 and 1 there is a fixed lead time constraint that enforces that the start of 1 cannot be earlier than the lead time
            /// The fixed lead time is 2 days
            /// All jobs have a goal of EarliestEndTime, the sequence starts at StartDate
            /// 
            /// Expected:
            /// Job 0 is scheduled on [StartDate, StartDate + 1s]
            /// Job 1 is scheduled on [StartDate + 3d, StartDate + 3d]
            /// Job 2 is scheduled on [StartDate + 3d, StartDate + 3d + 1s]
            /// </summary>
            [TestMethod]
            public void TestFixedLeadTimeOperation1WorkingTimes()
            {
                Logger.Enabled = true;
    
                FixedLeadTimeEngine jobSchedulingEngine = new FixedLeadTimeEngine();
    
                jobSchedulingEngine.AddResource("R0", true, 1, 1, 0, false, false);
    
                jobSchedulingEngine.AddJobInfo(0, JobGoal.EarliestEndTime, true, true);
                jobSchedulingEngine.AddJobInfo(1, JobGoal.EarliestEndTime, false, false);
                jobSchedulingEngine.AddJobInfo(2, JobGoal.EarliestEndTime, true, true);
    
                DateTime startDate = new DateTime(2020, 1, 1);
                jobSchedulingEngine.AddJobResourceCapacity(0, "R0", 1, 1, startDate.AddYears(1), EmptyProperties, true);
                jobSchedulingEngine.AddJobResourceRuntime(1, "R0", 0);
                jobSchedulingEngine.AddJobResourceCapacity(2, "R0", 1, 1, startDate.AddYears(1), EmptyProperties, true);
                jobSchedulingEngine.AddConstraintOnSameResource(0, 1);
                jobSchedulingEngine.AddConstraintOnSameResource(1, 2);
    
                for (int i = 0; i < 10; i++)
                {
                    if (i != 1)
                    {
                        jobSchedulingEngine.AddWorkingTime("R0", startDate.AddDays(i), startDate.AddDays(i).AddHours(1), 1, EmptyProperties);
                    }
                }
    
                // fixed lead time constraint of 2 days
                jobSchedulingEngine.AddConstraintFixedLeadTime(0, 1, 2, true);
                jobSchedulingEngine.AddJobLink(0, 1, (int)JobLinkRelation.FinishStart, (int)JobLinkType.Soft);
                jobSchedulingEngine.AddJobLink(1, 2, (int)JobLinkRelation.FinishStart, (int)JobLinkType.Soft);
    
                jobSchedulingEngine.Run(SequenceScheduleRuntimeLimit, SequenceOptimizationRuntimeLimit);
    
                Assert.AreEqual(3, jobSchedulingEngine.ScheduledJobs.Count);
                JobSchedulingResult job0 = GetScheduledJob(jobSchedulingEngine.ScheduledJobs, 0);
                JobSchedulingResult job1 = GetScheduledJob(jobSchedulingEngine.ScheduledJobs, 1);
                JobSchedulingResult job2 = GetScheduledJob(jobSchedulingEngine.ScheduledJobs, 2);
    
                Assert.AreEqual(startDate, job0.JobStartTime);
                Assert.AreEqual(startDate.AddSeconds(1), job0.JobEndTime);
                Assert.AreEqual(startDate.AddDays(3), job1.JobStartTime);
                Assert.AreEqual(startDate.AddDays(3), job1.JobEndTime);
                Assert.AreEqual(startDate.AddDays(3), job2.JobStartTime);
    
                Logger.Enabled = false;
            }
        }
    }

You can run tests from the **Test View** window and the **Test List Editor** window. To run one or more tests displayed in the **Test View** window, first select the tests in that window. To select multiple tests, hold either the Shift or CTRL key when clicking tests. Then click the **Run Tests** button in the **Test View** window toolbar.

### ![Hh830900.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Hh830900.collapse_all(en-us,AX.60).gif")The Full Implementation of the loadJobDetails method of the WrkCtrScheduler\_Prod class

To fully implement the loadJobDetails method, including the changes that were made to add the constraint to the temporary jobs, copy and paste the following code into the loadJobDetails method of the WrkCtrScheduler\_Prod class.

    /// <summary>
    /// Loads job information for the jobs of one operation into the scheduling engine.
    /// </summary>
    /// <param name="_wrkCtrParmSchedule">
    /// A <c>WrkCtrParmSchedule</c> table buffer that contains all the scheduling parameters needed for the scheduling of the order.
    /// </param>
    /// <param name="_order">
    /// A record with the data for the order being scheduled (<c>ProdTable</c>, <c>ReqTrans</c>, etc.).
    /// </param>
    /// <param name="_bomCalcData">
    /// A <c>BomCalcData</c> instance used to calculate the runtime of the job.
    /// </param>
    /// <param name="_routeMap">
    /// A <c>RouteMap</c> map with the operation data.
    /// </param>
    /// <param name="_siteId">
    /// The ID of the site stamped on the order.
    /// </param>
    /// <param name="_orderNext">
    /// A record with the data for the next (reference) order.
    /// </param>
    /// <param name="_startCollectRefLevel">
    /// The start BOM level to be used in determining the job goals.
    /// </param>
    /// <param name="_maxCollectRefLevel">
    /// The maximal BOM level to be used in determining the job goals.
    /// </param>
    /// <param name="_jobNumNextOprFirst">
    /// The <c>RecId</c> of the first job of the next operation.
    /// </param>
    /// <param name="_jobNumNextOprLast">
    /// The <c>RecId</c> of the last job of the next operation.
    /// </param>
    /// <returns>
    /// A container with the <c>RecId</c> values for the first and last job.
    /// </returns>
    /// <exception cref="Exception::Error">
    /// Exception thrown in case the resource specified as target resource for an operation is already in the scheduling that operation.
    /// </exception>
    protected container loadJobsDetail(WrkCtrParmSchedule           _wrkCtrParmSchedule,
                                       Common                       _order,
                                       BOMCalcData                  _bomCalcData,
                                       RouteMap                     _routeMap,
                                       InventSiteId                 _siteId,
                                       Common                       _orderNext,
                                       BOMLevel                     _startCollectRefLevel,
                                       BOMLevel                     _maxCollectRefLevel,
                                       recId                        _jobNumNextOprFirst,
                                       recId                        _jobNumNextOprLast)
    {
        ProdJobType                 prodJobType;
        ProdRouteJob                prodRouteJob;
    
        SchedJobLink                primaryLink = SchedJobLink::None;
        SchedJobLinkType            primaryLinkType = SchedJobLinkType::None;
    
        boolean                     isFirstJob = true;
        RouteGroup                  routeGroup;
        MapEnumerator               mapEnumerator;
    
        recId                       jobNum;
        recId                       jobNumPrev = 0;
        recId                       jobNumFirst;
    
        Map                         mapJobNumPrevNumPrimSec = new Map(Types::String,Types::Int64); // Key = numPrimary#numSecondary, Value = JobNum
    
        List                        resourceList;
        RouteJobType                jobTypePrev = RouteJobType::QueueBefore;
        Map                         jobTimes;
        ProdUnitId                  prodUnitId;
        InventLocationIdInput       inputWarehouse;
        recId                       prevProdRouteRecId;
        real                        jobTimeForAllResources;
        Map                         requirementProperties;
        boolean                     useFastSetup;
        real                        primaryJobTime;
        WrkCtrId                    resourceId;
        ProdRoute                   prodRoute;
        ProdTable                   prodTable = _order as ProdTable;
    
        WrkCtrActivityRequirementSet    wrkCtrActivityRequirementSet;
        WrkCtrProdRouteActivity         wrkCtrProdRouteActivity;
        SchedJobLinkType            routeLinkType;
    
        // Local cache of property information and applicable resources.
        Map                          mapOprPriorityToRequirementProperties = new Map(Types::Enum, Types::Class);
    
        #define.LeadTimeInDays(2)
        #define.LeadTimeCalendar('24Hours')
    
        int64                       fixedLeadTimeJob;
    
    
        // initialize the parallel job map
        this.initParallelJobsMap();
    
        masterData.insert(prodTable.ProdId, prodTable);
    
        // Loop through all jobs in the operation
        while select forupdate prodRouteJob
            order by NumType, NumPrimary, OprPriority, NumSecondary, RecId
            where prodRouteJob.ProdId        == prodTable.ProdId &&
                  prodRouteJob.OprNum        == _routeMap.OprNum
        join prodRoute
            where   prodRoute.ProdId        == prodRouteJob.ProdId
            &&      prodRoute.OprNum        == prodRouteJob.OprNum
            &&      prodRoute.OprPriority   == prodRouteJob.OprPriority
        join wrkCtrProdRouteActivity
            where   wrkCtrProdRouteActivity.ProdId          == prodTable.ProdId
            &&      wrkCtrProdRouteActivity.OprNum          == prodRoute.OprNum
            &&      wrkCtrProdRouteActivity.OprPriority     == prodRoute.OprPriority
            &&      wrkCtrProdRouteActivity.RouteDataAreaId == prodRoute.DataAreaId
        join wrkCtrActivityRequirementSet
            where wrkCtrActivityRequirementSet.Activity == wrkCtrProdRouteActivity.Activity
        join routeGroup
            where routeGroup.RouteGroupId == prodRoute.RouteGroupId
        {
            jobNum = prodRouteJob.RecId;
    
            this.addJobToOverlapJobList(prodRouteJob, prodRoute.OprNumNext);
    
            prodJobType     = ProdJobType::construct(prodRouteJob.JobType);
            routeLinkType   = prodRoute.LinkType;
    
            this.updateRequirementSetAndPropertiesMaps(mapOprPriorityToRequirementProperties,
                                                       prodRouteJob,
                                                       wrkCtrActivityRequirementSet,
                                                       _siteId,
                                                       _wrkCtrParmSchedule.schedMethod());
            requirementProperties = mapOprPriorityToRequirementProperties.lookup(prodRouteJob.OprPriority);
    
            [prevProdRouteRecId, prodUnitId, inputWarehouse] = this.getProductionUnitAndWarehouse(
                                                                                                 prodRoute.RecId,
                                                                                                 prevProdRouteRecId,
                                                                                                 _wrkCtrParmSchedule,
                                                                                                 prodUnitId,
                                                                                                 inputWarehouse,
                                                                                                 prodRoute);
            // Fast setup applies when
            // - only site and resource group requirements exists
            // - the job is not locked
            // - job scheduling is used
            // - runtimes are resource independent (formula0)
            // - not doing property limited scheduling
            useFastSetup = !_wrkCtrParmSchedule.propertyLimited() &&
                           (_wrkCtrParmSchedule.schedMethod() == SchedMethod::Detail) &&
                           this.requirementsAllowFastSetup(requirementProperties) &&
                           prodJobType.isWrkCtrHoursResourceIndependent(prodRoute);
    
            if (useFastSetup)
            {
                if (prodRouteJob.OprPriority == RouteOprPriority::Primary && prodRouteJob.NumPrimary == 1)
                {
                    jobTimeForAllResources = this.computeJobTime(_wrkCtrParmSchedule,
                                                                 prodRouteJob,
                                                                 prodRoute,
                                                                 prodRoute,
                                                                 prodRouteJob.JobType,
                                                                 _bomCalcData,
                                                                 prodRouteJob.JobStatus < ProdJobStatus::Completed,
                                                                 prodJobType);
                    primaryJobTime = jobTimeForAllResources;
                }
                else
                {
                    jobTimeForAllResources = primaryJobTime;
                }
            }
            else
            {
                // Resources based on the requirements
                resourceList = wrkCtrApplicableResourceListCache.applicableResourceList(wrkCtrActivityRequirementSet,
                                                                                        _siteId,
                                                                                        _wrkCtrParmSchedule.minimumSchedDate(),
                                                                                        _wrkCtrParmSchedule.schedMethod()==SchedMethod::Detail,
                                                                                        _wrkCtrParmSchedule.schedMethod()==SchedMethod::Rough,
                                                                                        _wrkCtrParmSchedule.schedMethod()==SchedMethod::Rough);
    
                // operations scheduling is done on resource groups
                if (_wrkCtrParmSchedule.schedMethod()==SchedMethod::Rough)
                {
                     // operations scheduling with specific resource requirement
                    resourceId = this.getResourceRequirement(requirementProperties);
                    if (resourceId != '')
                    {
                        resourceList.addEnd(resourceId);
                    }
                }
    
    
                if (resourceList.elements() == 0)
                {
                    this.addInfologMessage(_wrkCtrParmSchedule,
                                           WrkCtrJobSchedulingError::NoMatchingResources,
                                           '',
                                           prodRouteJob);
                }
    
                if (prodRouteJob.OprPriority == RouteOprPriority::Primary && prodRouteJob.NumPrimary == 1)
                {
                    // Set common values for all parallel jobs
                    prodJobType    = ProdJobType::construct(prodRouteJob.JobType);
    
                    jobTimes = this.computeJobTimes(_wrkCtrParmSchedule,
                                                    prodRouteJob,
                                                    prodRoute,
                                                    prodRoute,
                                                    prodRouteJob.JobType,
                                                    resourceList,
                                                    _bomCalcData,
                                                    prodRouteJob.JobStatus < ProdJobStatus::Completed,
                                                    prodJobType);
    
                    primaryJobTime = 0;
                    if (jobTimes.elements() > 0)
                    {
                        mapEnumerator = jobTimes.getEnumerator();
                        if (mapEnumerator && mapEnumerator.moveNext())
                        {
                            primaryJobTime = mapEnumerator.currentValue();
                        }
                    }
                }
                else
                {
                    jobTimes = this.fixedJobTimesForResources(resourceList,
                                                              primaryJobTime);
                }
            }
    
            [primaryLink, primaryLinkType, jobNumFirst, isFirstJob, jobNumPrev, jobTypePrev] = this.insertJobAndConstraints(
                                                                                                                            prodRouteJob,
                                                                                                                            _wrkCtrParmSchedule,
                                                                                                                            prodUnitId,
                                                                                                                            inputWarehouse,
                                                                                                                            requirementProperties,
                                                                                                                            jobTimes,
                                                                                                                            wrkCtrActivityRequirementSet,
                                                                                                                            prodRoute.OprNumNext,
                                                                                                                            prodJobType,
                                                                                                                            routeGroup,
                                                                                                                            this.computeJobGoal(_wrkCtrParmSchedule, prodTable.CollectRefLevel, _startCollectRefLevel),
                                                                                                                            useFastSetup,
                                                                                                                            jobTimeForAllResources,
                                                                                                                            jobNumPrev,
                                                                                                                            mapJobNumPrevNumPrimSec,
                                                                                                                            resourceList,
                                                                                                                            isFirstJob,
                                                                                                                            jobTypePrev,
                                                                                                                            primaryLink,
                                                                                                                            primaryLinkType,
                                                                                                                            jobNumFirst);
    
            this.insertNotOnSameResConstraints(_wrkCtrParmSchedule, prodRouteJob);
        }
    
        // insert constraints for parallel jobs for a specific job type
        this.insertParallelJobsConstraints(jobTypePrev,
                                           _jobNumNextOprFirst,
                                           SchedJobLink::FS,
                                           routeLinkType,
                                           _wrkCtrParmSchedule.schedMethod());
    
    
        fixedLeadTimeJob = this.insertEmptyJob(_wrkCtrParmSchedule,
                                           prodTable.ProdId,
                                           _startCollectRefLevel,
                                           prodTable.CollectRefLevel,
                                           _wrkCtrParmSchedule.schedDate(),
                                           _wrkCtrParmSChedule.schedTime());
    
        // insert constraints for parallel jobs for a specific job type
        this.insertParallelJobsConstraints(jobTypePrev,
                                           fixedLeadTimeJob,
                                           SchedJobLink::FS,
                                           SchedJobLinkType::Soft,
                                           _wrkCtrParmSchedule.schedMethod());
    
        if (_jobNumNextOprFirst)
        {
            scheduleEngine.addJobLink(fixedLeadTimeJob,
                                      _jobNumNextOprFirst,
                                      SchedJobLink::FS,
                                      prodRoute.LinkType);
        }
    
        scheduleEngine.addConstraintFixedLeadTime(jobNumFirst,
                                                  fixedLeadTimeJob,
                                                  #LeadTimeInDays,
                                                  true);
    
        jobNum = fixedLeadTimeJob;
    
    
        // Return the first job and last job of this operation, which will be used in the next loop
        // for linking the previous operation to this operation
        return [jobNumFirst, jobNum];
    }

## See also

[Customizing the Resource Scheduling Engine](customizing-the-resource-scheduling-engine.md)

[Microsoft.Dynamics.AX.Planning.JobScheduling Namespace](http://msdn.microsoft.com/en-us/library/microsoft.dynamics.ax.planning.jobscheduling.aspx)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

