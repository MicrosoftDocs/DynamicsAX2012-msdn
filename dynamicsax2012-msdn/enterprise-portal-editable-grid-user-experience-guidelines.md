---
title: Enterprise Portal Editable Grid User Experience Guidelines
TOCTitle: Enterprise Portal Editable Grid
ms:assetid: 4c97fbfa-ecaf-4779-9104-ec8f519fe65e
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg886592(v=AX.60)
ms:contentKeyID: 35267956
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# Enterprise Portal Editable Grid User Experience Guidelines 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The editable grid control allows a user to edit records directly in a lines grid on a task form. By using the editable grid, a user can edit such line items as the following:

  - Sales order line items

  - Purchase requisition line items

  - Expense report line items

Example of an editable grid

  
![Task form with editable grid](images/Gg886592.EPEditableGrid01(AX.60).png "Task form with editable grid")Example of an editable grid

## Overview

### Line item details

In most cases, line items have more fields than can be shown as columns in the lines grid. If the user needs to see the additional details of a line item, the user can click the **Details** button on the toolbar above the grid to open the details form for the selected line item. This will display all the fields of the line item that the user has access to in a modal popover on top of the task form that contains the lines grid.

### Row editing actions

When a row is in edit mode, the grid control can display action buttons specific to the task of editing the data in the row. These actions are displayed after the last data column in the grid.

## Design concepts

Users need an efficient and simple way to edit records inline. The editable grid gives users the flexibility to edit records in-place without losing the context.

## Guidelines

  - The maximum number of rows that should be displayed in the lines grid on a task form is 10.

  - The only row editing actions should be the following:
    
      - **Save** – Saves the changes made to the data in the row to the grid. The changes are also saved when the user selects another row in the grid.
    
      - **Undo** – Clears the changes made to the data in the row and exits edit mode. However, if the data has already been saved, **Undo** is no longer possible.

  - Only the icons for the **Save** and **Undo** actions should be used for the row editing actions.

  - Actions that are not specific to the task of editing the row should not be placed in the grid. Actions such as **New**, **Add**, **Delete**, **Remove**, **Details**, and **Refresh** should be placed on a toolbar above the grid.

## Labels and text

The following text should be used for the tooltips for the row editing actions:

  - The tooltip for the **Save** action should be "Save".

  - The tooltip for the **Undo** action should be "Undo changes".

The button to open line item details should be named "Details".

