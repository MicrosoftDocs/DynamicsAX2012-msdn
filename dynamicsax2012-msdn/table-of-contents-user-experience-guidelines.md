---
title: Table of Contents User Experience Guidelines
TOCTitle: Table of Contents
ms:assetid: 6a16fc15-8ee5-49c7-92a5-81850649d077
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg886597(v=AX.60)
ms:contentKeyID: 35267961
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# Table of Contents User Experience Guidelines 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The table of contents (TOC) pattern uses a set of vertical tab buttons down the left side of the page to navigate to content on the right side of the page. The TOC pattern is recommended for setup forms and configuration of groups of information.

The TOC pattern

  
![The TOC pattern](images/Gg886597.toc-00(AX.60).png "The TOC pattern")The TOC pattern

## Overview

  - Setup forms in Microsoft Dynamics AX can unnecessarily complicate navigation of the area page and the Navigation Pane.
    
      - Nearly 80% of the forms in the setup area are related to 4–10 other forms, some of which depend on still more forms, and some of which are entirely optional.
    
      - Opening all of these setup forms in individual windows increases window management problems for users.

  - The setup area is often one of the more complicated navigation areas in the system. But it doesn't have to be since the TOC pattern can help simplify setup navigation.

  - Setup operations often must be performed in a particular sequence. Using the vertical tab structure of the TOC pattern can help users understand where they are in the process and what the next step will be. A simple link does not provide this context.
    
      - Horizontal tabs don't scale well. A large number of horizontal tabs with long text looks clunky.

Consider the Accounts Payable Parameters form in Microsoft Dynamics AX 2009:

A page with a long row of horizontal tabs

  
![A page with a long row of horizontal tabs](images/Gg886597.toc-01(AX.60).png "A page with a long row of horizontal tabs")A page with a long row of horizontal tabs

In the example above, the large number of horizontal tabs causes the form to widen, resulting in a large amount of unused space. This large amount of blank space makes it difficult for users to understand how the command button on the right side of the tab relates to the controls that are grouped together far away on the left side of the tab.

  - Vertical tab button labels can be longer than horizontal tab labels, and vertical tab label text can wrap.

  - Vertical tabs offer richer presentation options. That’s partly because vertical tab button labels can display more text than horizontal tab labels, and also because label text can be generated dynamically. So, for example, you could have a vertical tab label display the date when the data was last modified, or you could have the label indicate whether information entered in the tab is required or optional.

  - Although disabling a horizontal tab button is generally not recommended, there is no such recommendation for vertical tabs.

## Design concepts

This section contains information on vertical tabs, task instructions, the list and details option, and the action pane strip.

### Vertical tabs

A vertical tab control can greatly simplify users’ setup experience by allowing consolidation of multiple setup forms onto a single window.

A TOC page with vertical tabs down the left side

  
![A TOC page with vertical tabs down the left side](images/Gg886597.toc-02(AX.60).png "A TOC page with vertical tabs down the left side")A TOC page with vertical tabs down the left side

### Task instruction

The top of the content area for each page of the setup form should display a task instruction. The instruction text should use the imperative verb form and tell the user what to do on the tab (for example, “Define benefit types”).

### List and details option

If you use a TOC pattern for the navigation area of a page, you should avoid using the list and details pattern for the content pane. That’s because including both a list grid and an editable details pane complicates the page and adds another layer of navigation. If it is possible to fit all the necessary information into a grid, it is not necessary to use a separate details area to edit or input information. Instead, you should just make the grid editable.

A TOC page with a list and details pattern in the content pane

  
![A TOC page with a list and details pattern](images/Gg886597.toc-03(AX.60).png "A TOC page with a list and details pattern")A TOC page with a list and details pattern in the content pane

A list page with an editable grid

  
![A list page with an editable grid](images/Gg886597.toc-04(AX.60).png "A list page with an editable grid")A list page with an editable grid

### Action pane strip

TOC pages should not have an action pane strip or a command bar for the entire page. Instead, an action pane strip should be used within the content panes to provide the actions related to that component. The action pane strip should be located under the content pane’s task instruction.

## Guidelines

This section contains general and specific guidance as well as lists of the items that TOC form should have and should not have.

### General guidelines

  - All labels on the form should be in sentence case.

  - All labels on the form should be spelled correctly.

  - The window should allow vertical and horizontal resizing.

  - The window should retain its last size when reopened.

  - The window should retain its last position when reopened.

  - The contents of the form should be aligned by using the fewest vertical gridlines possible.

  - The File menu should be displayed at the top of the form.

### Specific guidelines

Use a TOC form when these conditions exist:

  - Two or more related forms are used for configuring setup options.

  - The configuration is logically related.

  - Users will need to jump between sections quickly and efficiently.

The default state of the form should follow these rules:

  - The width of the form should be 900 pixels.

  - The height of the form should be 600 pixels.

  - The TOC tab control should be 200 pixels wide.

  - Focus should be in the first editable field of the first tab when the form is opened.

All TOC forms should have:

  - A window title displayed within the window frame. If opened from an area page, the window title should have the same text as the label of the command used to launch the form.

  - A TOC that lists all of the tabs that can be accessed through this form.
    
      - Tabs should appear in the same sequence that is typically used to enter information.
        
          - The **Number sequence** tab should be the last tab page.
        
          - The **Inventory dimensions** tab should be second to last, if needed.
    
      - The first tab button in the list should be highlighted when the form is opened.
    
      - The label of a TOC tab button should be one or two words that clearly describe the content of the corresponding tab. Longer labels result in an inefficient use of screen space, especially when the labels are localized.

  - A content pane that is displayed to the right of the TOC control and below the page title area. The content section can display one of the following patterns for each tab: a simple list form, a simple list and details form, or a simple details form.
    
      - The top of each page should display a page title area.
        
          - The window background color should be white.
        
          - The page area title area should have the following margins: Top=19 pixels, Right=14 pixels, Bottom=14 pixels, and Left=23 pixels.
        
          - There should be no vertical space between the page title area and the page content.
        
          - A main instruction should be displayed for the user.
            
              - Using the correct style properties on these elements in the development environment will render the main instruction with the recommended size and color, so there is no need to hard-code these values:
                
                  - The type size should be 2 points larger than the standard system font.
                
                  - The main instruction should be displayed in the color R:0, G:51, B:153.
        
          - A supplemental instruction should be displayed for the user.
            
            **Exception:** If the supplemental instruction repeats the main instruction with only slightly different wording, do not include it.
            
              - The supplemental instruction should be composed of a complete, concise sentence in sentence case and with ending punctuation.
            
              - A supplemental instruction can be used to present additional information that helps the user understand or use the page.
    
      - A simple list should follow all simple list guidelines.
        
          - The list and associated action pane strip should fill the entire content area of the page below the page title area. No borders should be visible on the grid, and there should be no gaps between the grid and the window borders.
    
      - A simple list and details form should follow all simple list and details guidelines.
        
          - The action pane strip should fill the entire width of the content pane below the page title area with no visible borders or gaps.
        
          - The list should be displayed with no visible border or gaps between the TOC, the bottom of the form, and the action pane strip.
    
      - A simple details form should follow all simple details guidelines.
        
          - The content pane should have a 3D line at the top to separate the page title from the page detail.

  - A simple status bar at the bottom of the form that contains:
    
      - Field Help text.
    
      - A **Close** button that simply closes the form. If there is unsaved information, the system should save it when the form closes.

## What TOC forms should not have:

  - An action pane strip at the top of the form.

  - Buttons in a button group on the right side of the form.

  - A preview pane.

  - FactBoxes.

  - Horizontal tabs to group fields.

  - View mode or read-only data.

