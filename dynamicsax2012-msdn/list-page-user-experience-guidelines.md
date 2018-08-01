---
title: List Page User Experience Guidelines
TOCTitle: List Page
ms:assetid: 0dfef204-5e57-4e7c-b9bc-063a5afdb0f0
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg853328(v=AX.60)
ms:contentKeyID: 35267918
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# List Page User Experience Guidelines [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The *list page* presents the primary data of the application on a user interface that is optimized for browsing records, finding the right one, and then taking an action upon that record. The list page takes up the entire application window and lets the user search, filter, sort, and preview the data. A Preview pane below the grid shows additional data about the selected record, while FactBoxes on the right side of the grid show related data for the record. Actions relevant to the record are located on the action pane at the top of the page.

Example of a list page

  
![List page](images/Gg886616.ClientGrid_01(AX.60).png "List page")Example of a list page

There are two types of list pages:

  - **Primary list page** – The primary list page is typically a list of master or transaction data without a filter. In rare cases, a filter is needed for the list page to be meaningful, for example, the **Open Customer Invoices** or **Pending PO Invoices** list page. Primary list pages are displayed in the first level of the Navigation Pane tree.

  - **Secondary list page** – The secondary list page is a list page with a filter and is typically used for a specific activity or status. The title of the page reflects the activity or status, for example, the **Orders to Ship** or **Vendor Invoices Due Today** secondary list page. Secondary list pages are displayed in the second level of the Navigation Pane tree, and there may be a Cue on a Role center for it.

## Overview of the list page

The following sections describe the elements of a list page.

### Action pane

The action pane is displayed at the top of each list page. The action pane displays all the actions that are specific to the list page, and each action can either relate to the selected record or be independent of it.

Example of an action pane

  
![Action pane](images/Gg853328.ListPage09(AX.60).png "Action pane")Example of an action pane

### Page title area

The list page title is displayed below the action pane. For primary list pages, the list page title is the name of the entity. For secondary list pages, the list page title relates to the filter on the list page. If a user-defined filter is active, a filter icon appears on the left side of the list page title. If the filter has not been saved, the title will also be followed with the text “(Unsaved filter)”.

### Filters

A list page has six filter types:

  - **Quick Filter** (above the grid).
    
    ![Quick Filter](images/Gg853328.ListPage03(AX.60).png "Quick Filter")

  - **Filter By Selection** (first button on the Filter toolbar and the shortcut menu for the form). Filter By Selection opens a filter dialog box that filters on the field that is clicked or selected.
    
    ![Filter By Selection](images/Gg853328.ListPage04(AX.60).png "Filter By Selection")

  - **Filter By Grid** (second button on the Filter toolbar). Filter By Grid inserts a row on the top of the grid that can be used for filtering.
    
    ![Filter By Grid](images/Gg853328.ListPage05(AX.60).png "Filter By Grid")

  - **Advanced Filter** (third button on the Filter toolbar). Advanced Filter opens the **Inquiry** form.
    
    ![Advanced Filter](images/Gg853328.ListPage06(AX.60).png "Advanced Filter")

  - **Filter By Field** (appears on the shortcut menu for any field in a form). Filter By Field filters based on the clicked field value.
    
    ![Filter By Field](images/Gg853328.ListPage07(AX.60).png "Filter By Field")

  - **Custom Filter** (application-based – the other filters are client controls). From one to three custom filters can be inserted just below the list page title and be used for filters.
    
    ![Custom Filter](images/Gg853328.ListPage08(AX.60).png "Custom Filter")
    
    Custom filters should be used only for filters that are used frequently and that are necessary to make the list page meaningful. They should only be used if it is not possible to create a secondary list page for each filter option, which is the case, for example, when there are many filter options.

### Grid

The grid on a list page is arranged as follows:

  - The records are displayed in the grid. The grid contains columns and rows. The grid is not editable.

  - Generally, the grid has at least 4 columns, but no more than 10.

  - The most important columns are on the left side of the grid.

  - If the list page has an ID field, the **Name** field is the next field to the right of the ID field. (For bidirectional languages, the order should be reversed.)

  - The default sort order for transactions is descending on the ID column.

  - The default sort order for master entities is ascending on the **Name** column.  
    
    Example of a grid
    
      
    ![Grid](images/Gg853328.ListPage10(AX.60).png "Grid")Example of a grid

### FactBoxes

Related information about the record is displayed in FactBoxes on the right side of the list page. The purpose of FactBoxes is to provide related information about the record, which in many cases is more important than the record itself. For example, details about a customer may not be as interesting as the customer's top purchased items, their payment status, or their past due invoices.

When navigating to another navigation page, such as a list page, from a FactBox, the destination list page should open in the same frame. The previous list page is added to the navigation history.

Example of a FactBox

  
![List FactBox](images/Gg853328.ListpageC_017(AX.60).png "List FactBox")Example of a FactBox

### Preview pane

Additional information about the record is displayed in the Preview pane, which appears below the grid. This information may be necessary to determine whether the correct record has been selected. It also allows the user to see more information about the selected record without needing to open the details form.

  - For master data list pages:
    
      - The Preview pane displays a title for the selected record that includes ID and name.
    
      - Below the title are selected fields that help the user identify and examine the record.

  - For transaction document list pages:
    
      - The Preview pane displays a title for the selected record that includes ID and name.
    
      - Below the title are selected fields that help the user identify and examine the record.
    
      - Transaction data should also show line information in a grid that can have up to seven columns. This helps identify the record, but does not show the entire content of it.

Fields found in the Preview pane should not be repeated in the grid or vice versa.

Example of a Preview pane

  
![Preview pane](images/Gg853328.ListPage11(AX.60).png "Preview pane")Example of a Preview pane

## Design concepts

Users need to find master data and transaction data to initiate their work. They do this by browsing, filtering, and previewing, and they need to determine whether the record is the right one by looking at related data and references. A list page is the place for people to find, analyze, and act on primary data supported by the following features of a list page:

  - A list page uses the entire application window. This means that the user has enough space for a good browsing experience, and that there is room for a preview at the bottom of the page and for related data on the right side of the list page.

  - The action pane displays the relevant actions for the list page in a logical and highly visible way.

  - The filters make it fast and easy to locate the right record.

  - The FactBoxes make sure the user does not have to open additional forms to get important information, such as totals, balances, overdue orders, and email addresses.

  - The Preview pane makes identification of the record easy. The user does not have to open a second window or go to a different tab.

## Guidelines

This section includes both general and specific guidelines for a list page.

### General guidelines

A user should be able to navigate to a list page from one of the following locations:

  - A link in the Navigation Pane with the same name as the list page title. The name should be plural.
    
      - There should be one primary list page per entity grouped in a module.

  - A Role center Cue with the same name as the list page.

A list page should adhere to the following standard form requirements:

  - All labels on the form should be in sentence case.

  - All labels on the form should be spelled correctly.

  - The contents of the form should be aligned by using the fewest vertical gridlines possible.

  - No user experience (UX) guidelines should be violated when security is applied for the various roles that have access to this form.

In its default state:

  - Focus should be in the **Type to filter** field when the list page is opened.

  - Double-clicking the grid should open the details form of the list page in view mode.

### Specific guidelines

#### Action pane

  - A list page should have an action pane at the top of the form.

  - All labels across all action panes for similar tabs, groups, and actions should be used consistently.

  - Each action should have a unique icon that is used consistently across all action panes for this action.

  - An action pane should have between 1 and 10 tabs.

  - An action pane tab should not contain all small or all big buttons.

  - An action pane should have no collapsed groups when the application window is 1280 pixels wide.

  - When the list page is resized smaller and there is no longer room to display all of the actions, the groups should collapse, starting with the rightmost groups.

  - An action pane should have 1 to 8 actions per group.

  - Actions in an action pane group should be laid out in one of the following configurations.
    
    ![Action pane configuration](images/Gg853328.ListpageC_02(AX.60).png "Action pane configuration")

  - The leftmost group should have a large button as the first item in the group.

**First tab**

The first tab is the home tab. It should have the same name as the entity, and it should be singular.

  - The home tab should contain the **New**, **Maintain**, **List**, and **Attachments** groups in the following order. Additionally, it may have common actions between the **Maintain** group and the **List** group.
    
    ![List page home tab](images/Gg853328.ListpageC_04(AX.60).png "List page home tab")

  - The **New** group should contain:
    
      - The **New** action that opens the details form in new mode. In some cases, it may open a dialog box before it opens the details form (two-phase create).
    
      - The label should be “\<name of entity\>” with the \<name of entity\> singular.
    
      - The button should be large.
    
      - The button should be set as a primary action.

  - Optionally, the **New** group should contain other new actions if these actions insert a new record into the list.
    
    **Examples**
    
    ![New group example 1](images/Gg853328.ListpageC_05(AX.60).png "New group example 1") ![New group example 2](images/Gg853328.ListpageC_06(AX.60).png "New group example 2") ![New group example 3](images/Gg853328.ListpageC_07(AX.60).png "New group example 3")

  - The label of the group should be “New”.

The **Maintain** group should contain:

  - The **Edit** action that opens the details form in edit mode.
    
      - The icon should be AXID 10040 ![AXID 10040](images/Gg886581.AXID10040(EditGeneric)16x16(AX.60).png "AXID 10040").
    
      - The label should be “Edit”.
    
      - The button should be large.
    
      - The button should be set as a primary action.

  - The **Edit in grid** action that opens the details form in edit in grid mode displaying all of the records from the list in an editable grid (never in view mode).
    
      - The icon should be AXID 10011 ![AXID 10011](images/Gg853328.AXID10011(EditGridLine)16x16(AX.60).png "AXID 10011") .
    
      - The label should be “Edit in grid”.
    
      - The button should be small.
    
      - The button should be set as a primary action.

  - Optionally, other **Maintain** actions that relate to maintaining the entity that are not related to a specific activity.

  - The **Delete** action that deletes the selected record in the list.
    
      - The icon should be AXID 10121 ![AXID 10121](images/Gg886581.AXID10121(DeleteRed)16x16(AX.60).png "AXID 10121").
    
      - The label should be “Delete”.
    
      - The button should be small.
    
      - The button should be set as a primary action.
        
        **Examples**
        
        ![Maintain group example 1](images/Gg853328.ListpageC_08(AX.60).png "Maintain group example 1") ![Maintain group example 2](images/Gg853328.ListpageC_09(AX.60).png "Maintain group example 2") ![Maintain group example 3](images/Gg853328.ListpageC_010(AX.60).png "Maintain group example 3")

  - The label of the group should be “Maintain”.

**The common actions**

Common actions that do not relate to a specific activity that is important or used frequently should be displayed between the **Maintain** group and **List** group.

![Common actions between Maintain and List groups](images/Gg853328.ListpageC_011(AX.60).png "Common actions between Maintain and List groups")

The **List** group should contain:

  - The **Refresh** action that refreshes the contents of the list page.
    
      - The icon should be AXID 11437 ![AXID 11437](images/Gg886581.AXID11437(Refresh)16x16(AX.60).png "AXID 11437").
    
      - The label should be “Refresh”.
    
      - The button should be large.
    
      - The button should not be set as a primary action.

  - The **Export to Microsoft Excel** action that opens Microsoft Excel with the contents of the list page.
    
      - The icon should be AXID 10156 ![AXID 10156](images/Gg886581.AXID10156(Excel)16x16(AX.60).png "AXID 10156").
    
      - The label should be “Export to Microsoft Excel”.
    
      - The button should be large.
    
      - The button should not be set as a primary action.

<!-- end list -->

  - The **List** group should always be to the left of the **Attachments** group on the home tab.
    
    ![List group example](images/Gg853328.ListpageC_012(AX.60).png "List group example")

  - The label of the group should be “List”.

The **Attachments** group should contain:

  - The **Attachments** action that opens the **Attachments** form that displays the documents attached to this entity.
    
      - The icon should be AXID 10442 ![AXID 10442](images/Gg886570.AXID10442(Attachments)16x16(AX.60).png "AXID 10442").
    
      - The label should be “Attachments”.
    
      - The button should be large.
    
      - The button should not be set as a primary action.

  - The **Attachment** group should always be the rightmost group on the home tab.
    
    ![Attachment group example](images/Gg853328.ListpageC_013(AX.60).png "Attachment group example")

  - The label of the group should be “Attachments”.

**Activity tabs**

All actions that relate to a specific activity should be grouped by those activities.

  - These tabs should be given names of activities that the user of this list page will understand. These names should consist of action verbs.
    
    <table>
    <colgroup>
    <col style="width: 100%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Examples</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Vendors – Purchase, Invoice</p></td>
    </tr>
    <tr class="even">
    <td><p>Customers – Sell, Invoice, Collect, Manage Projects, Market</p></td>
    </tr>
    <tr class="odd">
    <td><p>Sales Orders – Sell, Pick and Pack, Invoice</p></td>
    </tr>
    </tbody>
    </table>


**General tab**

If there are common infrequent actions that do not relate to a specific activity, these actions should be displayed on the last tab that should be named “General”.

  - Commands displayed on the **General** tab should not be repeated on other tabs.

#### Page title area

A list page should have a page title area at the top of the page.

  - For primary list pages, the title should be the name of the entity.
    
    <table>
    <colgroup>
    <col style="width: 100%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Examples</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Sales orders</p></td>
    </tr>
    <tr class="even">
    <td><p>Customers</p></td>
    </tr>
    </tbody>
    </table>


  - For secondary list pages, the title should reflect an activity or status.
    
    <table>
    <colgroup>
    <col style="width: 100%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Examples</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Orders to ship</p></td>
    </tr>
    <tr class="even">
    <td><p>Vendor invoices due today</p></td>
    </tr>
    </tbody>
    </table>


  - The primary list page name should not be a verb or verb phrase.

  - The primary list page name should be plural.

  - The secondary list page should not have the same name as the primary list page that it appears under in the Navigation Pane.

#### Filters

A list page should have a filter that allows the user to filter the list:

  - The filter should have between 4 and 10 columns.

  - Custom filters should be placed directly below the list page title.

#### Grid

A list page should have a grid to display relevant information about the entity:

  - The grid should have between 4 and 10 columns.

  - For transactional entities, the ID field should be the first column, followed by the master entity ID and **Name** fields.
    
    ![Example of transactional entities fields](images/Gg886616.ListpageC_014(AX.60).png "Example of transactional entities fields")
    
    **Exception**
    
    If the transactions are in a heterogeneous list (mixed types), the grid should be sorted on date (descending).

  - For master entities, the **Name** field should be the first column, followed by the ID field.
    
    ![Example of master entities fields](images/Gg886616.ListpageC_015(AX.60).png "Example of master entities fields")

  - Numeric columns should be right-aligned. All other columns should be left-aligned.

  - Each grid should have a visible sort indicator.

  - The grid should be sorted on the ID column in descending order for transactions.

  - The grid should be sorted on the **Name** column in ascending order for master entities.

  - Right-clicking an item in the grid should display a shortcut menu with **Open** as the first option. Selecting this option should open the details form in view mode.

#### FactBoxes

**General guidelines for FactBoxes on a list page**

  - A list page should have at least two FactBoxes.

  - The most important FactBox should be placed at the top because the first FactBox will be expanded by default and the others will be collapsed.

  - All FactBoxes that can be displayed on a list page should be made available so that the user can add FactBoxes through personalization.

  - Each ID field in a FactBox should be displayed as a link that opens the corresponding form when clicked.

  - FactBoxes should not display fields that allow the user to enter data by typing with the keyboard.

  - The title of a FactBox should accurately describe the content and should not be truncated when the FactBox is displayed in the default size of the FactBox area.

  - Each numeric field value in a FactBox should be formatted with a thousands separator.

  - A FactBox should not have a visible background or border.

  - The left side of the title should be aligned with the FactBox content.

  - The ID and name of the header or the line whose content is displayed in the FactBox should not be displayed.

**For a fields and values FactBox**

  - Two to ten fields should be displayed.

  - The labels should be left-aligned.

  - Numeric, date, and currency indicator field values should be right-aligned to the right side of the FactBox.

  - Text field values should be left-aligned.

  - Each field should have a label.

  - Currency indicator fields should be displayed as the last field in the FactBox.

  - A fields and values FactBox should have a **More** link in the lower-right corner that navigates to the appropriate form where the user can view or edit the information.
    
    Example of a fields and values FactBox
    
      
    ![Fields and values FactBox](images/Gg853328.ListpageC_016(AX.60).png "Fields and values FactBox")Example of a fields and values FactBox

**For a list FactBox**

  - One to four columns should be displayed.

  - Each column should have a column header.

  - The first column should be displayed as a link that navigates to the appropriate details form.

  - Five to ten rows should be displayed.

  - In numeric columns, field values should be right-aligned. In all other columns, field values should be left-aligned.

  - A list FactBox should have a **More** link in the lower-right corner that navigates to the appropriate list page, simple list form, or simple list and details form.
    
    Example of list FactBox
    
      
    ![List FactBox](images/Gg853328.ListpageC_017(AX.60).png "List FactBox")Example of list FactBox

**For a related documents FactBox**

  - Two to ten related documents should be displayed.

  - These documents should open a primary or secondary list page with the same name.

  - The number of documents in a related documents FactBox should be displayed in parentheses.

  - The documents should be displayed in ascending alphabetical order unless some other logical sequence is preferred.
    
    Example of a related documents FactBox
    
      
    ![Related documents FactBox](images/Gg853328.ListpageC_018(AX.60).png "Related documents FactBox")Example of a related documents FactBox

#### Preview pane

A list page should have a Preview pane below the grid.

  - The Preview pane should be 250 pixels in height.

  - The Preview pane should include a title.
    
      - The title should display information to allow the user to identify the record.
        
          - For master records, the title should be displayed as “\<ID\> : \<name\>” of the selected record.
        
          - For transactions, the title should be displayed as “\<ID or Description\>”.
            
            <table>
            <colgroup>
            <col style="width: 100%" />
            </colgroup>
            <thead>
            <tr class="header">
            <th><p>Examples</p></th>
            </tr>
            </thead>
            <tbody>
            <tr class="odd">
            <td><p>ESB-005 : Battery</p></td>
            </tr>
            <tr class="even">
            <td><p>00017_036</p></td>
            </tr>
            </tbody>
            </table>


  - For entities that have images associated with them, a thumbnail of the image should be displayed on the right side of the Preview pane.
    
      - The thumbnail image should be 120 x 120 pixels with no image distortion.
    
      - If no image exists for the selected record, an empty image should be displayed.

  - For entities with line items, the Preview pane should display:
    
      - The first 10 line items.
    
      - No more than 7 columns.
    
      - The same columns that are displayed on the line items grid in the details form.
    
      - The grid in a read-only state (no grid lines, no alternating line colors, and no border).

  - For entities without line items, the Preview pane should display two columns of fields.

  - The Preview pane should display fields that are found on the details form but not in the grid.

  - ID fields displayed in the Preview pane should be displayed as links that open the associated form when clicked.

  - The Preview pane should not display horizontal scroll bars by default when Microsoft Dynamics AX is opened full screen in 1280 x 1024 resolution.

  - No field should be editable or appear editable in a Preview pane.

  - No buttons or lookups should be included in a Preview pane.

## Labels and text

  - A list page should have the same title as the title used for the list page in the Navigation Pane.

  - A primary list page should have the name of the master or transaction data type, for example, **Sales Orders** or **Items**.

  - A secondary list page should have a title that explains the filter of the page.

  - The name of this secondary list page can be an activity (for example, “Orders to Ship”) or a categorization of the list page (for example, “Vendor Invoices Due Today” or “Vendor Invoices Past Due”).

  - Related information FactBox lists and the Role center Cue that correspond to the list page should have similar names, if not the same name.

  - A list page name should not use acronyms or abbreviations (if possible), should not be a verb or verb phrase, should be in sentence case, and should always be plural.

  - A list page name should contain the items or objects displayed in the list page. For example, if the records that are displayed in a list page are customer records, then the word "customers" should appear in the list page name.

  - A secondary list page should not have the same name as the primary list page that it appears under in the Navigation Pane, and it should be explanatory enough so that a user can look at the list page name and understand what data is displayed on that list page.
    
    <table>
    <colgroup>
    <col style="width: 100%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Correct example</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Primary list page = Customers; Secondary list page = Customers On Hold</p></td>
    </tr>
    </tbody>
    </table>
    
    <table>
    <colgroup>
    <col style="width: 100%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Incorrect example</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Primary list page = Customers; Secondary list page = On Hold</p></td>
    </tr>
    </tbody>
    </table>


  - Descriptor words should appear after the word that describes the items in the list page.
    
    <table>
    <colgroup>
    <col style="width: 100%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Correct examples</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Vendors Past Due</p></td>
    </tr>
    <tr class="even">
    <td><p>Vendor Invoices Not Paid</p></td>
    </tr>
    <tr class="odd">
    <td><p>Customers On Hold</p></td>
    </tr>
    </tbody>
    </table>
    
    <table>
    <colgroup>
    <col style="width: 100%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Incorrect examples</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Past Due Vendors</p></td>
    </tr>
    <tr class="even">
    <td><p>Not Paid Vendor Invoices</p></td>
    </tr>
    <tr class="odd">
    <td><p>On Hold Customers</p></td>
    </tr>
    </tbody>
    </table>


## See also

[Action Pane User Experience Guidelines](action-pane-user-experience-guidelines.md)

