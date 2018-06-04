---
title: Simple List and Details User Experience Guidelines
TOCTitle: Simple List and Details User Experience Guidelines
ms:assetid: 32b02cd6-2cb2-4726-bcf4-a2545328213b
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg886588(v=AX.60)
ms:contentKeyID: 35267952
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# Simple List and Details User Experience Guidelines 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

A simple list and details form is a single page that contains both list page and details form functionality. It is the recommended pattern for enabling users to view and create reference data.

Simple list and details form

  
![Simple list and details form](images/Gg886616.ClientGrid_04(AX.60).png "Simple list and details form")Simple list and details form

## Overview

Using a simple list and details form to view and create reference data has several advantages over using a list page to access separate details forms:

  - **Simpler navigation** – A user can stay on a single page to view details for multiple records instead of launching multiple details forms from a separate list.

  - **Information context** – A user can quickly see how information in a record will be used because the record’s fields are displayed on the page when the record is selected in the list.

## Design concepts

  - The simple list and details pattern helps users understand the nature of the data they see. When a user selects a record in the list, the details area displays the record’s fields, so the user can quickly see what information the form is designed to accept.

  - In general, the columns in the list grid should be repeated in the details pane to help connect the list and details information for the user.

  - In FastTabs, however, the columns should not be repeated, in order to save space.

  - When showing data of mixed types, hide the fields that are not applicable. This presents a simpler interface to the user.

## Guidelines

This section includes general application design guidelines as well as guidelines specific to the simple list and details form.

### General

The default state of the form should follow these rules:

  - The width of a simple list and details form should be 960 pixels.

  - The height of the forms should be 500 pixels.

  - Focus should be in the first cell of the grid or node of the tree when the form is opened for viewing.

  - The window should allow vertical and horizontal resizing.

  - The window should retain its last size when reopened.

  - The window should retain its last position when reopened.

  - The contents of the form should be aligned by using the fewest vertical gridlines possible.

  - No user experience (UX) guidelines should be violated when security is applied for the various roles that have access to this form.

### Specific

The **window title** is displayed within the window frame and should accurately describe the entity.

  - The window title should be in plural form.

  - If opened from an area page, the window title should have the same text as the text of the label used to launch the form.

  - If the form is opened in the context of another record, another title should be displayed above the list and content area.

The **action pane strip** is at the top of the form that contains the **File** menu on the left and the **View** and **Help** menus on the right. The strip should contain **New** and **Delete** buttons as the first two actions in the action pane.

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

The **simple list or tree control** is on the left side of the form.

  - A user should not be able to enter information directly into the grid or tree control.

  - A user should be able to select only one record at a time. If records are displayed in grids, no trough (row label) should be displayed because that might cause users to think incorrectly that they can select multiple records.

  - Grids should display two to four columns. Typically just the **ID** and **Description** columns are sufficient.

  - Grids should be sorted on the first column in ascending order with a visible sort indicator.

  - The default width should be 300 pixels.

  - If the number of fields for the reference data is five or fewer, you should use a grid that shows all columns. Do not use a pane on the right side of the window.

  - When creating a new record, focus should go to the first field in the details form.

  - The columns in the list, or the width of the tree control should be defaulted so there is no horizontal scroll bar by default.

  - When there is no data, the grid or tree control should not automatically add a new record.

A **splitter** is used between the list and the details sections.

  - When dragging to the right, more space should be given to the list and less space to the details.

  - When dragging to the left, more space should be given to the details section and less space to the list.

  - If there are resizable controls in the details section, such as a grid or a big text field, these fields should grow and shrink as the splitter is moved.

**Title:** Display the ID or name between the action pane strip and the data only when:

  - The user needs context for what they are looking at (for example, Emergency Contacts or Fees).

  - The ID or name is not redundant with other information on the form.

  - Simplicity is a higher priority than consistency.

The **details header** should repeat the columns from the grid. The columns should not be contained in a group because:

  - The header should not scroll.

  - The column information is important.

  - The name of the group would be “General,” which would be meaningless.

  - A group would make the page much more complicated.

The **details** area is the main place where users see data. This section is displayed on the right side of the form.

  - The grid columns or tree node label should be displayed as the first fields at the top of the form in the same order as displayed in the grid or tree control. These should never be in a FastTab.

  - Required fields should be displayed as mandatory, which displays a red squiggly line within the field.

  - If there are more fields than can be displayed in the details section, **FastTabs** should be used to group the fields. However, never use just one FastTab.
    
      - Each FastTab should display summary information.
        
        **Exception:** FastTabs that contain only grids.
    
      - The first FastTab should be expanded by default and all others should be collapsed.
    
      - The height of a FastTab should not grow when the forms is resized to be taller.
    
      - FastTabs should display only two columns of fields.
    
      - FastTabs that contain an editable grid should have an **Add** and a **Remove** button as the first two actions in the action pane strip for the FastTab.
        
          
        For the **Add** button:
        
          - The icon should be AXID 11421 ![AXID 11421](images/Gg886581.AXID11421(AddGeneric)16x16(AX.60).png "AXID 11421").
        
          - The label should be “Add”.
        
          - The tooltip should be “Add a new record”.
        
          
        For the **Remove** button:
        
          - The icon should be AXID 11438 ![AXID 11438](images/Gg886581.AXID11438(RemoveGeneric)16x16(AX.60).png "AXID 11438").
        
          - The label should be “Remove”.
        
          - The tooltip should be “Remove the selected record”.

The **status bar** is at the bottom of the form.

  - The status bar should contain a **Close** button, which closes the form. If there is unsaved information on the form, the user should be prompted to save.

  - A status bar also should contain field help text.

### What a simple list and details form should not have

  - A **Save** button in the action pane strip.

  - An **OK** or **Cancel** button in the lower-right corner of the form.

  - Buttons in a button group on the right side of the form.

  - A Preview pane.

  - FactBoxes.

  - Regular tabs to group fields.

## Labels and text

  - All labels on the form should be in sentence case.

  - All labels on the form should be spelled correctly.

## See also

[Details Form User Experience Guidelines](details-form-user-experience-guidelines.md)

