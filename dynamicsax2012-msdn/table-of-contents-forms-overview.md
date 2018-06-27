---
title: Table of Contents Forms Overview
TOCTitle: Table of Contents Forms Overview
ms:assetid: 41d00a79-30d1-4943-a141-2ea0631521a0
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh745332(v=AX.60)
ms:contentKeyID: 42607683
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Table of Contents Forms Overview 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The table of contents form has a vertical list of tabs that appear along the left side of the form. When you click a tab, the fields and other information associated with that tab appear on the right side of the form. You use table of contents forms to quickly view, update, or create records associated with a series of related tasks.

## Table of Contents Form Basics

You use the table of contents design pattern when you want to display a series of related tasks or forms. You should use a table of contents form when you encounter the following conditions:

  - You need two or more forms to complete a specified operation.

  - Your operation requires that you complete a series of logically related tasks.

  - You want to quickly and efficiently move between tasks.

Typically, you use a table of contents form for setup or configuration operations. These types of operations include several related tasks, each task requires that you update several fields, and the tasks are often completed in sequence.

## Table of Contents Form Design

A table of contents form has two sections:

  - A list section that shows tasks. The list section is called the table of contents pane. Each entry in the list is called a vertical tab.

  - A details section that shows the instructions and fields associated with a task. The details section is called the content pane. The information in the content pane changes when you click a vertical tab in the list.

The following illustration shows the components of a table of contents form.

![Table of Contents form design elements](images/Hh745332.Client_TOCFormDesign(en-us,AX.60).png "Table of Contents form design elements")

The vertical tabs in the table of contents pane represent specific tasks in a setup or configuration operation. To populate the list, you add tab pages that supply a one or two word label that describes the task. You should arrange the list of vertical tabs to follow the sequence of tasks you use to complete the operation. When you open the form, the first vertical tab in the list is selected. For example, you use **Accounts receivable parameters** form found in the **Setup** section of the **Account Receivable** area page to specify parameters for the account receivable module. Notice how the form includes a vertical tab for each setup task. When you first view the form, the **General** tab is selected and appears in the content pane.


> [!NOTE]
> <P>If you have a vertical tab that configures a number sequence, put that vertical tab at the bottom of the list. If you have a vertical tab that configures inventory dimensions, put that vertical tab at the bottom or just above the number sequence tab. For example, the <STRONG>Account receivable parameters</STRONG> form includes vertical tabs for both the <STRONG>Inventory dimensions</STRONG> and <STRONG>Number sequence</STRONG>. Notice how the <STRONG>Inventory dimensions</STRONG> tab appears before the <STRONG>Number sequence</STRONG> tab at the bottom of the vertical tab list.</P>



The content pane contains the detail information for a specific task. The information in the content pane changes every time that you click a vertical tab in the list section. The content pane includes two sections:

  - An instruction group that supplies guidance about the task and how to use the information that appears in the content pane.

  - A details group that shows fields and other information that you use to perform the specified task.

Notice that a table of contents form does not have an action pane or action pane strip that appears across the top of the form.


> [!TIP]
> <P>To include actions on table of contents form, you should add an action pane strip to the details group of the content pane.</P>



The form includes a title that displays across the top of the window. If you open the form from an area page, the title should use the same text as the label of the command you use to open the form. For more design guidelines for the table of contents form, see [Table of Contents User Experience Guidelines](table-of-contents-user-experience-guidelines.md).

### ![Hh745332.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Hh745332.collapse_all(en-us,AX.60).gif")Template

To create a new form, you use the **TableOfContents** template. The template populates the **Style** property in the **Design** node and adds several controls that are required for the specified design pattern. In addition, the template configures many property values for you so that you can focus on adding fields and controls to the form. For information about how to use the template, see [How to: Create a Table of Contents form](how-to-create-a-table-of-contents-form.md).

### ![Hh745332.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Hh745332.collapse_all(en-us,AX.60).gif")Data Sources

To populate the tab pages of a table of contents form, you add one or more tables to the **Data Sources** node of the form. The tables contain the records and fields that appear in the content pane of the form. For more information about how to add a data source to a form, see [How to: Add a Data Source to a Details Form](how-to-add-a-data-source-to-a-details-form.md).

### ![Hh745332.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Hh745332.collapse_all(en-us,AX.60).gif")Table of Contents Pane

The table of contents pane shows a list of vertical tabs. Each label in the list provides a one or two word description of a task. You access the contents of a vertical tab by clicking the label. When you click a label, a tab page opens in the content pane of the form.

To use vertical tabs, you add a single tab control to the **Design** node of the form. You set the **Style** property of that tab control to **VerticalTabs**. Each vertical tab represents a tab page under that tab control. You use the **Caption** properties of the tab page controls to specify the labels that appear in the table of contents pane.

### ![Hh745332.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Hh745332.collapse_all(en-us,AX.60).gif")Task Instruction

The task instruction group provides one or two lines of text that help you complete the selected task. The task instructions will appear at the top of the content pane. The task instruction group includes the following text elements:

  - A main instruction is a line of text that appears as a heading at the top of the content pane. You use the main instruction to describe the task you are working on. Every tab page that appears in the content pane must have a main instruction. For example, the **Collections** tab of the **Accounts receivable parameters** form uses **Set up options for collections and collection letters** to describe the task.

  - A supplemental instruction is a line of plain text that appears under the main instruction. You use the supplemental instruction to provide additional guidance about how to complete the task. Supplemental instructions are optional and you can decide not to include a supplemental instruction. If you add a supplemental instruction, always use complete, concise sentences that include ending punctuation.

To add instructions for a task, you add a group control and two static text controls to the tab page in the **Design** node of the form. You should use labels to populate the **Text** property of the static text controls. The labels should specify the text you want to appear in the static text controls. To format the text, use the **Style** property of the group control and the static text controls. For information about how to add a task instruction group, see [How to: Create a Table of Contents form](how-to-create-a-table-of-contents-form.md).

### ![Hh745332.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Hh745332.collapse_all(en-us,AX.60).gif")Content Pane

The content pane is the section of the form to the right of the table of contents pane that shows fields and other information for the selected vertical tab. The content pane includes the fields and controls you use to view, create, update, or delete a record. The fields and controls are included in a details group that appears under the task instruction group. You should use a line to separate the task instruction group from the details group.

Before you add fields and other controls to your tab page, you must add a group control. The details group appears under the task instruction group. To organize the fields and controls that appear in the details group, you should use one of the following design patterns. For information about simple form design patterns, see [Simple List Forms Overview](simple-list-forms-overview.md).

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Design pattern</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Simple details</p></td>
<td><p>To add information to the content pane, you add fields and controls to the details group. You should set the <strong>Style</strong> property of the details group to <strong>TOCTopicSimple</strong>. To learn how to create a table of contents form, see <a href="how-to-create-a-table-of-contents-form.md">How to: Create a Table of Contents form</a>.</p>
<p>You can also use two or more FastTabs to organize and display the fields that appear in the content pane. You add the FastTabs to the details group. If you add FastTabs, you must set the <strong>Style</strong> property of the details group to <strong>TOCTopicFastTabs</strong>. For information about how to add a FastTab, see <a href="how-to-add-fasttabs-to-a-form.md">How to: Add FastTabs to a Form</a>.</p></td>
</tr>
<tr class="even">
<td><p>Simple list</p></td>
<td><p>To add a list of records to the content pane, you can add a grid to the details group. You should set the <strong>Style</strong> property of the details group to <strong>TOCTopicList</strong>.</p></td>
</tr>
<tr class="odd">
<td><p>Simple list and details</p></td>
<td><p>You can use a grid that shows a list of records together with a details section that shows information about the selected record. You should set the <strong>Style</strong> property of the details group to <strong>TOCTopicSimple</strong>.</p>
> [!caution]  
> <P>You should avoid using the list and details pattern. The list grid and the details section add another layer of navigation that complicates the form. You should try to fit the information into an editable grid. You can then use the grid to add or update records.</P>
</td>
</tr>
</tbody>
</table>


To associate actions with the records that appear in the content pane, you can add an action pane strip to the details group. Typically, you add the action pane strip to the top of the details group. This enables the action pane strip to appear under the task instructions. For information about how to add an action pane strip to a form, see [How to: Create an Action Pane Strip](how-to-create-an-action-pane-strip.md).

### ![Hh745332.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Hh745332.collapse_all(en-us,AX.60).gif")Permissions

To secure a table of contents form or a control that is used on the form, you use the Microsoft Dynamics AX role-based security system. Role-based security uses permissions and roles to restrict access to forms, controls, and data records. For more information about the role-based security system, see [Role-based Security in the AOT for Developers](role-based-security-in-the-aot-for-developers.md).

In the AOT, each form includes a **Permissions** node. You use **Permissions** to specify user rights for controls, tables, methods, and forms that are associated with the form. For information about how to use security permissions and roles, see [Security Permissions Properties for a Form](security-permissions-properties-for-a-form.md).

## Development Tools

To create a table of contents form, you use the same techniques that you use when you create other Microsoft Dynamics AX forms. The AOT provides the tools that you use to create or modify the form. In addition, you can use the AOT to specify the template, add the form data source, and add controls to the form. For more information about how to create a table of contents form, see [How to: Create a Table of Contents form](how-to-create-a-table-of-contents-form.md).

As you create a table of contents form, you can use the form style best practice tool to validate the form. You can use the tool to identify differences between the form and the template for the specified type of form. Periodically run the form style best practice tool to check the form for compliance with best practice guidelines for the table of contents forms. For information about how to use the form style best practice tool, see [How to: Validate the Style of a New Form](how-to-validate-the-style-of-a-new-form.md).

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

