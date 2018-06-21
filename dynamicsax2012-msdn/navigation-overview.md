---
title: Navigation Overview
TOCTitle: Navigation Overview
ms:assetid: 83ad904c-d0a5-4ce0-9b28-85f4fcede9c3
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg862511(v=AX.60)
ms:contentKeyID: 35246158
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Navigation Overview [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

In Microsoft Dynamics AX, navigation to forms and reports is organized into modules. A module is a collection of forms, and reports that you use for a specified business activity. For example, you use the **Accounts receivable** module to open the forms and reports to track invoices and incoming payments from customers. In addition, some modules support role-based or administrative tasks that do not apply to a single business activity.

The client includes several specialized controls, forms, and modules that you use to find and open forms and reports. The Navigation Pane is the primary tool you use to access modules. In addition, each module has an area page and one or more list pages that you can use to find individual forms, reports, or data records. Area pages and list pages are types of navigation pages. The Navigation Pane and navigation pages always appear in the client workspace. When you click a link to a form or report, the form or report automatically opens in a separate task window that appears above the client workspace.

The following sections provide information about the controls, navigation pages, and modules you use to find and view forms, reports, and data records.

## Address Bar

The address bar appears at the top of the client. The address bar has forward, back and history buttons and shows the path you used to open the area or list page that appears in the client. In addition, you can use the drop-down list associated with each entry in the address bar to move to a different company, module, or page.

You cannot customize the address bar. To add, modify, or remove an entry that appears in the address bar, you have to change the menu or menu items for the module.

## Application Modules

An application module is a specialized module that includes navigation pages, forms, and reports that are used with more than one business activity. To add a navigation page, form, or report to an application module, you have to create a menu item and add that menu item to the Home, Organization administration, or System administration menus in the application object tree (AOT). For information about how to use the AOT to update the menu, see [How to: Create Menus and Menu Items](how-to-create-menus-and-menu-items.md).

The following table describes the available application modules.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Module name</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Home</p></td>
<td><p>The module that provides access to navigation pages, forms, and reports that apply to a role and not a specified business activity. For example, you create a form that can be used by everyone in your organization. To make that form available to everyone, add a menu item for the form to Home.</p>
<p>If you install Role Centers for the client, the role center appears in the Home module.</p></td>
</tr>
<tr class="even">
<td><p>Organization administration</p></td>
<td><p>The module that provides access to navigation pages, forms, and reports that you use to configure and maintain information about your organization.</p>
<p>If you have a form that is used in three or more modules, consider adding that menu item to Organization administration.</p></td>
</tr>
<tr class="odd">
<td><p>System administration</p></td>
<td><p>The module that provides access to navigation pages, forms, and reports that support the configuration and administration of Microsoft Dynamics AX.</p></td>
</tr>
</tbody>
</table>


## Area Pages

An area page appears in the client workspace when you first open a module. The area page includes links you can use to view list pages, forms, and reports for that module. Links are grouped into related submenus that include Common, Journal, Inquiries, Reports, Periodic, and Setup. For more information about these groups, see the table in the Navigation Pane section that follows.

To customize an area page, you use the AOT to add a menu item to the menu for the specified module. For more information about how to customize an area page, see [Area Pages](area-pages.md).

## List Pages

A list page is the navigation tool you use to work with data records. Each module should have one or more list pages. A list page shows a collection of records that you can filter and search to find the data records you want to work with. To view a data record in a detail form, you double-click the record in the list page grid. In addition, you can use the action pane of the list page to perform actions on records in the list page grid. For more information about list pages, see [List Page Forms](list-page-forms.md).

## Content Pages

A content page is a navigation page that you use to display data records in a format other than a list. You use a content page to display data, enable data interaction, and support navigation. For more information about content pages, see [Content Pages](content-pages.md).

## Navigation Pane

The Navigation Pane is the primary navigation tool in the client. The Navigation Pane shows you all the modules you have permission to access. Each button on the Navigation Pane represents an available module. If you click a button, links to the navigation pages, forms, and reports for that module appear in the Navigation Pane.

To modify the contents of the Navigation Pane, you use menu and menu items in the AOT. To add, modify, or remove anything that appears in the Navigation Pane, you have to change the menu, submenu, or menu items for the specified module. For information about how to use the AOT to update menus, see [How to: Create Menus and Menu Items](how-to-create-menus-and-menu-items.md).

To provide consistent navigation across modules, the links for a module always appear in one of the following groups.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Navigation Pane group</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Favorites</p></td>
<td><p>The <strong>Favorites</strong> section of the Navigation Pane includes links to the forms, reports, and queries that you specify. Typically, you find <strong>Favorites</strong> at the top of the Navigation Pane. However, you can use <strong>Show Favorites in Navigation Pane</strong> in the <strong>View</strong> section of the <strong>File</strong> menu to show or hide the <strong>Favorites</strong> section.</p>
<p>To add and maintain <strong>Favorites</strong>, you use <strong>Favorites</strong> or <strong>Add to Favorites</strong> found in the <strong>File</strong> and right-click menus of the client.</p></td>
</tr>
<tr class="even">
<td><p>Area page</p></td>
<td><p>Provides a link to the area page for the module. The link is automatically generated and cannot be changed.</p></td>
</tr>
<tr class="odd">
<td><p>Common</p></td>
<td><p>Provides links to the most frequently used forms for a module. The forms enable you to quickly find one or more data records and perform actions on those records. Typically, you add menu items that link to list pages and other primary forms that are not associated with a list page.</p></td>
</tr>
<tr class="even">
<td><p>Journal</p></td>
<td><p>Provides links to forms that you use to interact with a journal. You add menu items that link to journal forms that record the financial consequences of business events.</p></td>
</tr>
<tr class="odd">
<td><p>Inquiries</p></td>
<td><p>Provides links to forms you use to complete an inquiry. You add menu items that link to inquiry forms that you use to search and analyze a collection of data records.</p></td>
</tr>
<tr class="even">
<td><p>Reports</p></td>
<td><p>Provides links to the reports associated with the module.</p></td>
</tr>
<tr class="odd">
<td><p>Periodic</p></td>
<td><p>Provides links to the forms you use to complete periodically repeated tasks. Typically, you add menu items that link to forms that complete bulk updates to a set of data records on a monthly, quarterly, or other scheduled basis.</p></td>
</tr>
<tr class="even">
<td><p>Setup</p></td>
<td><p>Provides links to the forms you use to configure and maintain parameters and other information that is used in the module.</p></td>
</tr>
</tbody>
</table>


## Role Center

A role center is a navigation page that displays information that is relevant to a specified role. A role center is created in Enterprise Portal (EP) but can also be used in the client. The role center always appears in the Home module. For information about how to create a role center, see [Role Center Page Reference](role-center-page-reference.md).

## See also

[Area Pages](area-pages.md)

[Menus and Menu Items](menus-and-menu-items.md)

[List Page Forms](list-page-forms.md)

[Content Pages](content-pages.md)

[Role Center Page Reference](role-center-page-reference.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

