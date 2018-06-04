---
title: 'Walkthrough: Adding an Automated Task to a Workflow'
TOCTitle: 'Walkthrough: Adding an Automated Task to a Workflow'
ms:assetid: 81e9a94a-7328-4fce-9db6-487e343cfeb8
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg862506(v=AX.60)
ms:contentKeyID: 35246147
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Walkthrough: Adding an Automated Task to a Workflow 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

In Microsoft Dynamics AX, you can add automated tasks to a workflow in the Application Object Tree (AOT). In this walkthrough, you will create and add an automated task to the **MyWorkflowType** based on the **CustTable** form. This walkthrough builds on the [Walkthrough: Creating a Workflow Type](walkthrough-creating-a-workflow-type.md), the [Walkthrough: Adding Workflow to an Existing Form](walkthrough-adding-workflow-to-an-existing-form.md), and the [Walkthrough: Creating a Workflow with a Task and an Approval](walkthrough-creating-a-workflow-with-a-task-and-an-approval.md).

This walkthrough illustrates the following tasks:

  - Creating an automated task.

  - Writing code that is run when the automated task is executed.

  - Configuring a workflow on the client to run the automated task.

## Prerequisites

To complete this walkthrough, you will need:

  - Microsoft Dynamics AX

  - A license file that has access to the MorphX development environment.

  - To complete the steps in [Walkthrough: Creating a Workflow Type](walkthrough-creating-a-workflow-type.md).

  - To complete the steps in [Walkthrough: Adding Workflow to an Existing Form](walkthrough-adding-workflow-to-an-existing-form.md).

  - To complete the steps in [Walkthrough: Creating a Workflow with a Task and an Approval](walkthrough-creating-a-workflow-with-a-task-and-an-approval.md).

### To Create an Automated Task

1.  In the AOT, expand the **Workflow** node.

2.  Right-click the **Automated Tasks** node and then select **New Automated Task**. A new workflow automated task group displays under the **Automated Tasks** node.

3.  Right-click the new workflow automated task and then click **Properties**.

4.  In the **Properties** sheet, set the following properties:
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Property</p></th>
    <th><p>Value</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><strong>Name</strong></p></td>
    <td><p>MyWorkflowAutomatedTask</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Label</strong></p></td>
    <td><p>MyWorkflowAutomatedTask</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Document</strong></p></td>
    <td><p>MyWorkflowDocumentClass</p>
    <div class="mtps-table">
    <div class="mtps-row">
    <img src="images/Aa589339.alert_note(en-us,AX.60).gif" title="Note" alt="Note" class="note" /><strong>Note</strong>
    </div>
    <div class="mtps-row">
    This value is available only if you complete <a href="walkthrough-creating-a-workflow-type.md">Walkthrough: Creating a Workflow Type</a>.
    </div>
    </div></td>
    </tr>
    </tbody>
    </table>


5.  In the AOT, right-click **MyWorkflowAutomatedTask**, and then click **Save**.

### To Create a Class To Handle Automated Task Events

1.  In the AOT, right-click **Classes** and select **New Class**. A new class displays under the **Classes** node.

2.  Right-click the newly created class and select **Properties**.

3.  In the **Properties** sheet, set **Name** to MyWorkflowAutomatedTaskEventHandler.

4.  Expand the **MyWorkflowAutomatedTaskEventHandler** class. Double-click the **classDeclaration** node. The **Code Editor** opens.

5.  Type the following code into the **Code Editor**:
    
        class MyWorkflowAutomatedTaskEventHandler implements WorkflowElementExecutionEventHandler
        {
        }
    

    > [!WARNING]
    > <P>You can also implement the WorkflowElementCanceledEventHandler event handler, but it is not required.</P>



6.  In the AOT, right-click **MyWorkflowAutomatedTaskEventHandler** and select **New Method**. A new method appears under the class.

7.  Double-click the new method. The **Code Editor** opens.

8.  Type the following code in the **Code Editor**:
    
        public void execute(WorkflowElementEventArgs _workflowElementEventArgs)
        {
            // This is the variable declaration.
            WorkflowContext workflowContext;
            ;
        
            // Gets the workflow context from _workflowElementEventArgs.
            workflowContext = _workflowElementEventArgs.parmWorkflowContext();
        }

9.  In the **Code Editor**, press the **Save** button. You can now close the **Code Editor**.

10. You now need to update the automated task to set the **ExecutionEventHandler** property to the class that you just created. In the AOT, expand the **Workflow** node, and then expand the **Automated Tasks** node. Right-click **MyWorkflowAutomatedTask** and select **Properties**.

11. In the **Properties** sheet, set the **ExecutionEventHandler** property to **MyWorkflowAutomatedTaskEventHandler**.

12. Right-click the **MyWorkflowAutomatedTask** node and select **Save**.

13. To compile your application, in the AOT, right-click **AOT**, select **Add-Ins**, and then select **Incremental CIL generation from X++**.

## Next Steps

You can expand this walkthrough by adding a **CanceledEventHandler** to the automated task. For more information, see [How to: Create a Workflow Task or Approval Event Handler](how-to-create-a-workflow-task-or-approval-event-handler.md).

## See also

[Walkthrough: Creating a Workflow Type](walkthrough-creating-a-workflow-type.md)

[Walkthrough: Adding Workflow to an Existing Form](walkthrough-adding-workflow-to-an-existing-form.md)

[Walkthrough: Creating a Workflow with a Task and an Approval](walkthrough-creating-a-workflow-with-a-task-and-an-approval.md)

[Requirements for Enabling Workflow in an Application Module](requirements-for-enabling-workflow-in-an-application-module.md)

[Creating Workflow Tasks, Automated Tasks, and Approvals](creating-workflow-tasks-automated-tasks-and-approvals.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

