---
title: Area Page Overview
TOCTitle: Area Page Overview
ms:assetid: c93a6a2a-ffb8-480e-a0a8-238bc0807726
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc637871(v=AX.60)
ms:contentKeyID: 35251221
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Area Page Overview [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

An area page is a Microsoft Dynamics AX navigation page that displays menu items that link to list pages, content pages, forms, reports, classes, jobs, and queries. To view an area page, click a module button in the Navigation Pane. The area page opens in the client content pane.

## Area Page Features

When you click a module button in the Navigation Pane, the client automatically generates an area page using the menu information for that module. To display an area page, the client organizes the menu items using the following controls:

  - Groups

  - Lists

### ![Cc637871.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc637871.collapse_all(en-us,AX.60).gif")Groups

An area page typically contains one or more groups that organize menu items by type. Common area page group names include **Common**, **Journals**, **Inquiries**, **Reports**, **Periodic**, and **Setup**.

The **Common** group is automatically generated. This group contains menu items that open the forms that you use to work with individual data records.

All other area page groups represent submenus that have been added to the menu using the Application Object Tree (AOT). To add an item to one of these groups, use the AOT to add a menu item to that submenu.

### ![Cc637871.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc637871.collapse_all(en-us,AX.60).gif")Lists

An area page group contains a list of menu items. Each menu item opens a specified list page, content page, form, report, class, job, or query. When you add a menu item to an area page, you must specify a group for that menu item. To specify a group for a new menu item, use the following guidelines:

  - If the menu item represents a list page or content page, set the **IsDisplayedInContentArea** property to **Yes**.

  - If the menu item represents a non-list page or content page form, set the **IsDisplayedInContentArea** property to **No**.

  - If you want to display a menu item in a specific group, use the AOT to add that menu item to the submenu that represents that group.

## Development Tools

While you cannot directly design and build an area page, the AOT provides the tools that are required to create or update an area page. To display an area page, the client uses menu information to generate the area page for a module. To create or update an area page, use the AOT to provide the following menu information:

  - To create an area page, use the AOT to create a new menu and then add that menu to the **MainMenu**. To view the area page, save your changes and restart the client. The new menu is added to the Navigation Pane as a module button. To display the area page, click the new module button. To add groups and lists to the area page, use the AOT to add submenus and menu items. For more information about how to create a menu or menu item, see [How to: Create Menus and Menu Items](how-to-create-menus-and-menu-items.md).

  - To update an area page, use the AOT to add submenus and menu items to an existing menu. Use submenus to represent groups. Use menu items to represent list pages, content pages, and forms. For more information about how to update an area page, see [How to: Add a List Page to an Area Page](how-to-add-a-list-page-to-an-area-page.md).

## See also

[Menus and Menu Items](menus-and-menu-items.md)

[How to: Add a List Page to the Navigation Pane](how-to-add-a-list-page-to-the-navigation-pane.md)

[List Page Overview](list-page-overview.md)

[Content Page Overview](content-page-overview.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

