---
title: Content Page Overview
TOCTitle: Content Page Overview
ms:assetid: 949e08e3-53ce-4068-8c6f-9ff6925707be
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc605868(v=AX.60)
ms:contentKeyID: 35247597
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Content Page Overview [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

A Microsoft Dynamics AX content page is a collection of client user interface (UI) elements that work together to display data, enable data interaction, and support navigation. A content page enables a variety of controls that display data in the client content pane.

## Content Page Features

The basic structure of a content page is like a list page. A content page requires a form, a data source, and an action pane. In addition, you add a content page to the client Navigation Pane using the same techniques as a list page. For more information, see [List Page Overview](list-page-overview.md).

### ![Cc605868.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc605868.collapse_all(en-us,AX.60).gif")Validation

A key difference between a content page and a list page is the validation that is performed when you use the Application Object Tree (AOT) to build the page. A content page does not restrict the type of control that you use to display data in the client content pane. This gives you more freedom to design how the page displays that data.


> [!NOTE]
> <P>While a content page allows for more flexibility with how data is displayed, a content page should behave like other navigation pages. For example, the content pane should display basic data for a group of records. The content page should supply action pane buttons that perform specific actions on those records. A content page should always open a detail form to create or update a record.</P>



### ![Cc605868.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc605868.collapse_all(en-us,AX.60).gif")Content Pane

A content page enables different types of controls to display data in the client content pane. For example, you could use a tree control to represent the organizational hierarchy of related data records.

How the content pane displays data depends on the type of control that you use. To display data, you might have to override methods that load data from the data source into the control. You might also have to override methods that specify how the control responds to UI events.

## Data Sources

To populate a content page, you must supply a query that retrieves the desired records from the database. To provide consistent results and to make it easier to maintain your query, use the AOT to create the query. For more information about how to create a query, see [How to: Create Queries by using the AOT](how-to-create-queries-by-using-the-aot.md).

To use a query as the data source for a content page, use the same procedure as a list page. For more information, see [How to: Add a Data Source to a Primary List Page](how-to-add-a-data-source-to-a-primary-list-page.md).

## Permissions

To secure a list page or a list page control you use the Microsoft Dynamics AX role-based security system. Role-based security uses permissions and roles to restrict access to forms, controls, and data records. For more information about the role-based security system, see [Role-based Security in the AOT for Developers](role-based-security-in-the-aot-for-developers.md).

In the AOT, each form includes a **Permissions** node. You use **Permissions** to specify user rights for controls, tables, methods, and forms that are associated with the list page. For information about how to use security permissions and roles, see [Walkthrough: Using Roles and Privileges to Control Access to Forms](walkthrough-using-roles-and-privileges-to-control-access-to-forms.md).

## Development Tools

To create a content page, you use the same techniques that you use with other Microsoft Dynamics AX forms. The AOT provides the tools that you need to create or modify a content page. The AOT enables you to specify the content page data source, add basic content page UI elements, and define the actions that the content page supports.

Next, you will want to create a new content page. For more information about how to create a contact page, see [How to: Create a Content Page](how-to-create-a-content-page.md).

## See also

[Area Page Overview](area-page-overview.md)

[Walkthrough: Creating a Form by Using the AOT](walkthrough-creating-a-form-by-using-the-aot.md)

[AOT Overview](aot-overview.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

