---
title: Simple List User Experience Guidelines
TOCTitle: Simple List User Experience Guidelines
ms:assetid: 5967ed06-51d0-4a27-806b-f41cc5ddbab0
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg886595(v=AX.60)
ms:contentKeyID: 35267959
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# Simple List User Experience Guidelines 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

A simple list form is a single page that contains list functionality. It is the recommended pattern for enabling users to view and create reference and dependent data.

Simple list form

  
![Simple list form](images/Gg886616.ClientGrid_03(AX.60).png "Simple list form")Simple list form

## Overview

It is simpler for a user to view and create reference and dependent data on a simple list form than it is to perform the same tasks on various details forms accessed from a list page. That is because, with a simple list form, a user can stay on a single page to view all details for multiple records instead of opening multiple details forms from a separate list.

## Design concepts

The simple list pattern helps users understand the nature of the data they see. When a user selects a record in the list, all information related to that record is available to the user.

## Guidelines

This section includes both general and specific guidelines for simple list forms.

### General

A simple list form should follow these rules:

  - A simple list form should have an action pane strip at the top of the form and contain the **File** menu on the left side and the **Layout** and **Help** menus on the right side.

  - A **New** button and a **Delete** button should be the first two actions on the action pane strip.

  - The list should span the full width of the form with no borders.

  - The fields in the grid should be editable.

  - The width of a simple list form should be 640 pixels.

  - Focus should be in the first cell of the grid or node of the tree when the form is opened for viewing.

  - The window should allow vertical and horizontal resizing.

  - The window should retain its last size when reopened.

  - The window should retain its last position when reopened.

  - The contents of the form should be aligned by using the fewest vertical gridlines possible.

  - No user experience (UX) guidelines should be violated when security is applied for the various roles that have access to this form.

### Specific

Guidelines in this section are grouped by screen element.

A **window title** should be displayed within the window frame and should accurately describe the entity.

  - The window title should be in plural form.

  - If opened from an area page, the window title should have the same text as the text of the label used to open the form.

  - If the form is opened in the context of another record, another title should be displayed above the list and content area.

An **action pane strip** should be at the top of the form and contain the **File** menu on the left and the **View** and **Help** menus on the right. The action pane strip should contain **New** and **Delete** buttons as the first two actions.

  - For the **New** button:
    
      - The icon should be AXID 11045 ![AXID 11045](images/Gg886588.AXID11045(NewSparkle)16x16(AX.60).png "AXID 11045").
    
      - The label should be “New”.
    
      - The button should be set as a primary action.

  - For the **Delete** button:
    
      - The icon should be AXID 10121 ![AXID 10121](images/Gg886581.AXID10121(DeleteRed)16x16(AX.60).png "AXID 10121").
    
      - The label should be “Delete”.
    
      - The button should be set as a primary action.

  - For any additional actions:
    
      - Buttons should appear after a separator to the right of the **New** and **Delete** actions.
    
      - Their labels should be used consistently across all action pane strips for similar actions.
    
      - These actions should have tooltips.
    
      - These actions do not need an icon but can optionally have an icon. If the action has an icon, it should be an icon specifically designed for this action.

The **list grid** should adhere to the following guidelines:

  - The list should display up to six columns.

  - The fields in the grid should be editable.

  - Grids should be sorted on the first column in ascending order with a visible sort indicator.

  - A user should be able to select only one record at a time. If records are displayed in grids, no trough (row label) should be displayed because that might cause users to think incorrectly that they can select multiple records.

  - Full gridlines should be designated as mandatory, showing a red squiggly line within the field.

  - When there is no data, the grid should not automatically add a new record.

  - The list should span the full width of the form with no borders.

  - When creating a new record, focus should go to the first field in the details form.

There should be a **status bar** at the bottom of the form.

  - The status bar should contain a **Close** button, which closes the form.

  - The status bar should contain field Help text.

  - If the save fails, a message should be displayed to the user and the form should remain open.

### What a simple list form should not have

  - A **Save** button on the action pane strip.

  - An **OK** or **Cancel** button in the lower-right corner of the form.

  - VCR buttons (**First**, **Previous**, **Next**, and **Last**).

  - Buttons in a button group on the right side of the form.

  - A Preview pane.

  - FactBoxes.

  - Regular tabs to group fields.

## Labels and text

  - All labels on the form should be in sentence case.

  - All labels on the form should be spelled correctly.

## See also

[Simple List and Details User Experience Guidelines](simple-list-and-details-user-experience-guidelines.md)

[Action Pane Strip User Experience Guidelines](action-pane-strip-user-experience-guidelines.md)

[FastTab User Experience Guidelines](fasttab-user-experience-guidelines.md)

[List Page User Experience Guidelines](list-page-user-experience-guidelines.md)

[Details Form User Experience Guidelines](details-form-user-experience-guidelines.md)

