---
title: Enterprise Portal List Page User Experience Guidelines
TOCTitle: Enterprise Portal List Page
ms:assetid: 53e6f13d-0e5c-47fb-82ba-be91b263ee88
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg886593(v=AX.60)
ms:contentKeyID: 35267957
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# Enterprise Portal List Page User Experience Guidelines [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

An Enterprise Portal *list page* presents data on a user interface that is optimized for browsing records, finding the right record, and taking an action upon the record.

Example of an Enterprise Portal list page

  
![Enterprise Portal list page](images/Gg886593.EPListpage_01(AX.60).png "Enterprise Portal list page")Example of an Enterprise Portal list page

## Guidelines

This section includes both general and specific guidelines for an Enterprise Portal list page.

### General guidelines

An Enterprise Portal list page should adhere to the following standard form requirements:

  - All labels in the form should be in sentence case.

  - All labels in the form should be spelled correctly.

  - No user experience (UX) guidelines should be violated when security is applied for the various roles that have access to this form.

### Specific guidelines

#### Navigation Pane

The Navigation Pane of an Enterprise Portal list page should appear on the left side of an Enterprise Portal list page.

  - Links in the Navigation Pane should have the same text as the title of the list page that they point to. (For example, if the target page has a title of “Customers”, the Navigation Pane link to that page should also say “Customers.”)
    
      - There should be one primary list page per entity grouped in a module.

  - The titles of Enterprise Portal list pages as well as the text of the Navigation Pane links that point to those pages should be—or should at least include—a plural noun (for example, “Places,” “Contacts,” “Customers on hold”).

#### Action pane

An action pane should be placed at the top of the form.

  - Labels should be consistent across all action panes for similar tabs, groups, and actions.

  - An icon for an action should be unique and should be used consistently across all action panes for this action.

  - An Enterprise Portal list page should have 1 to 10 tabs.

  - No action pane tab should contain all small or all large buttons.

  - When the list page is resized smaller and there is no longer room to display all of the actions, the action pane groups should collapse, starting with the rightmost groups first.

  - There should be from 1 to 8 actions per group.

  - Actions in an action pane group should be laid out in one of the following configurations.
    
    ![Action pane configuration](images/Gg886570.EPDetailsForm_02(AX.60).png "Action pane configuration")

  - The leftmost group on an action pane should have a large button as the first item in the group.

**First tab**

The first tab on an Enterprise Portal list page is the home tab, which should be selected by default. The label of the first tab should be the same as the entity name. If the entity name is a verb, the label should be in the imperative mood. If the entity name is a noun, it should be singular.

  - The home tab should contain **New**, **Maintain**, **List**, and **Attachments** groups, in the following order.
    
    ![List page home tab](images/Gg886593.EPListpage_03(AX.60).png "List page home tab")

  - The home tab optionally can contain other important common actions.

  - The **New** group should contain:
    
      - The **New** action, which opens the details form in new mode. In some cases, the **New** action may open a dialog box before opening the details form.
        
          - The label should be “\<name of entity\>” and should be a singular noun.
        
          - The button should be large.
        
          - The button should be set as a primary action.

  - The **New** group optionally can contain other new actions if these actions insert a new record into the list.
    
    **Examples**
    
    ![New group on the action pane](images/Gg886593.EPListpage_04(AX.60).png "New group on the action pane")

  - The label of this group should be “New”.

<!-- end list -->

  - The **Maintain** group should:
    
      - Be placed right after the **New** group on the action pane.
    
      - Have a **View** action that is the first action in the group.
        
          - The **View** action should be a large button.
        
          - The **Edit** action should open the details form in edit mode.
            
              - The label should be “Edit”.
            
              - The button should be large.
        
          - The **Maintain** group optionally can contain other **Maintain** actions that relate to maintaining the entity but which are not related to a specific activity.
        
          - The **Delete** action deletes the selected record in the list.
        
          - The icon should be AXID 10121 ![AXID 10121](images/Gg886581.AXID10121(DeleteRed)16x16(AX.60).png "AXID 10121").
        
          - The label should be “Delete”.
        
          - The tooltip should be “Delete the selected \<name of entity\>”. The entity name it refers to should be a plural noun.
        
          - The button should be small.
        
          - The button should be the last button in the **Maintain** group.

  - Groups of one or more important common actions can be placed between the **Maintain** group and the **List** group.
    
      - Common action groups display common actions that do not relate to a specific activity but which are important or used frequently.
        
        **Example**
        
        ![Common actions](images/Gg886593.EPListpage_05(AX.60).png "Common actions")

<!-- end list -->

  - The **Attachments** group should contain the **Attachments** action.
    
      - The **Attachments** action should open the attachments form, which displays the documents attached to this entity.
        
          - The icon should be AXID 10442 ![AXID 10442](images/Gg886570.AXID10442(Attachments)16x16(AX.60).png "AXID 10442").
        
          - The label should be “Attachments”.
        
          - The button should be large.

  - The **Attachments** group should be the rightmost group on the home tab.
    
    **Example**
    
    ![Attachment group example](images/Gg886593.EPListpage_06(AX.60).png "Attachment group example")

  - The label of this group should be “Attachments”.

**Activity tabs**

All actions that relate to a specific activity should be grouped together on activity tabs.

  - Activity tabs should be given activity names that would commonly be used and understood by a list page user. The label of an activity tab should be an action verb.
    
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
    <td><p>For Vendor activity tabs – Purchase, Invoice</p></td>
    </tr>
    <tr class="even">
    <td><p>For Customer activity tabs – Sell, Invoice, Collect, Manage Projects, and Market</p></td>
    </tr>
    <tr class="odd">
    <td><p>For Sales Order activity tabs – Sell, Pick and Pack, and Invoice</p></td>
    </tr>
    </tbody>
    </table>


**General tab**

Common infrequent actions that do not relate to a specific activity should be displayed on the last tab, which should be named “General”.

  - Actions displayed on the **General** tab should not be repeated on other tabs.

  - The **General** tab should be the last tab on the action pane.

The **General** tab for an Enterprise Portal list page should have:

  - A filter for finding data in the list.
    
      - Controls for custom filters should be placed below the list page title and above the grid.

  - A grid to display relevant information about the entity.
    
      - The grid should have 4 to 10 columns.
    
      - For transactional entities, the ID field should be the first column in the grid, followed by the master entity ID, followed by the **Name** field.
        
        **Example**
        
        ![Example of transactional entities fields](images/Gg886593.EPListpage_07(AX.60).png "Example of transactional entities fields")
        
        **Exception:**
        
        If the transactions are in a heterogeneous list (mixed types), the sort should be on date (descending).
    
      - In a list, numeric columns should be right-aligned. All other columns should be left-aligned.
    
      - Each list should have a visible sort indicator in the column header.
    
      - The sort should be on the ID column in descending order for transactions.
    
      - The sort should be on the **Name** column in ascending order for master entities.

#### FactBoxes

**General guidelines for FactBoxes**

For lists that have not been designed as “simple lists,” there should be FactBoxes on the right side of the form.

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Example of when and when not to include FactBoxes</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>A purchase requisitions list page is not a simple list, and therefore requires a Preview pane and FactBoxes.</p></td>
</tr>
<tr class="even">
<td><p>A reports list page is a simple list, and therefore does not require a Preview pane or FactBoxes.</p></td>
</tr>
</tbody>
</table>


  - At least two FactBoxes should be displayed by default.

  - The most important FactBox should be placed at the top because the first FactBox will be expanded by default and the others will be collapsed.

  - All ID fields within a FactBox should be displayed as links that will open the corresponding form when clicked.

  - FactBoxes should not display fields that allow a user to enter data.

  - The title should accurately describe the content of the FactBox, and the title text should not be truncated when the FactBox is displayed at its default size.

  - Each numeric field value should be formatted with a thousands separator.

  - The left side of the title should align with the contents of the FactBox.

  - The ID or name of the header should not be displayed in the FactBox.

**Guidelines for a fields and values FactBox**

  - Two to ten fields should be displayed.

  - Labels should be left-aligned.

  - Numeric, date, and currency indicator field values should be right-aligned to the right side of the FactBox.

  - Text field values should be left-aligned.

  - Each field should have a label.

  - Currency indicator fields should be the last field on the FactBox.

  - Each fields and values FactBox should include a **More** link in the lower-right corner. The link should navigate to an appropriate form for viewing or editing relevant information.
    
    Example of a fields and values FactBox
    
      
    ![Fields and values FactBox](images/Gg886593.EPListpage_08(AX.60).png "Fields and values FactBox")Example of a fields and values FactBox

**Guidelines for a list FactBox**

  - One to four columns should be displayed.

  - Each column should have a column header.

  - The first column should be displayed as a link that navigates to the appropriate details form.

  - Five to ten rows should be displayed.

  - In numeric columns, field values should be right-aligned. In all other columns, field values should be left-aligned.

  - Each list FactBox should have a **More** link in the lower-right corner. The link should navigate to an appropriate list page, simple list, or simple list and details page.
    
    Example of a list FactBox
    
      
    ![List FactBox](images/Gg886593.EPListpage_09(AX.60).png "List FactBox")Example of a list FactBox

**Guidelines for a related documents FactBox**

  - Two to ten related documents should be displayed.

  - These documents should open a primary or secondary list with the same name.

  - The number of documents in a related documents FactBox should be displayed in parentheses.

  - Documents should be displayed in ascending alphabetical order unless some other logical sequence is preferred.
    
    Example of a related documents FactBox
    
      
    ![Related documents FactBox](images/Gg886593.EPListpage_10(AX.60).png "Related documents FactBox")Example of a related documents FactBox

#### Preview pane

An Enterprise Portal list page that is not a simple list should have a Preview pane below the grid. The Preview pane should display additional data about the selected record.

Example of a Preview pane

  
![Preview pane](images/Gg886593.EPListpage_11(AX.60).png "Preview pane")Example of a Preview pane

  - The Preview pane title should display information to allow the user to identify the selected record.
    
      - For master records, the Preview pane should display “\<ID\> : \<name\>” of the selected record.
    
      - For transactions, the Preview pane should display “\<ID or Description\>” of the selected record.
        
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
        <td><p>For items – ESB-005 : Battery</p></td>
        </tr>
        <tr class="even">
        <td><p>For sales orders – 00017_036</p></td>
        </tr>
        </tbody>
        </table>


  - The Preview pane should display:
    
      - The first 10 line items of the selected record.
    
      - No more than 7 columns.
    
      - The same columns that are displayed on the line items grid in the details form.

  - The Preview pane grid should be read-only, and should not have grid lines, alternating line colors, or borders.

  - Entities without line items should display two columns of fields.

  - The Preview pane should display fields that are found on the details form but not in the Enterprise Portal list page grid.

  - ID fields displayed on the Preview pane should be links that open the associated form when clicked.

  - The Preview pane should not display horizontal scroll bars by default when Microsoft Dynamics AX is opened at full screen size in 1280 x 1024 resolution.

  - No fields should be editable or appear to be editable in a Preview pane.

  - A Preview pane should not have buttons or lookups.

