---
title: List Page Overview
TOCTitle: List Page Overview
ms:assetid: acf216cf-1190-4b19-896b-8a1e26cf8ba3
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc616937(v=AX.60)
ms:contentKeyID: 35249721
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# List Page Overview [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

A Microsoft Dynamics AX list page is a form that displays a list of related data records. List pages represent the primary means of displaying data, performing actions on specified records, and opening forms.

## List Page Basics

You begin list page development by identifying the data records that you want to appear in the list. To populate a list page, you have to have a query that retrieves a collection of related records. You use that query as the form data source for the list page. In addition, you have to define the actions to perform on the records in the list, and identify related forms you want to open from the list page.

A list page can appear in both the Windows client application and Enterprise Portal (EP). All list pages include a class that inherits from a base class named ListPageInteraction. Both the client and Enterprise Portal use the ListPageInteraction class and the form metadata to render the list page. As a result, you can build a single list page that can appear in both environments.

To customize a list page for either the client or Enterprise Portal, many of the controls and FactBoxes include the **DisplayTarget** property. **DisplayTarget** lets you specify whether a control or FactBox appears in the client, in Enterprise Portal, or in both. By default, the property is set to **Auto** so that the control or FactBox appears in both.

For more information about how to add a list page to Enterprise Portal, see [List Page Reference](list-page-reference.md).

## List Page Types

The Microsoft Dynamics AX client supports the following types of list pages:

### ![Cc616937.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc616937.collapse_all(en-us,AX.60).gif")Primary List Page

A primary list page displays a list of related records. Typically, the query for a primary list page retrieves all the data records for a specified type of document. For example, the **All customers** list page is a primary list page that lists all the customers for a company.

A primary list page can use a data range (filter) to reduce the number of records in the list. The goal of the filter should be to make that list more useful. For example, a customer list page that shows only active customers might be more useful than a list of all available customers. For more information about how to create a primary list page, see [How to: Create a List Page Form](how-to-create-a-list-page-form.md).

### ![Cc616937.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc616937.collapse_all(en-us,AX.60).gif")Secondary List Page

A secondary list page displays a filtered version of the primary list page. One or more common attributes of the list data is used to modify the data source that selects the data for the secondary list. The list of records in a secondary list page is always a subset of the list found on a primary list page. Typically, the name of a secondary list page specifies the key attribute used to select the records for the list. For example, **Customers on hold** lists only the customers who are marked to have invoicing and delivery on hold.

To create a secondary list page, you modify the query from the primary list page. Typically, you add a range to the query that restricts the records that appear in the list. For information about how to create a secondary list page, see [Walkthrough: Creating a Secondary List Page](walkthrough-creating-a-secondary-list-page.md).

## List Page Design

A list page form is a collection of client user interface (UI) elements that work together to display data, enable data interaction, and support navigation. The following illustration shows the elements of a typical list page:

List page elements

  
![The design elements of a list page](images/Cc616937.Client_ListPageDesign(en-us,AX.60).gif "The design elements of a list page")

**List page elements**

The following sections describe the elements that you use to create or modify a list page.

### ![Cc616937.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc616937.collapse_all(en-us,AX.60).gif")Data Sources

To populate a primary list page, you have to supply a query that retrieves the desired records from the database. To provide consistent results and to make it easier to maintain your queries, use the AOT to create the query. For more information about how to create a query, see [How to: Create Queries by using the AOT](how-to-create-queries-by-using-the-aot.md).

To create a secondary list page, you have to create a query that retrieves the records for the secondary list page. Typically, you create a duplicate of the data source for the primary list and add a data range that limits the records that the query retrieves. For information about how to create a secondary list page data source, see [Walkthrough: Creating a Secondary List Page](walkthrough-creating-a-secondary-list-page.md).

### ![Cc616937.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc616937.collapse_all(en-us,AX.60).gif")Action Pane

The action pane is a collection of tab, button group and button controls. The buttons represent the actions that you can perform on the data records in the data grid. Examples of list page actions include creating a record, printing the list, and deleting one or more records. To initiate an action, click the button that implements that action.

The action pane is automatically added when you create a new list page form. You have to add the controls that organize, label, and execute actions. For more information about action panes, see [Action Pane Overview](action-pane-overview.md). For information about how to add an action pane to a list page, see [Walkthrough: Creating a List Page and Adding an Action Pane](walkthrough-creating-a-list-page-and-adding-an-action-pane.md).

### ![Cc616937.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc616937.collapse_all(en-us,AX.60).gif")Filter Pane

The filter pane is a collection of controls that you use to find and view a specific record or a group of similar records. The filter pane lets you search the data records in the data grid.

The filter pane is automatically added when you create a new list page form. To support more complex searches, you can add the following types of controls to the list page filter pane.

  - CheckBox

  - ComboBox

  - DataEdit

  - IntEdit

  - RealEdit

  - ReferenceGroup

  - StringEdit

  - TimeEdit

  - UtcDateTimeEdit

To specify values for the filter controls, you bind the control to an enumeration or extended data type (EDT). For information about how to customize the filter pane, see [How to: Add Controls to the Filter Pane](how-to-add-controls-to-the-filter-pane.md).

### ![Cc616937.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc616937.collapse_all(en-us,AX.60).gif")Data Grid

The data grid is a control that shows specified data fields for a list of records. The data grid is automatically added when you create a new list page form. You must specify the fields that appear in the data grid. For information about how to add fields to the data grid of a list page, see [How to: Add Fields to the List Page Grid](how-to-add-fields-to-the-list-page-grid.md).

The data grid uses the form data source to populate the fields that appear in the data grid. For information about how to add a data source to a list page, see [How to: Add a Data Source to a Primary List Page](how-to-add-a-data-source-to-a-primary-list-page.md).

### ![Cc616937.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc616937.collapse_all(en-us,AX.60).gif")FactBox Pane

The FactBox pane provides additional information about the items in the list and about the highlighted record in the data grid. The FactBox pane can contain Info Parts, Form Parts, and Cue Groups. You will add these to the list page form. For information about how to populate the FactBox pane, see [How to: Add a Part to the FactBox pane of a List Page](how-to-add-a-part-to-the-factbox-pane-of-a-list-page.md).

### ![Cc616937.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc616937.collapse_all(en-us,AX.60).gif")Preview Pane

A preview pane is an optional list page feature that displays additional data about the highlighted record in the data grid. The preview pane enables you to view additional data fields from a specific record without having to open that record in a new form. For information about how to add a preview pane, see [How to: Add a Preview Pane to a List Page](how-to-add-a-preview-pane-to-a-list-page.md).

## Permissions

To secure a list page or a control that is used on a list page, you use the Microsoft Dynamics AX role-based security system. Role-based security uses permissions and roles to restrict access to forms, controls, and data records. For more information about the role-based security system, see [Role-based Security in the AOT for Developers](role-based-security-in-the-aot-for-developers.md).

In the AOT, each form includes a **Permissions** node. You use **Permissions** to specify user rights for controls, tables, methods, and forms that are associated with the list page. For information about how to use security permissions and roles, see [Walkthrough: Using Roles and Privileges to Control Access to Forms](walkthrough-using-roles-and-privileges-to-control-access-to-forms.md).

## Development Tools

To create a list page, you use the same techniques that you use when you create other Microsoft Dynamics AX forms. The AOT provides the tools that you use to create or modify a list page form. The AOT enables you to specify the list page data source, add controls to the list page form, and define the actions that the list page supports.

For information about how to create a primary list page, see [How to: Create a List Page Form](how-to-create-a-list-page-form.md).

## See also

[Content Page Overview](content-page-overview.md)

[Area Page Overview](area-page-overview.md)

[AOT Overview](aot-overview.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

