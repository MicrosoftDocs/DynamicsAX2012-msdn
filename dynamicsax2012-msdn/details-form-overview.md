---
title: Details Form Overview
TOCTitle: Details Form Overview
ms:assetid: 1609d6a3-da3b-4a12-aaff-66d3f92360db
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh397314(v=AX.60)
ms:contentKeyID: 36929805
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Details Form Overview 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

A details form is a collection of client user interface (UI) elements that work together to display and enable interaction for a single record. You use details forms to enter new data into Microsoft Dynamics AX. The following illustration shows the elements of a details form:

![The design elements of a details form](images/Hh397314.Client_Details(en-us,AX.60).png "The design elements of a details form")

## Details Form Basics

A details form always opens in a separate window. The details form shows fields and related information about the specified record. A details form can appear in one of the following modes:

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Mode</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>View</p></td>
<td><p>View mode shows all fields as read-only. View mode prevents you from making unintended changes to the field values. When you first open a details form, the form opens in view mode.</p></td>
</tr>
<tr class="even">
<td><p>Edit</p></td>
<td><p>Edit mode enables you to enter values for the fields that appear on the form. You use edit mode when you want to update a field value. To switch to edit mode, you can click an action pane button or the <strong>Edit Record</strong> button (with a pencil icon) in the status bar.</p></td>
</tr>
</tbody>
</table>


Typically, details forms are opened from a list page or another form. As a result, you do not have to add them to the Navigation Pane or an area page. For example, the **Customers** form opens when you double-click a record in the **All customers** list page. For information about how to open a form from a list page, see [How to: Specify the Default Action for the List Page Grid](how-to-specify-the-default-action-for-the-list-page-grid.md).

## Details Form Types

The Microsoft Dynamics AX client supports the following types of details forms:

### ![Hh397314.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Hh397314.collapse_all(en-us,AX.60).gif")Details Form

A details form is the form you use to enter a record into Microsoft Dynamics AX. The details form design pattern includes a details view and an editable grid view that you can use to view or enter records. To switch between the details view and the editable grid, you click the Grid View button in the status bar. The following table describes each type of view.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>View</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Details</p></td>
<td><p>The details view shows a collection of fields associated with a single record. You use the details view to create, view, edit, or perform an action on a record. For information about how to customize the details view, see <a href="how-to-add-fields-to-a-details-form.md">How to: Add Fields to a Details Form</a>.</p></td>
</tr>
<tr class="even">
<td><p>Grid</p></td>
<td><p>The grid view shows an editable grid you can use to quickly find, view, and update a record or a collection of similar records. However, the grid shows a smaller number of fields. Typically, the grid includes the fields that are required to successfully create or update a record. For information about how to customize the grid view, see <a href="how-to-add-fields-to-a-details-form.md">How to: Add Fields to a Details Form</a>.</p>
<p>The grid view uses the same business logic that you use when you create or modify a record in the details view of the form. If you click the <strong>Edit in grid</strong> button on a list page, the specified record opens in the editable grid view of a details form.</p></td>
</tr>
</tbody>
</table>


### ![Hh397314.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Hh397314.collapse_all(en-us,AX.60).gif")Details Form with Lines

A details form with lines is like a details form. However, it includes additional views that enable you to create, view, edit, and delete the line items associated with the main record. The header view displays the full header for the record. The line view displays only the most important fields from the header and all of the lines associated with the record.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>View</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Details</p></td>
<td><p>The details view of a details form with lines includes two sections:</p>
<ul>
<li><p>A header section that is a collection of fields associated with a single record. You use the header section to create, view, edit, or perform an action on a record. For information about how to customize the header section, see <a href="how-to-add-fields-to-a-details-form.md">How to: Add Fields to a Details Form</a>.</p></li>
<li><p>A lines section that is a collection of the lines associated with a specified record. You use the lines section to view, enter, or update line information for a record.</p>
<p>The lines section includes a grid that lists the line items for the record. You cannot collapse the tab that contains the grid. The lines section also includes tabs for header and line details information. For information about how to customize the lines section, see <a href="how-to-customize-the-line-view-of-a-details-form-with-lines.md">How to: Customize the Line View of a Details Form with Lines</a>.</p></li>
</ul>
<p>You use the buttons in the <strong>Show</strong> group of the action pane to switch between the header view and the lines view.</p></td>
</tr>
<tr class="even">
<td><p>Grid</p></td>
<td><p>The grid view is an editable grid that lists records. The grid view includes an editable grid you can use to quickly find, view, and update a record or a collection of similar records. The grid view is the same view that you see in the details form design pattern. For information about how to customize the grid view, see <a href="how-to-add-fields-to-a-details-form.md">How to: Add Fields to a Details Form</a>.</p></td>
</tr>
</tbody>
</table>


## Details Form Design

To create or customize a details form, you use the **Forms** node of the AOT. The design patterns for the two types of details forms use many of the same AOT elements to create both form types.

### ![Hh397314.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Hh397314.collapse_all(en-us,AX.60).gif")Templates

When you create a details form, you must specify a design style for the form. To create a details form, you should use one of the following templates:

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Form style template</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>DetailFormMaster</strong></p></td>
<td><p>Use this template to create a form that implements the details form design pattern. You use the form to show detailed information for a single record. For information about the details form design pattern, see <a href="details-form-user-experience-guidelines.md">Details Form User Experience Guidelines</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>DetailFormTransaction</strong></p></td>
<td><p>Use this template to create a form that implements the details form with lines design pattern. You use the form to show the line items associated with a record. For information about the details form with lines design pattern, see <a href="details-form-with-lines-user-experience-guidelines.md">Details Form with Lines User Experience Guidelines</a>.</p></td>
</tr>
</tbody>
</table>


The template populates the **Style** property in the **Design** node and adds several controls that are required for the specified design pattern. In addition, the template configures many property values for you so that you can focus on adding new fields and controls to the form. For information about how to use a template to create a new details form, see [How to: Create a Details Form](how-to-create-a-details-form.md).

### ![Hh397314.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Hh397314.collapse_all(en-us,AX.60).gif")Data Sources

To populate a details form, you add the tables that contain the records that you want to access to the **Data Sources** node of the form. For more information about how to add a data source, see [How to: Add a Data Source to a Details Form](how-to-add-a-data-source-to-a-details-form.md).

### ![Hh397314.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Hh397314.collapse_all(en-us,AX.60).gif")Action Pane

A details form must include an action pane. The action pane is a collection of tabs, button groups, and button controls. The buttons represent the actions that you can perform on the current data record. Examples of actions include creating a record, deleting a record, and editing a record. To initiate an action, click the button that represents the action. You can also use an action pane button to open a related form.

If you use either details form template, a basic action pane is added to the form for you. You can then add the tabs, groups, and controls that organize, label, and execute actions. For more information about action panes, see [Action Pane Overview](action-pane-overview.md).

### ![Hh397314.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Hh397314.collapse_all(en-us,AX.60).gif")Page Title

The page title is the area of the details form that identifies the record that appears in the form. Typically, the page title shows fields that uniquely identify the record that appears in the form. For example, the **Customers** form shows the ID and name of the customer. You can show additional information about the record below the page title. For information about how to specify the values that appear in the page title, see [How to: Specify the Page Title for a Details Form](how-to-specify-the-page-title-for-a-details-form.md).

### ![Hh397314.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Hh397314.collapse_all(en-us,AX.60).gif")FastTab

A FastTab is a container for data entry controls. You use FastTabs to organize the fields that appear on a form. When you view the form, you can expand and collapse individual FastTabs. This enables you expand more than one FastTab in the form so that you can see the content of several FastTabs at the same time. You view the form from top to bottom, just as you would a document.

A FastTab can include one or more summary fields that remain visible when the FastTab is collapsed. You can show the field value from the following controls in the summary fields area of a FastTab:

  - **ComboBox**

  - **DateEdit**

  - **GuidEdit**

  - **Int64Edit**

  - **IntEdit**

  - **RealEdit**

  - **StringEdit**

  - **TimeEdit**

  - **UtcDateTimeEdit**

### ![Hh397314.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Hh397314.collapse_all(en-us,AX.60).gif")Action Pane Strip

An action pane strip is a simplified version of an action pane. An action pane strip can include several buttons that perform actions on the record in the FastTab. You add an action pane strip to a FastTab when you want to associate a set of actions with the data fields that appear in the tab. The action pane strip makes relevant actions easier to find than if they were included in the action pane at the top of the form.

### ![Hh397314.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Hh397314.collapse_all(en-us,AX.60).gif")FactBox Pane

The FactBox pane provides additional information related to the record that appears in the form. The FactBox pane can contain Info Parts, Form Parts, and Cue Groups. To add a FactBox to a details form, you add a part to the **Parts** node of the form. For more information about how to add a FactBox to a form, see [How to: Add a Part to the FactBox Pane](how-to-add-a-part-to-the-factbox-pane.md).

The FactBox pane is an optional element for a details form. If you do not add any parts to the **Parts** node of the form, the FactBox pane does not appear with the form. To best use the FactBox pane, you should have at least two parts.

### ![Hh397314.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Hh397314.collapse_all(en-us,AX.60).gif")Permissions

To secure a details form or a control that is used on a details form, you use the Microsoft Dynamics AX role-based security system. Role-based security uses permissions and roles to restrict access to forms, controls, and data records. For more information about the role-based security system, see [Role-based Security in the AOT for Developers](role-based-security-in-the-aot-for-developers.md).

In the AOT, each form includes a **Permissions** node. You use **Permissions** to specify user rights for controls, tables, methods, and forms that are associated with the form. For information about how to use security permissions and roles, see [Security Permissions Properties for a Form](security-permissions-properties-for-a-form.md).

## Development Tools

To create a details form, you use the same techniques that you use when you create other Microsoft Dynamics AX forms. The AOT provides the tools that you use to create or modify a details form. In addition, you can use the AOT to specify the template, add the form data source, add controls to the form, and add actions to the Action Pane. For more information about how to create a details form, see [How to: Create a Details Form](how-to-create-a-details-form.md).

As you create a new details form, you can use the form style best practice tool to validate the form. You can use the tool to identify differences between the form and the template for that type of form. Periodically run the form style best practice tool to check the form for compliance with best practice guidelines for details forms. For information about how to use the form style best practice tool, see [How to: Validate the Style of a New Form](how-to-validate-the-style-of-a-new-form.md).

## See also

[Form Overview](form-overview.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

