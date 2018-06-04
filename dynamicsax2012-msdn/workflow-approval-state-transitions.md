---
title: Workflow Approval State Transitions
TOCTitle: Workflow Approval State Transitions
ms:assetid: 8ffe2f62-76d7-48a7-b786-7cc41dffdb78
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc604518(v=AX.60)
ms:contentKeyID: 35247406
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Workflow Approval State Transitions 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Microsoft Dynamics AX workflow documents that are enabled for workflow approvals typically support at least five workflow states. The current workflow state of a workflow can be maintained in a table field associated with the workflow document. As the state of the document is changed, the state field in the table should be updated. This topic describes workflow approval states.

## Workflow State

Workflow state determines what you can do with the workflow document as soon as it is available in the system. Workflow states are defined by developers and must be supported in queries and business logic for operations that are controlled by workflow. Workflow approvals typically use the following workflow states.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Workflow state</p></th>
<th><p>Use</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>NotSubmitted</p></td>
<td><p>The state of the document before it is submitted to workflow or if the workflow is canceled. This is the state of all documents before a workflow instance is instantiated for the document.</p></td>
</tr>
<tr class="even">
<td><p>Submitted</p></td>
<td><p>The state of the document as soon as the workflow is activated and the document is submitted to workflow. This is a temporary state when the user activates a workflow, but the system has not yet processed the workflow for activation. For more information, see <a href="how-to-activate-a-workflow-from-a-workflow-type.md">How to: Activate a Workflow from a Workflow Type</a>.</p></td>
</tr>
<tr class="odd">
<td><p>PendingApproval</p></td>
<td><p>The state of the document as soon as the approval starts and remains in this state until the approval is completed, returned for a change, or rejected.</p></td>
</tr>
<tr class="even">
<td><p>ChangeRequested</p></td>
<td><p>The state of the document if a change is requested or the document is returned.</p></td>
</tr>
<tr class="odd">
<td><p>Approved</p></td>
<td><p>The state of the document when the approval is completed.</p></td>
</tr>
</tbody>
</table>


The following diagram illustrates a typical approval state transition model.

![Approval State Transition Model](images/Cc604518.AXApprovalStateTransitionsModel(en-us,AX.60).gif "Approval State Transition Model")

Here are some general guidelines for workflow state:

  - Avoid creating your own workflow states unless you have a business justification for doing this.

  - Consider refactoring existing approval states so that you can take advantage of the states listed here.

## See also

[Walkthrough: Adding Workflow to an Existing Form](walkthrough-adding-workflow-to-an-existing-form.md)

[Requirements for Enabling Workflow in an Application Module](requirements-for-enabling-workflow-in-an-application-module.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

