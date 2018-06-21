---
title: 'Walkthrough: Adding Workflow to an Existing Form'
TOCTitle: 'Walkthrough: Adding Workflow to an Existing Form'
ms:assetid: e9e14877-c8fe-4b4b-8820-4b7397729404
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc653399(v=AX.60)
ms:contentKeyID: 35253231
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Walkthrough: Adding Workflow to an Existing Form 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

In Microsoft Dynamics AX, you can add workflow to new or existing forms. In this walkthrough, you will:

  - Enable and add workflow to the **CustTable** form.

  - Create a method that indicates whether the current document can be submitted to workflow.

  - Create a configuration to test the workflow.

To add workflow to a form, you must have a workflow type that identifies the data fields that the workflow uses. This walkthrough builds on the [Walkthrough: Creating a Workflow Type](walkthrough-creating-a-workflow-type.md).

## Prerequisites

To complete this walkthrough, you will need:

  - Microsoft Dynamics AX

  - A license file that has access to the Development workspace.

  - To complete the steps in [Walkthrough: Creating a Workflow Type](walkthrough-creating-a-workflow-type.md).

### To Enable a Form for Workflow

1.  In the AOT, expand the **Forms** node.

2.  Expand the **CustTable** form, and then expand the **Designs** node.

3.  In the **Designs** node, right-click the **Design** child node, and then click **Properties**.

4.  In the **Properties** sheet, set the following properties.
    
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
    <td><p><strong>WorkflowEnabled</strong></p></td>
    <td><p><strong>Yes</strong></p></td>
    </tr>
    <tr class="even">
    <td><p><strong>WorkflowDataSource</strong></p></td>
    <td><p><strong>CustTable</strong></p>
    > [!note]  
    > <P>This is the root data source specified in the query used for the <strong>Document</strong> property on the <strong>MyWorkfowType</strong> type. For more information, see <a href="walkthrough-creating-a-workflow-type.md">Walkthrough: Creating a Workflow Type</a>.</P>
    </td>
    </tr>
    <tr class="odd">
    <td><p><strong>WorkflowType</strong></p></td>
    <td><p><strong>MyWorkflowType</strong></p></td>
    </tr>
    </tbody>
    </table>


5.  In the AOT, right-click the **CustTable** form, and then click **Save**.

After the form is enabled for workflow, you will add a canSubmitToWorkflow method to the form. This method runs before the **Submit** button is enabled to verify that the workflow document is in a valid state to submit to workflow. When this method returns true, the **Submit** button is enabled. An alternative is to add the canSubmitToWorkflow method to the main table for the form. This allows both the Microsoft Dynamics AX client and Enterprise Portal to share the same logic to determine whether workflow is enabled.


> [!NOTE]
> <P>If there are no records in the data source and the canSubmitToWorkflow method returns true, an exception is thrown. Therefore, you should programatically check for a record when you evaluate the state of the workflow.</P>



### To Create a Method to Indicate Whether the Current Document can be Submitted to Workflow

1.  In the AOT, expand the **CustTable** form, right-click the **Methods** node and then point to **Override method**. Click canSubmitToWorkflow.

2.  A method node named canSubmitToWorkflow displays under the **Methods** node and the **Editor** window opens.

3.  In the **Editor** window, enter the following code to enable the **Submit** button on the form for workflow.
    
        public boolean canSubmitToWorkflow()
        {
            // ToDo This method always returns true and the Submit
            // button will always be displayed on the form. Enter code
            // here to only return true when the document is NotSubmitted.
            // Also, add code to check if a record exists in the data source.
            return true;
        }

4.  Close the **Editor** window and then click **Yes** to save changes.

Now that the form is enabled for workflow, you must create a workflow configuration to display the **Submit** button on the workflow toolbar.

### To Create a Configuration

1.  In Microsoft Dynamics AX, click **Accounts receivable** \> **Setup** \> **Accounts receivable workflows**. The **Accounts receivable workflows** list is displayed.

2.  In the **Accounts receivable workflows** list, click **New**. The **Create workflow** form is displayed.

3.  On the **Create workflow** form, select **MyWorkflowType**, and then click **Create workflow**. The workflow configuration form is displayed.

4.  In the action pane, click **Properties**. The **Properties** form is displayed.

5.  In the **Properties** form, click **Basic Settings**. In the **Submission instructions** text box, enter My workflow submit instructions., and then click **Close**.

6.  In the **MyWorkflowType** form, create a simple workflow by dragging a **Conditional decision** onto the workflow in between the **Start** and **End** nodes. Drag a line from the **Start** node to the **Conditional decision 1** node. Then, drag a line from the **True** output of the **Conditional Decision 1** node to the **End** node. Finally, drag a line from the **False** output of the **Conditional decision 1** node to the **End** node.
    

    > [!TIP]
    > <P>You may need to scroll down in the workflow designer form to see the <STRONG>End</STRONG> node.</P>



7.  Right-click **Conditional decision 1**, and select **Properties**. The **Properties** form opens.

8.  In the **Conditional** tab, click **Add condition**, and then enter **Where Customers.Account number contains value 0**.

9.  Click **Close**.

10. In the workflow designer form, click **Save and close**. Enter Workflow Walkthrough in the **Version notes** field and click OK.

11. The **Activate workflow – MyWorkflowType** form appears. In the **Activate workflow – MyWorkflowType** form, select **Activate the new version**, and then click **OK**.

12. Display the **Accounts receivable** area page.

13. Click **Customers** \> **All customers**.

14. Double-click one of the customers in the list. The **Customers** form is displayed.

15. The workflow toolbar is displayed at the top of the **CustTable** form. Click the **View Workflow Instructions** icon on the workflow toolbar to display the submission instructions that you created in this walkthrough.

16. Click **MyWorkflowTypeSubmitMenuItem**, which is the menu item that you created to submit the customer to workflow. Supply a submission comment and then click **MyWorkflowTypeSubmitMenuItem** to see the submitted to workflow **Infolog** message.

## Next Steps

After you complete [Walkthrough: Creating a Workflow Type](walkthrough-creating-a-workflow-type.md) and [Walkthrough: Adding Workflow to an Existing Form](walkthrough-adding-workflow-to-an-existing-form.md), you have the foundation for a basic workflow. Now you can add tasks, automated tasks, and approvals to the workflow. For more information, see [Walkthrough: Creating a Workflow with a Task and an Approval](walkthrough-creating-a-workflow-with-a-task-and-an-approval.md).

## See also

[Walkthrough: Creating a Workflow Type](walkthrough-creating-a-workflow-type.md)

[Walkthrough: Creating a Workflow with a Task and an Approval](walkthrough-creating-a-workflow-with-a-task-and-an-approval.md)

[Walkthrough: Adding an Automated Task to a Workflow](walkthrough-adding-an-automated-task-to-a-workflow.md)

[Requirements for Enabling Workflow in an Application Module](requirements-for-enabling-workflow-in-an-application-module.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

