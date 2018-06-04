---
title: Client Grid User Experience Guidelines
TOCTitle: Client Grid
ms:assetid: ea29e40e-eceb-4d2b-af51-5e68efb32a6b
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg886616(v=AX.60)
ms:contentKeyID: 35267980
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# Client Grid User Experience Guidelines 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Grids in the client provide a way for a user to group a set of records that have similar data into rows and columns. The data in any given column will usually be of the same type. In a grid, a user can select either a single row of information or multiple rows, and can then perform several different actions against the selected rows. Grids can be used with several different patterns in the client, including list pages, inquiry forms, line items within a details form, simple list forms, simple list and details forms, FactBoxes, and enhanced previews.

## Design concepts

Three types of grids are used in the client: editable grids, selection grids, and read-only grids. Each of these types of grids has a unique visual presentation.

**Editable grids**

Editable grids allow a user to edit directly in a cell of the grid. The user can select an individual cell in the grid and update the data. Editable grids are commonly used in simple list forms, details forms, or legacy forms. Visually, editable grids in Microsoft Dynamics AX look like a Microsoft Excel spreadsheet. Actions are performed on the selected cell. To select the entire row, the user must click the check box to the left of the row.

**Selection grids**

Selections grids are essentially read-only grids that have functionality that allows a user to select the entire row. Selection grids are commonly used on list pages. They are also used for the list portion of simple list and details forms and on legacy forms, such as inquiries. Visually, selection grids have alternating row colors. Clicking anywhere in the row will select it.

**Read-only grids**

Read-only grids only display information; the information, displayed in a table format, cannot be selected. Read-only grids are commonly used for FactBoxes and Preview panes used on list pages or for enhanced previews. Visually, a read-only grid does not have any adornment other than the grid’s header. The cells of the grid are the same color as the window’s background, with no line separators between the rows or columns.

## Guidelines

This section includes both general and specific guidelines for client grids.

### General guidelines

Client grids should adhere to the following guidelines:

  - Decide which columns to display and define a simple, short name for each column. Display columns that will help users be confident that they are selecting the correct record.

  - Order the columns so that the most important columns are on the left. Amount columns are most usable for a user when they are placed in the rightmost position in the grid.

  - Include amounts if possible, as follows:
    
      - Display "Total" for documents such as Sales Orders and Purchase Orders.
    
      - Display "Balance" for documents such as Vendor and Customer.
    
      - Display other amounts that are relevant.

  - The default sort order for all grids used anywhere in Microsoft Dynamics AX should be by the natural key. A user must be able to discover how the data is sorted by looking at the standard sorting indicator. For example:
    
      - “ID” for documents (Sales Orders, Purchase Orders, and so on.)
    
      - “Name” for entities (Vendor, Customer, and so on.)
        
        Depending on the scenario, sorting may alternatively be on another column that makes business sense, such as sequence number or date.

  - Icon columns should be used to convey status or a state that a row may be in, for example, workflow, or whether there is an error condition.

### Specific guidelines

This section includes the guidelines for grids in list pages, details forms with lines, simple list forms, simple list and details forms, FactBoxes, and enhanced previews.

#### List page grid

Example of a list page grid

  
![List page grid](images/Gg886616.ClientGrid_01(AX.60).png "List page grid")Example of a list page grid

A list page grid should adhere to the following guidelines:

  - The grid should not be editable.

  - The grid should have between 4 and 10 columns.

  - For transactional entities, the ID field should be the first column, followed by the master entity ID field and the **Name** field. (For bidirectional languages, the order should be reversed.)
    
    **Example**
    
    ![Example of transactional entities fields](images/Gg886616.ListpageC_014(AX.60).png "Example of transactional entities fields")
    
    **Exception**: If the transactions are in a heterogeneous list (mixed types), the grid should be sorted on date (descending).

  - For master entities, the **Name** field should be the first column, followed by the ID field.
    
    **Example**
    
    ![Example of master entities fields](images/Gg886616.ListpageC_015(AX.60).png "Example of master entities fields")

  - Numeric columns should be right-aligned. All other columns should be left-aligned.

  - Each grid should have a visible sort indicator.

  - Right-clicking an item in the grid should display a shortcut menu with **Open** as the first option. Selecting this option should open the details form in view mode.

  - The icon column should be placed on the left side of the grid without a column label. The indication of the icon should come from the tooltip when a user moves the pointer over the icon.

#### Details form with lines grid

Example of details form with lines grid

  
![Details form with lines grid](images/Gg886616.ClientGrid_02(AX.60).png "Details form with lines grid")Example of details form with lines grid

The grid for a details form with lines should adhere to the following guidelines:

  - Mandatory fields should be displayed in the grid.

  - Summary information should not be displayed.
    
    **Exception**: Totals

  - In view mode, double-clicking an item in the grid should expand the line details if it is not already expanded.

There should be an action pane strip above the lines grid that contains:

  - An **Add line** action that adds a new line to the grid.
    
      - The icon should be AXID 10009 ![AXID 10009](images/Gg886570.AXID10009(AddGridLine)16x16(AX.60).png "AXID 10009").
    
      - The label should be “Add line”.
    
      - The button should be set as a primary action.

  - Other actions that add new lines to the grid.
    
    **Example**: Add multiple lines or add sales lines using product configurator.
    
      - The buttons should be set as primary actions.

  - A **Remove** action that deletes the selected line in the grid.
    
      - The icon should be AXID 11400 ![AXID 11400](images/Gg886570.AXID11400(Deleted_line)16x16(AX.60).png "AXID 11400").
    
      - The label should be “Remove”.
    
      - The button should be set as a primary action.

  - An optional **View** action that contains multiple view options for the columns in the lines grid.
    
      - The label should be “View”.
    
      - The button should be set as a primary action.

  - The remaining buttons on the action pane strip should be buttons or menus with all the actions that relate to a specific activity, and they should be grouped by those activities.
    
      - The menu buttons should not have icons.

  - The action pane strip should not have a **Details** action.

#### Simple list grid

Example of a simple list grid

  
![Simple list grid](images/Gg886616.ClientGrid_03(AX.60).png "Simple list grid")Example of a simple list grid

A simple list grid should adhere to the following guidelines:

  - The list should have no more than six columns.

  - The fields in the grid should be editable.

  - Grids should be sorted on the first column in ascending order with a visible sort indicator.

  - A user should be able to select only one record at a time. If records are displayed in grids, no trough (row label) should be displayed because that might cause users to think incorrectly that they can select multiple records.

  - Full gridlines should be designated as mandatory by showing a red squiggly line within the field.

  - When there is no data, the grid should not automatically add a new record.

  - The list should span the width of the form and have no borders.

#### Simple list and details grid

Example of a simple list and details grid

  
![Simple list and details grid](images/Gg886616.ClientGrid_04(AX.60).png "Simple list and details grid")Example of a simple list and details grid

A simple list and details grid should adhere to the following guidelines:

  - A user should not be able to enter information directly into the grid.

  - Grids should be sorted on the first column in ascending order with a visible sort indicator.

  - Grids should display two to four columns. Typically just the ID and Description columns are sufficient.

  - A user should be able to select only one record at a time. If records are displayed in grids, no trough (row label) should be displayed because that might cause users to think incorrectly that they can select multiple records.

  - The default width should be 300 pixels.

  - If the number of fields for the reference data is five or fewer, a grid should be used that shows all columns. Do not use a pane on the right side of the window.

  - When creating a new record, focus should go to the first field in the details form, not to the grid.

  - The columns in the list should be defaulted so that there is no horizontal scroll bar by default.

  - When there is no data, the grid should not automatically add a new record.

#### Grids in list FactBoxes and enhanced previews

Example of a list FactBox

  
![List FactBox](images/Gg886616.details-lines-09(AX.60).png "List FactBox")Example of a list FactBox

A list FactBox grid should adhere to the following guidelines:

  - One to four columns should be displayed, and no columns should be clipped by default.

  - Each column should have a column header.

  - The first column should be displayed as a link that navigates to the appropriate details form.

  - Five to ten rows should be displayed.

  - In numeric columns, field values should be right-aligned. In all other columns, field values should be left-aligned.

Grids in enhanced previews should adhere to the same guidelines as grids in list FactBoxes.

## Labels and text

  - All labels in the grid should be in sentence case.

  - All labels in the grid should be spelled correctly.

  - All labels should be spelled out completely. Abbreviations should not be used unless they are industry standards, such as BOM.

