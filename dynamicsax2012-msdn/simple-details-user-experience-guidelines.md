---
title: Simple Details User Experience Guidelines
TOCTitle: Simple Details
ms:assetid: 01a9b5ad-b95f-4049-bfa1-71af0bdf3b36
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg853299(v=AX.60)
ms:contentKeyID: 35267887
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# Simple Details User Experience Guidelines 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

A *simple details form* is a single page that contains details form functionality. It is the recommended pattern for enabling users to view and create reference and dependent data.

Simple details form, simple example

  
![Simple details form, simple example](images/Gg853299.SimpleDetails_01(AX.60).png "Simple details form, simple example")Simple details form, simple example

Simple details form, complex example with grid

  
![Simple details form, complex example with grid](images/Gg853299.SimpleDetails_02(AX.60).png "Simple details form, complex example with grid")Simple details form, complex example with grid

## Overview

Using a simple details form to view and create reference and dependent data has an advantage over using a list page to access separate details forms, as follows:

  - **Simpler navigation** – A user can stay on a single page to view all details for a record.

## Design concepts

The simple detail pattern helps users understand the nature of the data they see. When a user selects a record in the list, all information related to that record is available to the user.

## Guidelines

This section provides both general guidelines and specific guidelines.

### General guidelines

A simple details form should follow these rules:

  - A simple details form should have an action pane strip at the top of the form and contain the **File** menu on the left side and the **Layout** and **Help** menus on the right side.

  - The action pane strip should not have **New** or **Delete** buttons.

  - The details section should span the entire form.

  - If there are more fields that can be displayed in the details section, FastTabs should be used to group the fields. However, never use just one FastTab.

  - The contents of the form should be aligned by using the fewest vertical gridlines possible.

  - No user experience (UX) guidelines should be violated when security is applied for the various roles that have access to this form.

  - The window should allow vertical and horizontal resizing.

  - The window should retain its last size when reopened.

  - The window should retain its last position when reopened.

### Specific guidelines

Guidelines in this section are grouped by screen element.

A **window title** should be displayed within the window frame and should accurately describe the entity.

  - The window title should be in plural form.

  - If opened from an area page, the window title should have the same text as the text of the label used to open the form.

  - If the form is opened in the context of another record, another title should be displayed above the list and content area.

An **action pane strip** should be at the top of the form and contain the **File** menu on the left, and the **View** and **Help** menus on the right.

  - For any additional actions:
    
      - Buttons should appear after a separator.
    
      - Their labels should be used consistently across all action pane strips for similar actions.
    
      - These actions should have tooltips.
    
      - These actions do not need an icon but can optionally have an icon. If the action has an icon, it should be an icon specifically designed for this action.

The **content area** should have the following characteristics:

  - Focus should be in the first field when the form is opened for viewing.

  - Required fields should be displayed as mandatory, with a red squiggly line within the field.

  - If there are more fields than can be displayed in the details section, FastTabs should be used to group the fields. However, never use just one FastTab.

  - Each FastTab should display summary information.
    
    **Exception:** FastTabs that only contain grids.

  - The first FastTab should be expanded by default and all others should be collapsed.

  - The height of a FastTab should not grow when the form is resized to be taller.

  - FastTabs should display only two columns of fields.

  - FastTabs that contain an editable grid should have an **Add** and a **Remove** button as the first two actions on the action pane strip for the FastTab.
    
      - For the **Add** button:
        
          - The icon should be AXID 11421 ![AXID 11421](images/Gg886581.AXID11421(AddGeneric)16x16(AX.60).png "AXID 11421").
        
          - The label should be “Add”.
        
          - The tooltip should be “Add a new record”.
    
      - For the **Remove** button:
        
          - The icon should be AXID 11438 ![AXID 11438](images/Gg886581.AXID11438(RemoveGeneric)16x16(AX.60).png "AXID 11438").
        
          - The label should be “Remove”.
        
          - The tooltip should be “Remove the selected record”.

A **status bar** should be at the bottom of the form.

  - The status bar should contain a **Close** button, which closes the form.

  - A status bar also should contain field Help text.

  - If a save fails, a message should be displayed to the user and the form should remain open.

## Labels and text

  - All labels on the form should be in sentence case.

  - All labels on the form should be spelled correctly.

## See also

[Simple List and Details User Experience Guidelines](simple-list-and-details-user-experience-guidelines.md)

[Action Pane Strip User Experience Guidelines](action-pane-strip-user-experience-guidelines.md)

[FastTab User Experience Guidelines](fasttab-user-experience-guidelines.md)

[Enterprise Portal List Page User Experience Guidelines](enterprise-portal-list-page-user-experience-guidelines.md)

[Details Form User Experience Guidelines](details-form-user-experience-guidelines.md)

