---
title: 'Walkthrough: Creating a Workflow with a Task and an Approval'
TOCTitle: 'Walkthrough: Creating a Workflow with a Task and an Approval'
ms:assetid: 2c570a06-01ec-45fd-9658-d28b040acb00
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc585944(v=AX.60)
ms:contentKeyID: 35241813
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Walkthrough: Creating a Workflow with a Task and an Approval [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

In Microsoft Dynamics AX, you can add tasks and approvals to a workflow that you defined in the AOT. In this walkthrough, you will create and add a task and an approval to the **MyWorkflowType** that was created for the **CustTable** form. This walkthrough builds on the [Walkthrough: Creating a Workflow Type](walkthrough-creating-a-workflow-type.md) and the [Walkthrough: Adding Workflow to an Existing Form](walkthrough-adding-workflow-to-an-existing-form.md).

This walkthrough illustrates the following tasks:

  - Create a workflow task.

  - Add a workflow task to a workflow type.

  - Create a workflow approval.

  - Configure the workflow approval outcomes.

  - Add a workflow approval to a workflow type.

  - Create a workflow configuration.

## Prerequisites

To complete this walkthrough, you will need:

  - Microsoft Dynamics AX

  - A license file that has access to the Development workspace.

  - To complete the steps in [Walkthrough: Creating a Workflow Type](walkthrough-creating-a-workflow-type.md).

  - To complete the steps in [Walkthrough: Adding Workflow to an Existing Form](walkthrough-adding-workflow-to-an-existing-form.md).

### To create a workflow task

1.  In the AOT, expand the **Workflow** node.

2.  Right-click the **Tasks** node, and then click **Add-Ins** \> **Task wizard**. The **Workflow wizard** is displayed. This wizard will help you create a new workflow task.

3.  Click **Next**.

4.  Set the following values for the wizard.
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Value</p></th>
    <th><p>Input</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><strong>Name</strong></p></td>
    <td><p>Enter MyWorkflowTask.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Workflow document</strong></p></td>
    <td><p>Choose MyWorkflowTypeDocument.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Document preview field group</strong></p></td>
    <td><p>Choose AutoSummary.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Document menu item</strong></p></td>
    <td><p>Choose CustTable.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Document web menu item</strong></p></td>
    <td><p>Choose EPCustTableInfo.</p></td>
    </tr>
    </tbody>
    </table>


5.  Click **Both** to generate menu items for both the Microsoft Dynamics AX client and Enterprise Portal.

6.  Click **Next**.

7.  Next, you will add the Complete outcome to the task. In the **Name** field, enter **MyTaskOutcomeComplete**. For the **Type**, choose **Complete**. Click **Add**.

8.  Now that the workflow task as at least one outcome, click **Next**. A list of all of the resources that will be created for the workflow task is displayed.

9.  Click **Finish** to create the resources. The wizard will create classes, menu items, web menu items, the task, and a project that contains all of the items.

10. A dialog box will be displayed that indicates the status. Click **OK**. The project that contains the workflow type resources is displayed.

After a workflow task with an outcome is created, you can add the workflow task to the **Supported Elements** node of a workflow type. For more information, see [Creating Workflow Tasks, Automated Tasks, and Approvals](creating-workflow-tasks-automated-tasks-and-approvals.md).

### To add a task to a workflow type

1.  Expand the **Workflow Types** node, and then expand the **MyWorkflowType** node.

2.  Within the **Workflow** node, expand the **Tasks** node. Drag the **MyWorkflowTask** node onto the **Supported Elements** node in the **MyWorkflowType** node.

3.  In the AOT, right-click **MyWorkflowType**, and then click **Save**.

Next, you will create a workflow approval with two outcomes and then add it to the workflow type.

### To create a workflow approval

1.  In the AOT, expand the **Workflow** node.

2.  Right-click the **Approvals** node, and then click **Add-Ins** \> **Approval wizard**. The **Workflow wizard** is displayed. This wizard will help you create a new workflow approval.

3.  Click **Next**.

4.  Set the following values for the wizard.
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Value</p></th>
    <th><p>Input</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><strong>Name</strong></p></td>
    <td><p>Enter MyWorkflowApproval.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Workflow document</strong></p></td>
    <td><p>Choose MyWorkflowTypeDocument.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Document preview field group</strong></p></td>
    <td><p>Choose AutoSummary.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Document menu item</strong></p></td>
    <td><p>Choose CustTable.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Document web menu item</strong></p></td>
    <td><p>Choose EPCustTableInfo.</p></td>
    </tr>
    </tbody>
    </table>


5.  Click **Both** to generate menu items for both the Microsoft Dynamics AX client and Enterprise Portal.

6.  Click **Next**. A list of all of the resources that will be created for the workflow approval is displayed.

7.  Click **Finish** to create the resources. The wizard will create classes, menu items, web menu items, the approval, and a project that contains all of the items.

8.  A dialog box will be displayed that indicates the status. Click **OK**. The project that contains the workflow type resources is displayed.

To simplify this walkthrough, only the **Approve** and **Deny** outcomes are enabled.

### To configure the approval outcomes

1.  Expand **MyWorkflowApproval**, and then expand **Outcomes**. Right-click the **Approve** outcome and then click **Properties**.

2.  In the **Properties** sheet, verify the following properties:
    
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
    <td><p><strong>Enabled</strong></p></td>
    <td><p>Yes</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>ActionMenuItem</strong></p></td>
    <td><p>MyWorkflowApprovalApprove</p></td>
    </tr>
    </tbody>
    </table>


3.  In the **Outcomes** node, right-click the **Deny** outcome, and then click **Properties**.

4.  In the **Properties** sheet, verify the following properties:
    
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
    <td><p><strong>Enabled</strong></p></td>
    <td><p>Yes</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>ActionMenuItem</strong></p></td>
    <td><p>MyWorkflowApprovalDeny</p></td>
    </tr>
    </tbody>
    </table>


5.  In the **Outcomes** node, set the **Enabled** property for **RequestChange** and **Reject** to **No**. By setting this property to No, the action buttons in the user interface for **Request Change** and **Return** will not be shown.

6.  In the AOT, right-click **MyWorkflowApproval**, and then click **Save**.

After a workflow approval with outcomes is created, you can add the approval to the **Supported Elements** node of a workflow type. For more information, see [Creating Workflow Tasks, Automated Tasks, and Approvals](creating-workflow-tasks-automated-tasks-and-approvals.md).

### To add an approval to a workflow type

1.  Expand the **Workflow Types** node, and then expand the **MyWorkflowType** node.

2.  Within the **Workflow** node, expand the **Approvals** node. Drag the **MyWorkflowApproval** node onto the **Supported Elements** node of the **MyWorkflowType** node.

3.  In the AOT, right-click **MyWorkflowType**, and then click **Save**.

To view the approval and the task in the configuration user interface, you must create a new configuration.


> [!NOTE]
> <P>To update metadata changes in the client, you must close and restart Microsoft Dynamics AX before continuing.</P>



### To create a configuration

1.  In Microsoft Dynamics AX, click **Accounts receivable** \> **Setup** \> **Accounts receivable workflows**. The **Accounts receivable workflows** list is displayed.

2.  In the **Accounts receivable workflows** list, click **New**. The **Create workflow** form is displayed.

3.  On the **Create workflow** form, select **MyWorkflowType**, and then click **Create workflow**. The workflow configuration form is displayed.

4.  In the action pane, click **Properties**. The **Properties** form is displayed.

5.  In the **Properties** form, click **Basic Settings**. In the **Submission instructions** text box, enter My workflow submit instructions., and then click **Close**.

6.  In the workflow configuration window, drag a **MyWorkflowTask** task from the **Workflow elements** onto the workflow in between the **Start** and **End** nodes.

7.  Right-click the **MyWorkflowTaskTask 1** node, and select **Properties**. The **Properties** form opens.

8.  In the **Work item subject** textbox of the **Basic Settings** pane, enter My subject..

9.  In the **Work item instructions** textbox of the **Basic Settings** pane, enter My workflow instructions..

10. In the **Assignment type** tab of the **Assignment** pane, select **Workflow user**. Then, from the **Workflow user** tab, select **Work item owner**.

11. Click **Close** to exit the **Properties** form.

12. In the workflow configuration window, drag a **MyWorkflowApproval** approval from the **Workflow elements** onto the workflow in between the **Start** and **End** nodes.

13. Double-click the **MyWorkflowApprovalApproval 1** node. Then, right-click on **Step 1** and select **Properties**. The **Properties** window opens.

14. Repeat steps 8 – 11.

15. In the workflow breadcrumb bar, click **Workflow** to go to the top level of the workflow.

16. In the **Workflow Editor**, drag a line from **Start** to **MyWorkflowTaskTask 1**. Then, drag a line from **MyWorkflowTaskTask 1** to **MyWorkflowApprovalApproval 1**. Finally, drag a line from **MyWorkflowApprovalApproval 1** to **End**.

17. Click **Save and close** to exit the workflow designer form. Enter Workflow Walkthrough in the **Version notes** field and click OK.

18. The **Activate workflow – MyWorkflowType** dialog appears. In the **Activate workflow – MyWorkflowType** dialog, select **Activate the new version** and click **OK**.

19. In the **Accounts receivable workflows** list, select the **MyWorkflowTemplate** configuration that you just created, and then click **Set as default** to use this workflow configuration as the default workflow configuration.

20. Display the **Accounts receivable** area page.

21. Click **Customers** \> **All customers**.

22. Double-click one of the customers in the list. The **Customers** form is displayed.

23. The workflow toolbar is displayed at the top of the **CustTable** form.
    

    > [!NOTE]
    > <P>Since the canSubmitToWorkflow method on the <STRONG>CustTable</STRONG> form always returns true, the workflow toolbar and the <STRONG>Submit</STRONG> button are always displayed. You can test the remaining sections of this workflow after the workflow is submitted and processed by changing the canSubmitToWorkflow method to always return false.</P>



## Next Steps

After you complete [Walkthrough: Creating a Workflow Type](walkthrough-creating-a-workflow-type.md), [Walkthrough: Adding Workflow to an Existing Form](walkthrough-adding-workflow-to-an-existing-form.md), and [Walkthrough: Creating a Workflow with a Task and an Approval](walkthrough-creating-a-workflow-with-a-task-and-an-approval.md), you have the foundation for a basic workflow. Now you can add automated tasks to the workflow. For more information, see [Walkthrough: Adding an Automated Task to a Workflow](walkthrough-adding-an-automated-task-to-a-workflow.md).

You can simulate server data flow for the workflow process by using the **Tutorial\_WorkflowProcessor** form located in the **Forms** node in the AOT.

## See also

[Walkthrough: Creating a Workflow Type](walkthrough-creating-a-workflow-type.md)

[Walkthrough: Adding Workflow to an Existing Form](walkthrough-adding-workflow-to-an-existing-form.md)

[Walkthrough: Adding an Automated Task to a Workflow](walkthrough-adding-an-automated-task-to-a-workflow.md)

[Requirements for Enabling Workflow in an Application Module](requirements-for-enabling-workflow-in-an-application-module.md)

[Creating Workflow Tasks, Automated Tasks, and Approvals](creating-workflow-tasks-automated-tasks-and-approvals.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

