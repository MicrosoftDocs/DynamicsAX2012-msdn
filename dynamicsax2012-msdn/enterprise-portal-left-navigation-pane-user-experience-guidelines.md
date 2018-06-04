---
title: Enterprise Portal Left Navigation Pane User Experience Guidelines
TOCTitle: Enterprise Portal Left Navigation Pane
ms:assetid: 1856cdd9-e298-4351-a245-0fb30d55c2da
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg886575(v=AX.60)
ms:contentKeyID: 35267943
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# Enterprise Portal Left Navigation Pane User Experience Guidelines 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

A user uses the left Navigation Pane to navigate within the current content area. The Navigation Pane is designed with the assumption that a user performs business tasks repeatedly.

## Guidelines

This section contains both general Enterprise Portal left Navigation Pane guidelines, and specific guidelines for the Role center and area page Navigation Panes.

### General guidelines

  - All Navigation Panes should include a module header that displays the name of the current content area. For example, if a user navigates to the Sales area, the module header should display "Sales".

  - The Navigation Pane module header is a clickable link that should point to the default page for the module.

  - The **Places** menu item group should be first group in the Navigation Pane.

  - The menu item group that contains links to reports should be named "Reports".

  - The **Reports** menu item group should be placed last in the Navigation Pane.

  - All items in the Navigation Pane must have unique names:
    
      - The Navigation Pane should not contain a menu item group named "Main lists".
    
      - The Navigation Pane should not contain a menu item group named "Main pages".
    
      - The Navigation Pane should not contain a menu item group named "Browse”.

  - The Navigation Pane should not include links to task forms. For example, an item such as "New Sales Order" should not appear in the Navigation Pane. (The action pane above a list page should be used instead.) The only pages that should be linked to from the Navigation Pane are navigation pages, such as:
    
      - Area pages (that is, the default page for a content area)
    
      - List pages (including **Report** list pages)
    
      - Activity sites

  - A primary list page menu item should have only one level of secondary list page items below it.

  - The maximum number of levels allowed in the Navigation Pane is three, as follows: **Menu Item Group** \> **Primary List Page Menu Item** \> **Secondary List Page Menu Item**.

  - The Navigation Pane should always remain the same within a content area. It should not change when the user navigates within a content area.

  - Each section in the Navigation Pane should contain a maximum of 10 items. If there is a need for more than 10 items, the section should be split into multiple sections if possible.

### Specific guidelines

This section contains the specific guidelines for the Role center Navigation Pane and the area page Navigation Pane.

#### Role center Navigation Pane

  - **Module header** – The module header should display the name of the current location in the top navigation bar. For Role centers, the module name is always “Home”. The module header is also a menu item that links to the Role center page.

  - **Places** – The **Places** group should list page menu items tailored to the user's role. For example, Kevin, the Sales Manager, will see different menu items in this group than Brooke, the HR Assistant. Note that the **Places** group header is not a link.
    
    ![Role center Navigation Pane with callouts](images/Gg886575.EPLeftNavigationPane_01(AX.60).png "Role center Navigation Pane with callouts")

#### Area page Navigation Pane

  - **Module header** – The module header should display the name of the current location in the top navigation bar. For example, for the **Sales** module, the module name should be “Sales”. The module header is also a menu item that links to the default page for the module.

  - **Places** – The **Places** group should contain links to the selected module's list pages and activity sites (optional). Note that the **Places** group header is not a link.
    
      - Secondary list pages should be grouped below their primary list page.
    
      - Links to secondary list pages should be displayed as links indented below the primary list page menu items.
    
      - A primary list page menu item can be expanded and collapsed by clicking the **Expand/Collapse** button to show or hide the secondary list page menu items.

  - **Reports** – This group contains links to **Reports** list pages for the content area. If there are no reports, this section can be omitted.
    
    ![Area page Navigation Pane with callouts](images/Gg886575.EPLeftNavigationPane_02(AX.60).png "Area page Navigation Pane with callouts")

## Labels and text

  - A module header label should be in sentence case.

  - A menu item label should be in sentence case.

