---
title: 'How to: Enable a Form or List for Workflow'
TOCTitle: 'How to: Enable a Form or List for Workflow'
ms:assetid: 8859306a-f5e2-4027-a18b-f2eda00a97b8
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc602813(v=AX.60)
ms:contentKeyID: 35246232
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Enable a Form or List for Workflow [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

In Microsoft Dynamics AX, each form or list that is to be used by workflow must be enabled for workflow. This topic describes the steps to enable a form for workflow. It also describes the steps to enable a list for workflow.

When a form is enabled for workflow, the workflow menu bar is automatically inserted at the top of the form, below the form title bar or action pane. The workflow menu bar provides everything that you must have to interact with a workflow. The menu bar contains workflow action buttons, such as **Submit** and **Complete**, and data fields that contain workflow instructions, configuration name, and information icons.

To display the **Submit** button, the form must have a canSubmitToWorkflow method.


> [!NOTE]
> <P>The form data source, or table, must contain a field for the workflow state of the document. For example, a field that contains the workflow state NotSubmitted should be updated to Submitted when the user clicks the <STRONG>Submit</STRONG> button on the form. For more information, see <A href="workflow-approval-state-transitions.md">Workflow Approval State Transitions</A> and <A href="how-to-enable-a-state-model-for-a-workflow-document.md">How to: Enable a State Model for a Workflow Document</A>.</P>



### To enable a form for workflow

1.  In the Application Object Tree (AOT), expand the **Forms** node.

2.  Expand the form that you want to enable for workflow, and then expand the **Designs** node.

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
    <td><p>Set to Yes to enable the workflow menu bar on the form. The default setting is No.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>WorkflowDataSource</strong></p></td>
    <td><p>Set to the same root data source specified in the query used for the <strong>Document</strong> property on the workflow type. For more information, see <a href="how-to-create-a-workflow-document-class.md">How to: Create a Workflow Document Class</a>.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>WorkflowType</strong></p></td>
    <td><p>Set to the workflow type that you want to use for the list.</p></td>
    </tr>
    </tbody>
    </table>


5.  In the AOT, right-click the form, and then click **Save**.

### To enable a list for workflow

1.  In the Application Object Tree (AOT), expand the **Forms** node.

2.  Expand the form for the list that you want to enable for workflow, and then expand the **Designs** node.

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
    <td><p>Set to Yes to enable the workflow for the list. The default setting is No.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>WorkflowDataSource</strong></p></td>
    <td><p>Set to the same root data source specified in the query used for the <strong>Document</strong> property on the workflow type. For more information, see <a href="how-to-create-a-workflow-document-class.md">How to: Create a Workflow Document Class</a>.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>WorkflowType</strong></p></td>
    <td><p>Set to the workflow type that you want to use for the list.</p></td>
    </tr>
    </tbody>
    </table>


5.  In the AOT, right-click the form, and then click **Save**.

## See also

[Requirements for Enabling Workflow in an Application Module](requirements-for-enabling-workflow-in-an-application-module.md)

[How to: Enable a State Model for a Workflow Document](how-to-enable-a-state-model-for-a-workflow-document.md)

[Workflow Approval State Transitions](workflow-approval-state-transitions.md)

[How to: Create a Workflow Document Class](how-to-create-a-workflow-document-class.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

