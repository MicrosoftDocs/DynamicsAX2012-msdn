---
title: Web Modules for Enterprise Portal
TOCTitle: Web Modules for Enterprise Portal
ms:assetid: b8644622-c5da-4b78-a319-694a4ce7e312
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc618032(v=AX.60)
ms:contentKeyID: 35246122
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# Web Modules for Enterprise Portal 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

For Enterprise Portal, the Home module and several submodules are already defined. The Home module corresponds to the main site and home page in Enterprise Portal. The submodules for the Home module correspond to the various module sites in Enterprise Portal, such as the Sales site and the Project site.

The following list shows when you can add submodules and menu items to the existing module structure for Enterprise Portal:

  - If you are creating a new module site for Enterprise Portal, you will add a submodule to the Home module in the AOT. This adds a top-level navigation item and also creates a subsite in SharePoint to store the documents for the new module site.

  - If you add a submodule to an existing submodule (such as Sales or Purchase) a menu item will be added in the navigation for the module site. A subsite in SharePoint will also be created to store documents for the new submodule.

  - If you add a menu item to an existing module or submodule, a menu item will be added that will appear in the navigation under the module or submodule. The menu item is used for navigation only. There is no storage in SharePoint associated with the menu item.

