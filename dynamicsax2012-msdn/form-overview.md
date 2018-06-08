---
title: Form Overview
TOCTitle: Form Overview
ms:assetid: 979878fc-d3e0-4f5a-814f-e28dcf579282
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa844397(v=AX.60)
ms:contentKeyID: 35247818
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Form Overview 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

A form is a window that you open from the Microsoft Dynamics AX client workspace that shows information and enables you to perform actions. For example, the following figure shows the form you use to view and enter information about a customer. Notice how the form has tabs, fields, and buttons that you can use to view, update, and perform actions with a customer record.

Customer details form

  
![Details form](images/Aa844397.detail-form-01(en-us,AX.60).png "Details form")

## Form Design Patterns

To create a form, you should first select a design pattern for that form. A design pattern is a set of guidelines that standardize the appearance and use of a form. You should select the design pattern that reflects the type of data that appears in the form and how you expect to use the form. For more information about form design, see [Client User Experience Guidelines](client-user-experience-guidelines.md).

The following sections provide an overview of the design patterns. There are patterns for forms that open in a separate window and for navigation forms that appear in the client workspace.

### ![Aa844397.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa844397.collapse_all(en-us,AX.60).gif")Forms

The following table lists the design patterns for forms. For more information about these patterns, see [Form User Experience Guidelines](form-user-experience-guidelines.md).

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Pattern</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Details form</p></td>
<td><p>You use the form to view, enter and update an individual record. In addition, the form enables you to perform actions on that record.</p></td>
</tr>
<tr class="even">
<td><p>Details form with lines</p></td>
<td><p>You use the form to view, enter and update an individual record that is associated with one or more related lines. In addition, the form enables you to perform actions on that record and the lines.</p></td>
</tr>
<tr class="odd">
<td><p>Dialog</p></td>
<td><p>You use the form to initiate a task or process where you must provide input. The form enables you to specify whether to continue or cancel the task or process.</p></td>
</tr>
<tr class="even">
<td><p>Drop dialog</p></td>
<td><p>You use the form to enter or update a small amount of data. The form enables you to enter data values without having to leave the parent form.</p></td>
</tr>
<tr class="odd">
<td><p>Simple details</p></td>
<td><p>You use the form to view, enter and update a record. You use the form for setup information or a record that is dependent upon another record.</p></td>
</tr>
<tr class="even">
<td><p>Simple list</p></td>
<td><p>You use the form to view, enter, and update records that appear as a list of records in a grid.</p></td>
</tr>
<tr class="odd">
<td><p>Simple list and details</p></td>
<td><p>You use the form to view a list of records and a details form at the same time. The detail section of the form shows additional fields for the highlighted record in the list.</p></td>
</tr>
<tr class="even">
<td><p>Table of contents</p></td>
<td><p>You use the form to complete a series of related setup or configuration tasks. The form includes a list of buttons that you click to specify the fields that appear in the form.</p></td>
</tr>
</tbody>
</table>


You might notice that there are no design patterns for journal and inquiry forms. The structures of these forms are dependent upon the data and the process they support. As a result, there are no standard design patterns for these types of forms.

### ![Aa844397.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa844397.collapse_all(en-us,AX.60).gif")Navigation Forms

You use navigation forms to find information, open forms, and perform actions. For example, you use a list page to find a single record or a collection of records that you want to work with. Unlike other forms, navigation forms open in the content pane of the client workspace.

The following table shows the types of navigation forms that you can create. For more information about these patterns, see [Navigation User Experience Guidelines](navigation-user-experience-guidelines.md).

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Pattern</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Area page</p></td>
<td><p>You use the form to list links to list pages, content pages, forms, reports, classes, jobs, and queries for a module.</p></td>
</tr>
<tr class="even">
<td><p>List page</p></td>
<td><p>You use the form to view a list of records. You use the list page to browse records, select one or more records, and perform an action upon the highlighted record or records.</p></td>
</tr>
<tr class="odd">
<td><p>Role center</p></td>
<td><p>You use the role center to shows a collection of information that is relevant to your Microsoft Dynamics AX role.</p></td>
</tr>
</tbody>
</table>


## Form Development

You use the Application Object Tree (AOT) to create a new form. The AOT enables you to add form components, and to view and set values for the properties of the form. You use property values to specify the appearance and behavior of the form. If the desired behavior cannot be set by using properties, you can use X++ code to customize form behavior. For information about how to create a form, see [Walkthrough: Creating a Form by Using the AOT](walkthrough-creating-a-form-by-using-the-aot.md).


> [!TIP]
> <P>To enable the reuse of code, you should add X++ code to the data sources (tables) or a class instead of the form.</P>



### ![Aa844397.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa844397.collapse_all(en-us,AX.60).gif")Templates

To create a form that implements a design pattern, you use a form template. The template generates a new form that has the basic structure and components specified by the design pattern. The template reduces the number of steps that you have to complete to create the new form. For an example that shows how to use a template to create a form, see [Walkthrough: Creating a List Page and Adding an Action Pane](walkthrough-creating-a-list-page-and-adding-an-action-pane.md).

To create a form with a template, right-click **Forms** in the AOT, click **New Form from template**, and then click the template that specifies the type of form you want to create. A form is generated from the specified template. The new form contains controls that implement the form structure specified by the design pattern for that form. In addition, several properties are populated with values that apply to the specified type of form. To complete the form, you add controls that provide access to the data and actions that the form supports.

For example, you use the AOT to create a form and you click the **SimpleListDetails** template. If you expand the **Design** node of the new form, you see that the form already includes several controls. In addition, The **Style** property in the **Design** node of that form is set to **SimpleListDetails**.

The following table lists the templates and describes the types of forms the templates create.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Template</p></th>
<th><p>Purpose</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DetailsFormMaster</p></td>
<td><p>Use the template to create a Details form to view, edit, and act on master data.</p></td>
</tr>
<tr class="even">
<td><p>DetailsFormTransaction</p></td>
<td><p>Use the template to create details form with lines to view, edit, and act on master data that has line items.</p></td>
</tr>
<tr class="odd">
<td><p>Dialog</p></td>
<td><p>Use the template to create a dialog window that provides a response to a question.</p></td>
</tr>
<tr class="even">
<td><p>DropDialog</p></td>
<td><p>Use the template to create a drop dialog form to perform an action with data.</p></td>
</tr>
<tr class="odd">
<td><p>ListPage</p></td>
<td><p>Use the template to create a list page you can use to find, analyze, and performs actions on master data.</p></td>
</tr>
<tr class="even">
<td><p>SimpleList</p></td>
<td><p>Use the template to create a simple list form to view, edit, and act on dependent or reference data.</p></td>
</tr>
<tr class="odd">
<td><p>SimpleListDetails</p></td>
<td><p>Use the template to create a simple list and details form to view, edit, and act on dependent and reference data.</p></td>
</tr>
<tr class="even">
<td><p>TableOfContents</p></td>
<td><p>Use the template to create a table of contents form to view and edit configuration or setup data.</p></td>
</tr>
</tbody>
</table>


### ![Aa844397.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa844397.collapse_all(en-us,AX.60).gif")Form Style Properties

Each form has one or more properties that you can use to specify the design pattern for the form. These properties are called metadata style properties. When you specify a value for the metadata style property, you enable the client framework to substitute values at runtime for several other form and control properties.

You use metadata style properties to simplify form development. When you specify a value for the **Design.Style** property, you reduce the number of form property changes you have to make. The selection of a form style has the following effect on form and control properties.

  - If the style requires a form or control property to have a specified value, that property is made inactive in the AOT property sheet. The property is populated with the required value at runtime when the form is opened.

  - If the style has recommended values for some form and control properties, the client framework populates the property by using the recommended value when the form opens. However, the client framework only uses the template value if the AOT property sheet shows the default value for that property. As a result, you can override template specified property value by using the AOT to set a non-default value for a property.

The following table describes the properties you can use to specify the metadata style for a form.

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
<td><p><strong>Design.Style</strong></p></td>
<td><p>You use this property to specify the design pattern for a form. If you use a template to create a form, the property is set to reflect the design pattern that the template uses.</p>
<p>You should verify that the <strong>Style</strong> property accurately reflects the type of form you want to create. If you want to validate the form design, the validation tool uses the <strong>Style</strong> property to identify the validation template for the form.</p>
<p>In addition, you can use the <strong>Properties</strong> sheet of the AOT to manually set or change the <strong>Style</strong> property of a form.</p></td>
</tr>
<tr class="even">
<td><p><strong>Form.FormTemplate</strong></p></td>
<td><p>You use this property to specify whether the form uses an interaction class. All list pages require that you use an interaction class. The interaction class enables the list page to appear in both the client and Enterprise Portal.</p>
<div class="mtps-table">
<div class="mtps-row">
<img src="images/Hh404129.alert_caution(en-us,AX.60).gif" title="Caution note" alt="Caution note" class="note" /><strong>Caution</strong>
</div>
<div class="mtps-row">
If you specify a value for the property, you also have to populate the <strong>InteractionClass</strong> property. The property specifies the name of an interaction class. The default class for list pages is the <strong>ListPageInteraction</strong> class.
</div>
</div>
<p>You can also set the <strong>FormTemplate</strong> property for a details form. You can use an interaction class to help improve the performance of the details form. However, details forms do not require an interaction class.</p></td>
</tr>
</tbody>
</table>


### ![Aa844397.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa844397.collapse_all(en-us,AX.60).gif")Components

To complete the form, you add form components that retrieve data, specify how the data is used and displayed, and set security permissions for the form. The following table lists the components you find under each form node in the AOT.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Name</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Methods</strong></p></td>
<td><p>You add or override X++ methods for the form. You can use X++ to customize the appearance and behavior of the form. For more information about form methods, see <a href="methods-on-a-form.md">Methods on a Form</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>Data Sources</strong></p></td>
<td><p>You specify the database query, table, or view that the form uses to retrieve the data that appears in the form. For more information about the form data source, see <a href="form-data-sources.md">Form Data Sources</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Parts</strong></p></td>
<td><p>You add Parts that appear on the form. A Part is a specialized type of control that provides information related to the record that appears in the form. List pages and details forms have a FactBox pane or preview pane where the Parts appear. For more information about Parts, see <a href="parts.md">Parts</a>.</p></td>
</tr>
<tr class="even">
<td><p><strong>Designs</strong></p></td>
<td><p>You add the controls that appear on the form to the <strong>Design</strong> node of the form. For more information about how to add controls, see, <a href="using-controls-in-a-form-design.md">Using Controls in a Form Design</a>.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Permissions</strong></p></td>
<td><p>You specify access levels for the securable objects that appear in the form. For more information about security, see <a href="security-permissions-properties-for-a-form.md">Security Permissions Properties for a Form</a>.</p></td>
</tr>
</tbody>
</table>


## Validation

The Development Workspace includes a tool you can use to validate a form. You use form validation to identify differences between the design of the form you created and the form design pattern best practices for that type of form. Validation helps you create forms that follow the form design patterns used throughout the client.

To validate a form, you use the form style best practice tool. The form style best practice tool compares the structure of the form and the values that you specified for form and control properties to a standard form design template. The form style best practice tool uses the value in the **Design.Style** property of the form to determine the template that is used to validate the form.

To use the form style best practice tool, right-click a form in the AOT, click **Add-Ins**, and then click **Check form style best practices**. The **Form style analysis** window opens and lists the form style best practice violations for that form. You can use **Fix violation** button to quickly fix many design issues with the form. You can also use the **Re-analyze** button to repeat the validation of the form. For more information about how to use the form style best practice tool, see [How to: Validate the Style of a New Form](how-to-validate-the-style-of-a-new-form.md) or [How to: Convert an Existing Form to a New Style](how-to-convert-an-existing-form-to-a-new-style.md).

## See also

[Form Data Sources](form-data-sources.md)

[Controls in Microsoft Dynamics AX](controls-in-microsoft-dynamics-ax.md)

[Parts](parts.md)

[Menus and Menu Items](menus-and-menu-items.md)

[Enterprise Portal for Microsoft Dynamics AX](enterprise-portal-for-microsoft-dynamics-ax.md)

[User Experience Guidelines for Microsoft Dynamics AX 2012](user-experience-guidelines-for-microsoft-dynamics-ax-2012.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

