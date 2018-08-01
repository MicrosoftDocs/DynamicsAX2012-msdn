---
title: Customizing the Resource Scheduling Engine
TOCTitle: Customizing the Resource Scheduling Engine
ms:assetid: a2061b36-089f-4922-9684-bd26c2afb123
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh830901(v=AX.60)
ms:contentKeyID: 45260821
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Customizing the Resource Scheduling Engine [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

You use resource scheduling to plan production orders, based on resources and their capabilities and when those resources are available. Resource scheduling in Microsoft Dynamics AX consists of two parts:

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Pre- and post-processing code</p></td>
<td><p>This is X++ code that is used for interfacing Microsoft Dynamics AX with the resource scheduling engine. The scheduling engine code is contained in a Microsoft .NET assembly.</p></td>
</tr>
<tr class="even">
<td><p>The scheduling engine</p></td>
<td><p>A C# assembly that provides a defined interface for resource scheduling. For information about the classes, structures, interfaces, and enumerations in the assembly, see <a href="http://msdn.microsoft.com/en-us/library/microsoft.dynamics.ax.planning.jobscheduling.aspx">Microsoft.Dynamics.AX.Planning.JobScheduling Namespace</a>.</p></td>
</tr>
</tbody>
</table>


The scheduling engine uses resource groups that contain resources and capabilities for job and operations scheduling. The scheduling engine is responsible for making the actual resource selections and allocations. To allocate resources, the scheduling engine uses input from the X++ preprocessing code. The preprocessing code supplies the engine with the activities and constraints that are required to complete the operation. Those activities and constraints are provided as one or more jobs.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Term</p></th>
<th><p>Definition</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Job</p></td>
<td><p>An occurrence of an activity performed between specific start and end times and at specific locations.</p></td>
</tr>
<tr class="even">
<td><p>Activity</p></td>
<td><p>A functional work structure in which one or more persons and pieces of equipment participate and in which resources are consumed, produced, and used.</p></td>
</tr>
<tr class="odd">
<td><p>Resource</p></td>
<td><p>Anything that is used for the creation, production or delivery of a good or service beyond the materials consumed in the process. These can be of type tool, machine, human resource, location or vendor.</p></td>
</tr>
</tbody>
</table>


## Fixed Lead Time

To customize the scheduling engine, you change the X++ pre-processing code and, if necessary, extend the C\# code that is contained in the resource scheduling assembly. By extending the engine code, you do not need to directly change the C\# scheduling engine assemblies that are shipped with Microsoft Dynamics AX. For example, to implement a fixed lead time constraint – which is the amount of time necessary to fill an order – you make changes to both the X++ pre-processing code and extend the C\# scheduling engine. For more information on this, see [Walkthrough: Adding Fixed Lead Time to a Resource Schedule](walkthrough-adding-fixed-lead-time-to-a-resource-schedule.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

