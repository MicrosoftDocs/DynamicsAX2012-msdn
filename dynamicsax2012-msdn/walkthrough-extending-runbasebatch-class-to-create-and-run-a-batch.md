---
title: 'Walkthrough: Extending RunBaseBatch Class to Create and Run a Batch'
TOCTitle: 'Walkthrough: Extending RunBaseBatch Class to Create and Run a Batch'
ms:assetid: b94e68f1-588b-4472-bb08-7a37da9a74ec
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc636647(v=AX.60)
ms:contentKeyID: 35249863
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Walkthrough: Extending RunBaseBatch Class to Create and Run a Batch 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

You can design your own batch job by extending the RunBaseBatch class. You can also write code to schedule the batch to run.

By default, after a batch is scheduled, the batch is no longer associated with the client. The batch runs on the Application Object Server (AOS). However, you have the option to make a batch run on a client.

This walkthrough illustrates the following tasks:

  - Configuring your AOS batch server

  - Extending the RunBaseBatch class

  - Scheduling your batch

  - Viewing your scheduled batch

  - Making your batch dependent on a client session

  - Running your batch on the client

## Configuring Your AOS Batch Server

In this procedure you will configure your AOS to be a batch server.

### To configure your AOS batch server

1.  Open an application workspace.

2.  In the **Navigation Pane**, click **Administration**, expand **Setup**, expand System, and then click **Server configuration**.

3.  In the **Server configuration** form, click the row that has your AOS listed.

4.  In the details section of the form, select the check box that is labeled **Is batch server**.

5.  In the **Batch server schedule** section, make sure that the server can process at least a few concurrent threads (eight is a nice default). Ensure the start-to-end time range is broad enough to include the time when you want to test.

6.  Close the form.

## Extending the RunBaseBatch Class

In this procedure, you will extend the RunBaseBatch class. Objects of type RunBaseBatch implement all the methods that the system needs in order to run the object as a batch job. You will extend RunBaseBatch to override the run method. The run method contains the logic that handles the particular processing need that you are solving.

### To extend RunBaseBatch

1.  Press Ctrl+D to open the Application Object Tree (AOT) in a development workspace.

2.  Right-click the **Classes** node, and then select **New Class**.

3.  Expand the node for your new class. Rename it **Batch4DemoClass**.

4.  Right-click the **classDeclaration** node under **Batch4DemoClass**, and then click **View Code**.

5.  In the code **Editor** window, after Batch4DemoClass, add extends RunBaseBatch. Save the change.

6.  In the AOT right-click the **Batch4DemoClass** node, select **Override method**, and then select the **run** method. Edit the run method to match the code shown in the following example.

7.  Override the methods pack and unpack. Edit them to match the code shown in the following example.
    

    > [!NOTE]
    > <P>For this example, do not yet override the runsImpersonated method. The base method always returns true. true means the batch must run under the authority of the person who scheduled the batch, and that no client session is involved.</P>

    
```X++
    class Batch4DemoClass extends RunBaseBatch
        {
            public void run()
            {
                // The purpose of your job.
                info(strFmt("Hello from Batch4DemoClass .run at %1"
                    ,DateTimeUtil ::toStr(
                        DateTimeUtil ::utcNow())
                    ));
            }
            public container pack()
            {
                return conNull();
            }
            public boolean unpack(container packedClass)
            {
                return true;
            }
        }
```

## Scheduling Your Batch

In this procedure, you will write an X++ job that can be run to schedule an occurrence of your batch. Then you will run the job.

### To schedule your batch job

1.  In the AOT, right-click the **Jobs** node, and then select **New Job**.

2.  In the **Editor** window, enter the X++ code shown in the following example, and then save the changes.

3.  In the **Editor** window, press F7 to compile your job, and then press F5 to run your job.
    

    > [!NOTE]
    > <P>The result of your job is that your batch is scheduled to run.</P>

    
       ```X++
       static void Job_ScheduleBatch2(Args _args)
        {
            BatchHeader batHeader;
            BatchInfo batInfo;
            RunBaseBatch rbbTask;
            str sParmCaption = "My Demonstration (b351)";
            ;
            rbbTask = new Batch4DemoClass();
            batInfo = rbbTask .batchInfo();
            batInfo .parmCaption(sParmCaption);
            batInfo .parmGroupId(""); // The "Empty batch group".
            batHeader = BatchHeader ::construct();
            batHeader .addTask(rbbTask);
            batHeader .save();
            info(strFmt("'%1' batch has been scheduled.", sParmCaption));
        }
       ```

4.  Click the **Build** menu, and then click **Generate Incremental CIL**.  
    This CIL build is necessary because batch jobs that run on the AOS can run only in .NET Framework managed mode.

## Viewing Your Scheduled Batch

In this procedure, you will use the **Navigation Pane** to view the line item that represents your scheduled batch.

### To view your scheduled batch

1.  In the **Navigation Pane**, click **System administration**, expand **Inquiries**, expand **Batch jobs**, and then click **Batch jobs**.

2.  On the **Batch job** form , find the row for you batch job and read its value in the **Status** column. After the status becomes **Ended**, click the **Batch job history** button.

3.  On the **Batch job history** form, click the **Log** button. This displays the **Infolog** form that shows the output message from the Batch4DemoClass .run method.  
    The following are the actual output messages that are captured by the **Infolog**:
    
    Message\_@SYS14327 (02:12:57 pm)   
     Hello from Batch4DemoClass .run, at 2008-01-25T22:05:48   
     Infolog for Job My Demonstration (b351) (5637144579)   
       Infolog for Task My Demonstration (b351) (5637144579)   
         Hello from Batch4DemoClass .run, at 2008-01-25T22:05:48

## Making Your Batch Dependent on a Client Session

In this procedure, you add an override of the runsImpersonated method to your Batch4DemoClass class. Your override method must return false. The value false means that the system cannot run the batch by having it impersonate a logged on session. Instead, the system must find the client session of the user before the system can run the batch (on the server, as always). The client session can exist on a different computer from where the AOS is running.

### To make your batch dependent on a client session

1.  Override the runsImpersonated method of your Batch4DemoClass class. The override code is shown in the example.

2.  Rerun your job ScheduleMyBatchJob\_Job.

3.  View your batch on the **Batch job** form.
    
       ```X++
       public boolean runsImpersonated()
        {
            // false means that the batch must run on a client.
            return false;
        }
       ```

## Running Your Batch on the Client

You have a batch class that overrides the runImpersonated method. The override makes the batch eligible to run only on a client computer. You run a job that schedules the batch. The batch remains in a waiting status until you use the client to tell the AOS to send the client-bound batch to your client now so the batch can run.

In this procedure, you will use the **Navigation Pane** to tell the AOS to send client-bound batches to your client.

### To run your batch on the client

1.  In the **Navigation Pane**, click **Basic**, expand **Periodic**, expand **Batch**, and then click **Processing**. This displays the form **Set up batch processing**.

2.  Click the drop-down list, and then select **Empty batch group**. Batch tasks in this group will be run.

3.  Make sure the check box labeled **Private** is clear.

4.  Click **OK** to start the **Batch processing** form.

## Related Topics

For more information about batch jobs and batch tasks, see the following topics:

  - "Processing batch jobs" in the Help menu item **Applications and Business Processes**

  - "Create a batch job" in the **Help** menu item **Application and Business Processes**

## See also

[Developing Applications Using the AOS](developing-applications-using-the-aos.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

