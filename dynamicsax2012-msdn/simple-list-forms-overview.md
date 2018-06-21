---
title: Simple List Forms Overview
TOCTitle: Simple List Forms Overview
ms:assetid: 95445ba9-4093-4040-8436-79a90979c780
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh538484(v=AX.60)
ms:contentKeyID: 39508917
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Simple List Forms Overview [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

A simple list form is a form you use to view a collection of records in a list. You use simple list forms for record types that include a small number of fields. Typically, a simple list form shows all the fields for a specified type of record. You use a simple list form to view a collection of records, or to update, add, or delete a single record.

## Simple List Form Basics

You use simple list forms to view, update, and create the following types of data.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Type</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Dependent data</p></td>
<td><p>An entity that you associate with master data, transaction data, or reference data. Dependent data is generally deleted when the parent record is deleted.</p>
<p>Master data is an entity that describes the parties, locations, products, and activities you use to document and record business events. Transactional data is an entity you use to document a business event and record the economic value of the event.</p></td>
</tr>
<tr class="even">
<td><p>Reference data</p></td>
<td><p>A named entity that has no describing properties or numeric values. You can associate reference data with both master and transaction data. Reference data is found in the setup areas of the system and is stable over time.</p></td>
</tr>
</tbody>
</table>


## Simple List Form Types

The Microsoft Dynamics AX client supports the following types of simple list forms:

### ![Hh538484.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Hh538484.collapse_all(en-us,AX.60).gif")Simple list

A simple list form enables you to work with a collection of records in a grid. You use the list to view, create, update, or delete a record. You can use a simple list form with reference or dependent data. You should use a simple list form when the record type that appears in the form requires that you show six or fewer fields. The following illustration shows the components of a simple list form.

![Simple list form design elements](images/Hh538484.Client_SimpleListFormDesign(en-us,AX.60).png "Simple list form design elements")

### ![Hh538484.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Hh538484.collapse_all(en-us,AX.60).gif")Simple list and details

A simple list and details form combines a list section with a details section. You use the grid in the list section to select the record you want to work with. When you select a record, the complete record appears in the details section of the form. You use the details section to show the information that you must have in order to understand and work with the data records in the list. In addition, you use the details section to view, update, create, or delete a record.

You should use a simple list and details form to view and create reference data. In addition, you use a simple list and details form when you have to show more than six fields on the form. The following illustration shows the components of a simple list and details form.

![Simple list and details design elements](images/Hh538484.Client_SimpleListDetailsFormDesign(en-us,AX.60).png "Simple list and details design elements")

### ![Hh538484.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Hh538484.collapse_all(en-us,AX.60).gif")Simple details

A simple details form shows a collection of fields in a details view. You can use a simple details form to view, update, create, and delete reference or dependent data. You use a simple details form when you want to work with a single record. For more information about the simple details form, see [Simple Details User Experience Guidelines](simple-details-user-experience-guidelines.md).

## Simple List Form Design

To create or customize a simple list form, you use the **Forms** node of the AOT. The design patterns for the simple list and simple list and details forms use many of the same elements. For more information about simple list form design, see [Simple List User Experience Guidelines](simple-list-user-experience-guidelines.md) or [Simple List and Details User Experience Guidelines](simple-list-and-details-user-experience-guidelines.md).

### ![Hh538484.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Hh538484.collapse_all(en-us,AX.60).gif")Templates

To create a simple list form, you specify the design style for that form. To create a simple list or simple list and details form, you should use one of the following templates:

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
<td><p><strong>SimpleList</strong></p></td>
<td><p>Use this template to create a simple list form. For information about how to use the template, see <a href="how-to-create-a-simple-list-form.md">How to: Create a Simple List Form</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>SimpleListDetails</strong></p></td>
<td><p>Use this template to create a simple list and details form. For information about how to use the template, see <a href="how-to-create-a-simple-list-and-details-form.md">How to: Create a Simple List and Details Form</a></p></td>
</tr>
</tbody>
</table>


The template populates the **Style** property in the **Design** node and adds several controls that are required for the specified design pattern. In addition, the template configures many property values for you so that you can focus on adding fields and controls to the form.


> [!NOTE]
> <P>There is no template for the simple details type of form.</P>



### ![Hh538484.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Hh538484.collapse_all(en-us,AX.60).gif")Data sources

To populate a simple list or simple list and details form, you add one or more tables to the **Data Sources** node of the form. To populate the form, you add a database table that contains the records you want to appear in the form. For more information about how to add a data source, see [How to: Add a Data Source to a Details Form](how-to-add-a-data-source-to-a-details-form.md).

### ![Hh538484.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Hh538484.collapse_all(en-us,AX.60).gif")Action pane strip

You can add an action pane strip to both the simple list and simple list and details form. An action pane strip is a simplified version of an action pane. You use the buttons on the action pane strip to perform actions on the selected record. For more information about the action pane strip, see [Action Pane Strip Overview](action-pane-strip-overview.md).

The typical action pane strip contains **New** and **Delete** buttons as the first two actions. You can add more buttons to the right of the **New** and **Delete** buttons. Typically, you add a button separator between the **New** and **Delete** buttons and the buttons you add. For information about how to customize the action pane strip, see [How to: Customize the Action Pane Strip](how-to-customize-the-action-pane-strip.md).

### ![Hh538484.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Hh538484.collapse_all(en-us,AX.60).gif")Page title

The page title is an optional element of both the simple list and simple list and details form. You use the page title to identify the selected record, supply important context information, or show a text message. The page title is optional and you do not have to add a page title if that information is already visible in the form. For information about how to add a page title, see [How to: Add a Page Title Group to a Simple List Form](how-to-add-a-page-title-group-to-a-simple-list-form.md).

The page title does not appear on the form unless you add a **StringEdit** control to the page title group. To specify the page title, you can use one of the following options to set the text value of the control:

  - You use the **DataField** property to specify a field from the form data source. The control displays the value for that field for the record that is selected in the simple list or simple list and details form.

  - You use the **DataMethod** property to specify a method from the data source. For example, you can use the parentTitleFields method to show field values from a parent record.

  - You populate the **Text** property of the control to provide information to the user about the form. You can use the property sheet to type a message into the **Text** property or you can use X++ to dynamically populate the property.

### ![Hh538484.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Hh538484.collapse_all(en-us,AX.60).gif")Custom filter

The custom filter is an optional element of both the simple list and simple list and details form. The custom filter includes controls you use to specify the records that appear in the grid. If you set a value in the control, the list updates to show the records that include the specified value.

The custom filter is an optional element and will not appear on the form unless a control is added to the custom filter group. For information about how to add a custom filter, see [How to: Add Filter Controls to a Simple List Form](how-to-add-filter-controls-to-a-simple-list-form.md).

### ![Hh538484.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Hh538484.collapse_all(en-us,AX.60).gif")Grid

The simple list and simple list and details form include a grid. The grid should not let you select more than one record. By default, the grid is sorted in ascending order on the first column. The column header will include a sort indicator. When you view the form, you can change the column and the sort order. The following table shows how you use the grid with each type of simple list form.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Form type</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Simple list</p></td>
<td><p>You use the grid to display up to six columns. The fields in the grid should be editable.</p></td>
</tr>
<tr class="even">
<td><p>Simple list and details</p></td>
<td><p>You use the grid to display between two and four columns. The fields in the grid should not be editable.</p>
<p>The columns that appear in the grid of a simple list and details form should be repeated in the details section. You repeat the field to clearly connect the list and details information across the two sections.</p></td>
</tr>
</tbody>
</table>



> [!WARNING]
> <P>You should not include a row label column in the grid. The appearance of row labels could cause confusion because the simple list and simple list and details forms do not support selecting multiple records.</P>



### ![Hh538484.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Hh538484.collapse_all(en-us,AX.60).gif")Splitter

A simple list and details form includes a vertical splitter between the list section and the details section. The splitter enables you to manually resize the space allocated to the grid and the details sections.

### ![Hh538484.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Hh538484.collapse_all(en-us,AX.60).gif")Details header

You use the details header for a simple list and details form to show field values that identify the record. Typically, you show the same two to four fields that appear in the grid. The details header should not have scrollbars. In addition, the details header is optional. You do not need a details header if the form displays all the fields for a record without using FastTabs or scrollbars.

### ![Hh538484.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Hh538484.collapse_all(en-us,AX.60).gif")Details tab

You use the details tab of a simple list and details form to show the important fields for a specified record. The details tab appears on the right side of the form. Typically, you show the grid columns or tree node labels as the first fields at the top of the form. The fields must appear in the same order that they appear in the grid or tree control.

If you use a template to create the form, the template supplies the group, tab, and tab page controls for the details tab. To complete the form you can add fields or field groups to the existing controls. If you have more fields than can appear on a single tab page, consider using FastTabs to display and organize the fields. However, you should not use FastTabs unless the form will include two or more.

### ![Hh538484.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Hh538484.collapse_all(en-us,AX.60).gif")FastTabs

If the record type that appears in a simple list and details form includes many fields, you can use two or more FastTabs to organize and display the fields. The FastTabs will appear in the details section of the form. FastTabs enable you to expand or collapse a collection of fields. If a FastTab includes the fields that identify the record, you will not see those fields when that FastTab is collapsed. As a result, you should not put fields that identify the record in a FastTab. You should add the fields that identify the record to the details header of the form.

By default, the first FastTab will appear expanded and all the others will be collapsed. The height of a FastTab should not grow when the form is resized. For information about how to use a FastTab with a form, see [FastTabs](fasttabs.md).

You can add an editable grid to a FastTab. However, you should also add an action pane strip to the FastTab that includes an **Add** and a **Remove** button. You can use the action pane buttons to work with the records in the grid. For information about how to use an action pane strip with a FastTab, see [Action Pane Strip Overview](action-pane-strip-overview.md).

### ![Hh538484.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Hh538484.collapse_all(en-us,AX.60).gif")Permissions

To secure a simple list form or a control that is used on a simple list form, you use the Microsoft Dynamics AX role-based security system. Role-based security uses permissions and roles to restrict access to forms, controls, and data records. For more information about the role-based security system, see [Role-based Security in the AOT for Developers](role-based-security-in-the-aot-for-developers.md).

In the AOT, each form includes a **Permissions** node. You use **Permissions** to specify user rights for controls, tables, methods, and forms that are associated with the form. For information about how to use security permissions and roles, see [Security Permissions Properties for a Form](security-permissions-properties-for-a-form.md).

## Development Tools

To create a simple list or a simple list and details form, you use the same techniques that you use when you create other Microsoft Dynamics AX forms. The AOT provides the tools that you use to create or modify the form. In addition, you can use the AOT to specify the template, add the form data source, add controls to the form, and add actions to the action pane strip. For more information about how to create a simple list form, see [How to: Create a Simple List Form](how-to-create-a-simple-list-form.md) or [How to: Create a Simple List and Details Form](how-to-create-a-simple-list-and-details-form.md).

As you create a simple list or simple list and details form, you can use the form style best practice tool to validate the form. You can use the tool to identify differences between the form and the template for the specified type of form. Periodically run the form style best practice tool to check the form for compliance with best practice guidelines for simple list or simple list and details forms. For information about how to use the form style best practice tool, see [How to: Validate the Style of a New Form](how-to-validate-the-style-of-a-new-form.md).

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

