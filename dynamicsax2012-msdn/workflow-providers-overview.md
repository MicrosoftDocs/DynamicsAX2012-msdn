---
title: Workflow Providers Overview
TOCTitle: Workflow Providers Overview
ms:assetid: 0ec16425-6498-467a-9323-20494e98d863
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc519521(v=AX.60)
ms:contentKeyID: 35240488
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Workflow Providers Overview [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

In Microsoft Dynamics AX, you can use workflow providers to provide application-specific information to a workflow instance at runtime. For example, you can use workflow providers to determine who is required to approve an invoice, or by which date an invoice payment is considered to be late. This topic describes the default providers available in Microsoft Dynamics AX.

In a Microsoft Dynamics AX workflow, there are four types of workflow providers that are available. The following table describes the workflow providers.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Provider type</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Hierarchy Assignment</p></td>
<td><p>Determines a user ID based on a search in a hierarchy.</p></td>
</tr>
<tr class="even">
<td><p>Due Date Calculation</p></td>
<td><p>Determines the due date for a task or approval, or the due date for a step in a task or approval.</p></td>
</tr>
<tr class="odd">
<td><p>Participant Assignment</p></td>
<td><p>Resolves a logical role into one or more user IDs. For example, this provider is used to resolve a Microsoft Dynamics AX security role into the users assigned to that role.</p></td>
</tr>
<tr class="even">
<td><p>Queue Assignment</p></td>
<td><p>Directs a work item to an appropriate queue.</p></td>
</tr>
</tbody>
</table>


Workflow provider types are defined in the **Workflow** \> **Providers** node of the AOT. Each provider type has one or more instances that are defined for it. Some of the workflow provider instances are global and available for use by any workflow. Other workflow provider instances are available only for the workflow types that are assigned to them.

You can create an instance of a workflow provider, customize that instance, and make it available to all workflow types, or to specific workflow types. See [How to: Create a Custom Workflow Provider](how-to-create-a-custom-workflow-provider.md) for more information. Each workflow provider instance has a provider class that defines how the provider works. Each provider type has an interface that the provider class must implement. You control the behavior of the workflow provider instance by how you implement the methods for the interface. See [Workflow Provider Interfaces](workflow-provider-interfaces.md) for more information about each interface.

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

