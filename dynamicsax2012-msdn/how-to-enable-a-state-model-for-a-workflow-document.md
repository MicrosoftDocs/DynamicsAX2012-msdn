---
title: 'How to: Enable a State Model for a Workflow Document'
TOCTitle: 'How to: Enable a State Model for a Workflow Document'
ms:assetid: 6f02ef6a-5f0c-47db-af7e-a9c4da78c517
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc592907(v=AX.60)
ms:contentKeyID: 35244850
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Enable a State Model for a Workflow Document 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Workflow documents in a Microsoft Dynamics AX workflow must implement a state model to represent the state of a workflow, approval, or task for a workflow document in the application. For example, a workflow document in the NotSubmitted state can be changed to the Submitted state when a user clicks the **Submit** button. This section describes how to enable the state model for a workflow document by using a class or by creating a method on a table.

The following table contains recommended states. However, the needs of your application will determine what states are needed, validation type for state transitions, and how many states are needed. For more information, see [Workflow Approval State Transitions](workflow-approval-state-transitions.md).

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>For the state of the</p></th>
<th><p>Use</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Workflow document</p></td>
<td><ul>
<li><p>NotSubmitted</p></li>
<li><p>Submitted</p></li>
<li><p>ChangeRequested</p></li>
<li><p>Returned</p></li>
<li><p>Completed</p></li>
</ul></td>
</tr>
</tbody>
</table>


Typically, the workflow state should be persisted in the root table of your workflow document data source. To add workflow state to a table, create an enum in the **BaseEnums** node of the Application Object Tree (AOT) that contains the workflow states shown in the previous table. The first enum defined should be the NotSubmitted enum, and this will also be the default setting in the table. After the enum is defined, drag the enum to the **Fields** node of the workflow document data source table. For more information, see [Enums](enums.md).

After a state model is defined, you can enable forms and lists to work with workflow. For more information, see [How to: Enable a Form or List for Workflow](how-to-enable-a-form-or-list-for-workflow.md).


> [!NOTE]
> <P>Workflow state can be implemented in many ways. The following procedure shows one way of performing this task.</P>



### To create a state change manager class

1.  In the AOT, expand the **Classes** node.

2.  Right-click the **Classes** node, and then select **New Class**. A class group displays under the **Classes** node.

3.  Right-click the new class, click **Rename**, and then enter a name for the class.

4.  Right-click the new class and then click **New Method**. A method node named **method1** displays under the **Classes** node.

5.  Right-click **method1** and then click **Edit**. Enter the following code for the started event method.
    ```X++  
        public static void started(RecID _recID)
        {
            <insert method here>
        }
    ```
6.  Repeat steps 4 and 5 for the remaining states.

## Example

The following code is part of the setWorkflowState on the [PurchReqTable Table](https://msdn.microsoft.com/en-us/library/gg926866\(v=ax.60\)). This method sets the workflow state field in the table and updates the user interface with a user friendly status, and then updates the state in the database.
```X++  
    static void setWorkflowState(RecId _purchReqRecId, PurchReqWorkflowState _purchReqWorkflowState)
    {
        // Declare variables.
        PurchReqTable purchReqTable;
    
        ttsbegin;
     
        // Selects the record to be updated based on the recId and then
        // sets the workflow state. 
        purchReqTable = PurchReqTable::findRecId(_purchReqRecId, true);
        purchReqTable.State = _purchReqWorkflowState;
    
        // Based on the workflow state, the status in the user interface
        // is updated with a user friendly status.
        switch (_purchReqWorkflowState)
        {
            case PurchReqWorkflowState::Submitted:
                purchReqTable.Status = PurchReqStatus::Submitted;
                break;
            case PurchReqWorkflowState::NotSubmitted:
                purchReqTable.Status = PurchReqStatus::Draft;
                break;
            case PurchReqWorkflowState::Completed:
                purchReqTable.Status = PurchReqStatus::Completed;
                break;
            case PurchReqWorkflowState::Returned:
                purchReqTable.Status = PurchReqStatus::Rejected;
                break;
            case PurchReqWorkflowState::ChangeRequest:
                purchReqTable.Status = PurchReqStatus::ChangeRequested;
                break;
        }
     
        // Commits the state to the database. 
        purchReqTable.update();
     
        ttscommit;
    }
```
## See also

[Requirements for Enabling Workflow in an Application Module](requirements-for-enabling-workflow-in-an-application-module.md)

[How to: Enable a Form or List for Workflow](how-to-enable-a-form-or-list-for-workflow.md)

[Workflow Approval State Transitions](workflow-approval-state-transitions.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

