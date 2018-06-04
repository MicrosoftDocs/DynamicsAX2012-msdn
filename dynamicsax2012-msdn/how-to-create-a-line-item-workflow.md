---
title: 'How to: Create a Line-item Workflow'
TOCTitle: 'How to: Create a Line-item Workflow'
ms:assetid: 15e45dd8-e49c-4cca-916b-42eeb53deae5
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh528502(v=AX.60)
ms:contentKeyID: 37835250
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Create a Line-item Workflow 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

This procedure describes how to create a line-item workflow in the Application Object Tree (AOT). A line-item workflow is used together with a standard workflow type that was created in the AOT.

### To create a line-item workflow

1.  If it does not already exist, create the workflow type for the base document.

2.  Create a workflow type for the line item document. Use the same techniques that are described in [Creating a Workflow Type](creating-a-workflow-type.md).

3.  In the AOT, expand the **Workflow** \> **Workflow Types** node. Locate the workflow type for the base document.

4.  Expand the node for the base document workflow type.

5.  Right-click the **Line Item Workflow** node and then click **New Line Item Workflow**.

6.  Right-click the node for the new line item workflow and then click **Properties**.

7.  Set the properties for the line item workflow. The following table lists the available properties.
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Property</p></th>
    <th><p>Description</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Name</p></td>
    <td><p>The name for the line item workflow.</p></td>
    </tr>
    <tr class="even">
    <td><p>Label</p></td>
    <td><p>A descriptive name for the line item workflow.</p></td>
    </tr>
    <tr class="odd">
    <td><p>HelpText</p></td>
    <td><p>A description of the line item workflow.</p></td>
    </tr>
    <tr class="even">
    <td><p>LineItemWorkflowRelation</p></td>
    <td><p>Specifies the relation for the line item workflow.</p></td>
    </tr>
    <tr class="odd">
    <td><p>StartedEventHandler</p></td>
    <td><p>Specify the event handler class that you created for the Started event.</p></td>
    </tr>
    <tr class="even">
    <td><p>CompletedEventHandler</p></td>
    <td><p>Specify the event handler class that you created for the Completed event.</p></td>
    </tr>
    <tr class="odd">
    <td><p>CanceledEventHandler</p></td>
    <td><p>Specify the event handler class that you created for the Canceled event.</p></td>
    </tr>
    <tr class="even">
    <td><p>RecallMenuItem</p></td>
    <td><p>The menu item for the recall action, if it is used for the line item workflow.</p></td>
    </tr>
    <tr class="odd">
    <td><p>RecallWebMenuItem</p></td>
    <td><p>The web menu item for the recall action, if it is used for the line item workflow.</p></td>
    </tr>
    <tr class="even">
    <td><p>CancelMenuItem</p></td>
    <td><p>The menu item for the cancel action, if it is used for the line item workflow.</p></td>
    </tr>
    <tr class="odd">
    <td><p>CancelWebMenuItem</p></td>
    <td><p>The web menu item for the cancel action, if it is used for the line item workflow.</p></td>
    </tr>
    <tr class="even">
    <td><p>EnableLineItemWaitSelection</p></td>
    <td><p>Specifies whether the wait selection is enabled for the workflow editor.</p></td>
    </tr>
    </tbody>
    </table>


8.  Expand the node for the line item workflow.

9.  Right-click the **Line Item Workflow Types** node, and then click **New Line Item Workflow Type**.

10. For the new node, set the **LineItemWorkflowType** property to the name of the workflow type for the line item that you created in step 2.

11. Save the changes for the base workflow type.

The line item workflow will now be available as an element in the workflow editor when you set up a workflow for the base document.

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

