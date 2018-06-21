---
title: Enterprise Portal Toolbar User Experience Guidelines
TOCTitle: Enterprise Portal Toolbar
ms:assetid: 7d855e53-fd2d-413e-85c6-17b4db93a550
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg886600(v=AX.60)
ms:contentKeyID: 35267964
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# Enterprise Portal Toolbar User Experience Guidelines [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The *Enterprise Portal toolbar* is used to show actions that are specific to a grid on a FastTab in a form.

Example of a callout of an Enterprise Portal toolbar

  
![Callout of the Enterprise Portal toolbar](images/Gg886600.EPToolbar01(AX.60).png "Callout of the Enterprise Portal toolbar")Example of a callout of an Enterprise Portal toolbar

## Design concepts

The Enterprise Portal toolbar appears only on a FastTab with a grid. It helps users better understand the relationships between commands available to them for the items in the grid. When a user selects a command on a toolbar, those commands affect only the items for that grid.

## Guidelines

### For view forms

In view forms, the toolbar above the line items grid should not include actions for creating, deleting, or modifying lines. The toolbar above line items grids should only include a **Details** action and any additional actions for opening related information for the selected line item.

![Enterprise Portal toolbar in a view form](images/Gg886600.EPToolbar02(AX.60).png "Enterprise Portal toolbar in a view form")

### For edit forms

In edit forms, any FastTabs that contain a grid that can be edited should include **Add**, **Remove**, and **Details** buttons as the first three actions on the toolbar for that FastTab.

  - For the **Add** button:
    
      - The icon should be AXID 11421 ![AXID 11421](images/Gg886581.AXID11421(AddGeneric)16x16(AX.60).png "AXID 11421").
    
      - The label should be “Add”.
    
      - The tooltip should be “Add a new record”.

  - For the **Remove** button:
    
      - The icon should be AXID 11438 ![AXID 11438](images/Gg886581.AXID11438(RemoveGeneric)16x16(AX.60).png "AXID 11438").
    
      - The label should be “Remove”.
    
      - The tooltip should be “Remove the selected record”.

  - For the **Details** button:
    
      - The icon should be AXID 10010 ![Details button](images/Gg886570.AXID(AX.60).png "Details button").
    
      - The label should be “Details”.
    
      - The tooltip should be “Details for the selected record”.

  - Additional actions for opening related information should appear after the **Add**, **Remove**, and **Details** buttons.
    
    ![Enterprise Portal toolbar in an edit form](images/Gg886600.EPToolbar03(AX.60).png "Enterprise Portal toolbar in an edit form")

### Drop-down menus

  - If there are more than four actions that can be grouped, as is the case with the **Line** and the **Related information** groups, they should be placed in a drop-down menu.

