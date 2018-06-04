---
title: Details Form with Lines User Experience Guidelines
TOCTitle: Details Form with Lines
ms:assetid: 9aeb8e04-9c38-42e9-9566-bfdd2abf473f
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg886601(v=AX.60)
ms:contentKeyID: 35267965
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# Details Form with Lines User Experience Guidelines 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

A *details form with lines* consists of one form that can have two views that the user can toggle between. There is a Header view, which contains all fields that are related to or part of the header. And there is a Line view, which contains the lines grid, line details, and a section with a collection of the most important header fields.

Example of details form with lines

  
![Details form with lines](images/Gg886601.details-lines-00(AX.60).png "Details form with lines")Example of details form with lines

## Design concepts

A user of a details form with lines can use the **Header view** and **Line view** actions in the **Show** group on the action pane of the form to toggle between Header view and Line view.

Example of the Header view and Line view actions

  
![Header view and Line view actions](images/Gg886601.details-lines-01(AX.60).png "Header view and Line view actions")Example of the Header view and Line view actions

### Header view

Header view is the same as the details form layout with FastTabs, displaying all information that is related to the entity header. An important difference is that the **Lines** FastTab (or the old **Lines** tab) has been taken out and moved to Line view. But next to the lines, all header fields are displayed in this view (even if repeated in Line view).

Example of Header view

  
![Header view of a details form with lines](images/Gg886601.details-lines-02(AX.60).png "Header view of a details form with lines")Example of Header view

Header view contains all of the fields of the header of the data. The data should be grouped into FastTabs. For more information about grouping fields, see the [FastTab User Experience Guidelines](fasttab-user-experience-guidelines.md) topic.

Header view is not required if all of the header fields would fit in the header section in Line view. In this case, the **Show** group on the action pane would also be removed.

### Line view

Line view is a combination of a collection of header fields, a lines grid, and line details (the combined view).

Example of Line view

  
![Line view of a details form with lines](images/Gg886601.details-lines-03(AX.60).png "Line view of a details form with lines")Example of Line view

The header fields, lines grid, and line details are divided into three zones in the form. The header fields and the line details can be expanded or collapsed. However, the lines grid will always be visible.

  - **Expandable zone: \<entity\> header fields**
    
    The expandable zone with the header fields should repeat fields from Header view. Candidate fields for this section include the following:
    
      - The mandatory header fields
        
        These are fields in the header that the user must fill in to create the entity's transaction document. These fields should be displayed with the mandatory field indicator, also known as a “red, squiggly line.”
        
        ![Mandatory fields with red, squiggly lines](images/Gg886601.details-lines-04(AX.60).png "Mandatory fields with red, squiggly lines")
    
      - The header fields to complete an order in a fast data entry scenario
        
        If the combined view is used to speed up the data entry scenario by saving the user time to switch between views, all header fields that generally must be filled in should be displayed here.
    
      - The header fields that the user could change, based on line entries
        
        The user might decide to modify certain fields in the header, based on the details entered in the lines during the line entry or after the line entry.
    
      - The header fields that directly affect the lines
    
      - The header fields that serve as defaults for the lines grid, but that are placed in the header
        
        Because they have a direct relation to the lines, they should be placed close to the lines.
        
        **Example**: Requested ship date

<!-- end list -->

  - **Lines grid zone**
    
    The lines grid should contain all of the mandatory columns that need to be entered for line items, plus any columns that are needed to fulfill the key business scenarios. Ideally, horizontal scrolling should not be used. There should be an action panes strip above the lines grid that contains all actions that relate to the document lines.
    
    Example of action pane strip above lines grid
    
      
    ![Lines grid](images/Gg886616.ClientGrid_02(AX.60).png "Lines grid")Example of action pane strip above lines grid
    
    The lines grid is the primary focus of Lines view. Therefore, the user should not be able to collapse it. If the header and the line details are collapsed, the lines grid should take up all of the available space.

  - **Expandable zone: line details**
    
    The expandable zone with the line details should contain the standard tabs with all the details of a selected line. To create a good visual hierarchy, the tab labels should be placed under the tabs.
    
    Example of expandable zone with line details
    
      
    ![Line details](images/Gg886601.details-lines-06(AX.60).png "Line details")Example of expandable zone with line details

## Guidelines

This section includes both general and specific guidelines for a details form with lines. It also includes guidelines about what a details form with lines should not have.

### General guidelines

A details form with lines should open in one of the following ways, depending on how it was initiated:

  - In view mode when the user clicks the **Open** action (or double-clicks on a record) from its corresponding list page. This mode does not allow any fields to be edited until the user switches the form to edit mode, unless the user has changed the default open mode to be **Edit**.

  - In edit mode when the user clicks the **Edit** action from its corresponding list page.

  - In edit in grid mode when the user clicks the **Edit in grid** action from its corresponding list page.

  - In new mode when the user clicks the **New** action from its corresponding list page or any other place where the new action is initiated.
    
      - When opened from a master data list page, details forms with lines should open with the context of the selected entity from the list page.
        
        **Example:** Opening a sales order from the customer list would default to the customer information from the selected customer.

  - In the default view (Line view or Header view), whether opened in view, edit, or new mode.

A details form with lines should adhere to the following standard form requirements:

  - All labels in the form should be in sentence case.

  - All labels in the form should be spelled correctly.

  - The window should allow vertical and horizontal resizing.

  - The window should retain its size when reopened.

  - The window should retain its position when reopened.

  - The contents of the form should be aligned by using the fewest vertical gridlines possible.

  - No user experience (UX) guidelines should be violated when security is applied for the various roles that have access to this form.

In its default state:

  - The action pane should have no collapsed groups by default when opened in this size.

  - There should be no vertical scroll bars in Line view.

  - There should be a minimum of 8 lines visible in the lines grid of Line view.

### Specific guidelines

#### Action pane

A details form with lines should have an action pane at the top that contains the **File** menu on the left side and the **Layout** and **Help** menus on the right side.

  - Labels should be used consistently across all action panes for similar tabs, groups, and actions.

  - Each action should have a unique icon that is used consistently across all action panes for this action.

  - An action pane should have between 1 and 10 tabs.

  - No action pane tab should contain all small or all big buttons across all groups.

  - There should be no collapsed groups on the action pane when the application window is 1280 pixels wide.

  - When the details form with lines is resized smaller and there is no longer room to display all of the actions, the groups should collapse, starting with the rightmost groups.

  - There should be from 1 to 8 actions per group.

  - The leftmost group should have a large button as the first item in the group.

**First tab**

The first tab is the home tab. It should have the same name as the entity, and it should be singular.

  - In view and edit mode, the home tab should contain the **Maintain**, **New**, **Show**, and **Attachments** groups in the following order.
    
    Home tab in view and edit mode
    
      
    ![Home tab in view and edit mode](images/Gg886601.details-lines-11(AX.60).png "Home tab in view and edit mode")Home tab in view and edit mode

  - In edit in grid mode, the home tab should contain the **Maintain**, **New**, **List**, and **Attachments** groups in the following order.
    
    Home tab in edit in grid mode
    
      
    ![Home tab in edit in grid mode](images/Gg886581.detail-form-10(AX.60).png "Home tab in edit in grid mode")Home tab in edit in grid mode

The **Maintain** group should contain:

  - In view and edit mode, an **Edit record** toggle button that, in view mode, toggles the details form with lines between edit mode and view mode.
    
      - The label should be “Edit record”.
    
      - The button should be large.
    
      - The button should be set as a primary action.

  - In edit in grid mode, an **Edit** action that opens the current record in another details form in edit mode.
    
      - The label should be “Edit”.
    
      - The button should be large.
    
      - The button should be set as a primary action.

  - Optionally, other **Maintain** actions that relate to maintaining the entity that are not related to a specific activity.

  - A **Delete** action that deletes the selected record.
    
      - The icon should be AXID 10121 ![AXID 10121](images/Gg886581.AXID10121(DeleteRed)16x16(AX.60).png "AXID 10121").
    
      - The label should be “Delete”.
    
      - The button should be small.
    
      - The button should be set as a primary action.

  - The label of the group should be “Maintain”.

The **New** group should contain:

  - The **New** action that opens the details form with lines in new mode. In some cases, it may open a dialog box before opening the details form with lines (two-phase create).
    
      - The label should be “\<name of entity\>” with the \<name of entity\> singular.
    
      - Each details form with lines should have a custom icon used for the **New** button.
    
      - The button should be large.
    
      - The button should be set as a primary action.

  - Optionally, other **New** actions if there are multiple ways to create a new record.

  - The label of the group should be “New”.

The **Show** group should contain:

  - A **Header view** button that shows the header details view of the details form with lines.
    
      - The icon should be AXID 12133 ![AXID 12133](images/Gg886601.AXID12133(HeaderView)16x16(AX.60).png "AXID 12133").
    
      - The label should be “Header view”.
    
      - The button should be large.
    
      - The button should be set as a primary action.
    
      - The tooltip should be “View and edit header details“.

  - A **Line view** button that shows the combined view of the details form with lines.
    
      - The icon should be AXID 12134 ![AXID 12134](images/Gg886601.AXID12134(LineView)16x16(AX.60).png "AXID 12134").
    
      - The label should be “Line view”.
    
      - The button should be large.
    
      - The button should be set as a primary action.
    
      - The tooltip should be “Create, edit, or view line details and header information“.

  - The label of the group should be “Show”.

  - The **Show** group should not be repeated on multiple tabs.

  - The correct button should be shown in the selected state when the user changes views.

  - The F11 key should be used to activate Line view, and the F12 key should be used to activate Header view.

  - The **Show** group should not be visible when the form is in edit in grid mode.

Between the **Show** and **List** groups, common actions that are not related to a specific activity that is important or used frequently should be displayed.

  - These actions should be the same actions that are displayed on the list page.

![Common actions](images/Gg886601.details-lines-07(AX.60).png "Common actions")

The **List** group should contain:

  - The **Refresh** action that refreshes the contents of the grid.
    
      - The icon should be AXID 11437 ![AXID 11437](images/Gg886581.AXID11437(Refresh)16x16(AX.60).png "AXID 11437").
    
      - The label should be “Refresh”.
    
      - The button should be large.
    
      - The button should not be set as a primary action.

  - The **Export to** **Microsoft Excel** action that opens Excel with the contents of the grid.
    
      - The icon should be AXID 10156 ![AXID 10156](images/Gg886581.AXID10156(Excel)16x16(AX.60).png "AXID 10156").
    
      - The label should be “Export to Microsoft Excel".
    
      - The button should be large.
    
      - The button should not be set as a primary action.

  - The **List** group should be to the left of the **Attachments** group on the home tab.

  - The label of the group should be “List”.

The **Attachments** group should contain the **Attachments** action that opens the **Attachments** form displaying the documents attached to this entity.

  - The icon should be AXID 10442 ![AXID 10442](images/Gg886570.AXID10442(Attachments)16x16(AX.60).png "AXID 10442").

  - The label should be “Attachments”.

  - The button should be large.

  - The **Attachment** action should always be the rightmost action on the home tab.

  - The button should not be set as a primary action.

<!-- end list -->

  - The label of the group should be “Attachments".

**Activity tabs**

The **Activity** tabs with all actions that relate to a specific activity should be grouped by those activities.

  - These tabs should be given names of activities that the user of the details form with lines will understand. The names should consist of action verbs.
    
    <table>
    <colgroup>
    <col style="width: 100%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Examples:</p></th>
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

If there are common infrequent actions that do not relate to a specific activity, the actions should be displayed on the last tab, which should be named “General”.

  - Commands displayed on the **General** tab should not be repeated on other tabs.

#### Page title area

A details form with lines should have a page title area at the top of the page.

**In view and edit mode**

  - For the name of the record being displayed or edited, the following format should be used: “\<Record ID\> : \<Description\>”.

  - If the entity has no description, then just the ID should be displayed.

  - If the entity has no ID, then just the name or description should be displayed.
    
    **Example**: 303 : ABC Builders

  - The status of the record should be displayed in the upper-right corner of the page title area without a label.
    
    ![Record status in upper-right corner of title area](images/Gg886601.details-lines-08(AX.60).png "Record status in upper-right corner of title area")

**In new mode**:

  - The string “New record” should be displayed where “name of entity” is the same as the window title.
    
    **Example**: New purchase order

**In edit in grid mode**:

  - No page title area should be displayed.

#### Header view

In Header view, a details form with lines should contain:

  - FastTabs

  - A Line view

  - FactBoxes

  - A status bar

#### FastTabs

In Header view, a details form with lines should have FastTabs to group the fields instead of traditional tabs.

  - The first FastTab should be fully visible without the user having to scroll.

  - Focus should be on the first editable field on the **General** FastTab.

  - All FastTabs should display summary information.
    
    <table>
    <colgroup>
    <col style="width: 100%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Exceptions:</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>A <strong>Lines</strong> FastTab or any other FastTab that contains only a grid cannot display summary fields.</p></td>
    </tr>
    <tr class="even">
    <td><p>A <strong>Dimensions</strong> FastTab cannot display summary fields because it is currently not supported.</p></td>
    </tr>
    </tbody>
    </table>


  - The height of a FastTab should not grow when the form is resized to be taller.

  - FastTabs should display two columns of fields by default.
    

    > [!NOTE]
    > <P>The user will be able to switch to a three-column layout.</P>



  - The first FastTab should be the **General** FastTab.
    
      - The label should be “General”.
    
      - The FastTab should be expanded initially.
    
      - The **General** FastTab should contain the most important fields for this entity that will be edited most frequently.
    
      - If the list page for this entity displays a thumbnail image in the Preview pane, the thumbnail image should be displayed on the right side of the **General** FastTab.
        
          - If no image exists for the current record, an empty image should be displayed.

  - Additional FastTabs that contain an editable grid should have **Add** and **Remove** buttons as the first two actions on the action pane strip for the FastTab.
    
      - For the **Add** button:
        
          - The icon should be AXID 11421 ![AXID 11421](images/Gg886581.AXID11421(AddGeneric)16x16(AX.60).png "AXID 11421").
        
          - The label should be “Add”.
        
          - The tooltip should be “Add a new record”.
    
    <!-- end list -->
    
      - For the **Remove** button:
        
          - The icon should be AXID 11438 ![AXID 11438](images/Gg886581.AXID11438(RemoveGeneric)16x16(AX.60).png "AXID 11438").
        
          - The label should be “Remove”.
        
          - The tooltip should be “Remove the selected record”.


> [!NOTE]
> <P>If there are not enough fields in Header view for at least two FastTabs, then the Header view may be omitted.</P>



#### Line view

In Line view, there should be three zones, in the following order:

  - An expandable zone named “\<Entity\> header”.

  - A lines grid zone with an action pane strip above the lines grid.

  - An expandable zone named “Line details”.


> [!NOTE]
> <P>The expandable zones should be implemented by using the FastTab control.</P>



**Expandable Zone: \<Entity\> header**

  - The label of the expandable zone should be "\<entity\> header".

  - The maximum number of rows should be six, including fields that span multiple rows and group titles.

  - To optimize the space, there should be a three-column layout, but the user should be able to change it to a two-column layout.

  - There should not be an action pane strip.

  - Summary information can be displayed when this area is collapsed.

  - When the user collapses this area by using the keyboard, focus should go to the last field that had focus in either the lines grid or the line details expandable zone.

**Lines grid zone**

In a lines grid:

  - Mandatory fields should be displayed in the grid.

  - Summary information should not be displayed.
    
    **Exception**: Totals

  - In view mode, double-clicking an item in the grid should expand the line details if it is not already expanded.

There should be an action pane strip above the lines grid that contains:

  - An **Add line** action that adds a new line into the grid.
    
      - The icon should be AXID 10009 ![AXID 10009](images/Gg886570.AXID10009(AddGridLine)16x16(AX.60).png "AXID 10009").
    
      - The label should be “Add line”.
    
      - The button should be set as a primary action.

  - Other actions that create new lines into the grid.
    
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

**Expandable zone: Line details**

  - The label of the expandable zone should be ”Line details”.

  - The maximum number of rows should be seven, including fields that span multiple rows and group titles.

  - Three columns of fields should be displayed by default, but the user should be able to change it to a two-column layout.

  - There can be an action pane strip on each tab of the expandable zone section.

  - Summary information can be displayed, but only for fields that are not in the grid.

  - There should be no mandatory fields or common business use fields.
    
      - Scroll bars can appear on the **Line Detail** tab if needed. There should also be a splitter between the lines grid and the line details, so that they can be scrolled when the splitter is adjusted.
    
      - When the user collapses this area by using the keyboard, focus should go to the last field that had focus in either the lines grid or the header expandable zone.

#### FactBoxes

**General guidelines for FactBoxes on a details form with lines**

  - There should be FactBoxes on the right side of the form.

  - There should be at least two FactBoxes available for the user in the form, but they can be hidden.

  - The most important FactBox should be placed at the top because the first FactBox will be expanded by default and the others will be collapsed.

  - All FactBoxes that pertain to data sources on this details form with lines should be added and made invisible so that the user can add the FactBoxes through personalization.

  - Each ID field in a FactBox should be displayed as a link that opens the corresponding form when clicked.

  - FactBoxes should not display fields that allow the user to enter data by typing with the keyboard.

  - The title of a FactBox should accurately describe the content and should not be truncated when it is displayed in the default size of the FactBox area.

  - Each numeric field value should be formatted with a thousands separator.

  - A FactBox should not have a visible background or border.

  - The left side of the title should be aligned with the FactBox content.

  - The ID and name of the header or the line whose content is displayed in the FactBox should not be displayed.

**For a fields and values FactBox**

  - Two to ten fields should be displayed.

  - The labels should be left-aligned.

  - Numeric, date, and currency indicator field values should be right-aligned to the right side of the FactBox.

  - Text field values should be left-aligned.

  - Each field should have a label.

  - Currency indicator fields should be displayed as the last fields in the FactBox.

  - A fields and values FactBox should have a **More** link in the lower-right corner that navigates to the appropriate form where the user can view more information.
    
    Fields and values FactBox
    
      
    ![Fields and values FactBox](images/Gg853328.ListpageC_016(AX.60).png "Fields and values FactBox")Fields and values FactBox

**For a list FactBox**

  - One to four columns should be displayed, and no columns should be clipped by default.

  - Each column should have a column header.

  - The first column should be displayed as a link that navigates to the appropriate details form.

  - Five to ten rows should be displayed.

  - In numeric columns, field values should be right-aligned. In all other columns, field values should be left-aligned.

  - The list FactBox should have a **More** link in the lower-right corner that navigates to the appropriate list page, simple list form, or simple list and details form.
    
    List FactBox
    
      
    ![List FactBox](images/Gg853328.ListpageC_017(AX.60).png "List FactBox")List FactBox

**For a related documents FactBox**

  - Two to ten related documents should be displayed.

  - These documents should open a primary or secondary list page with the same name.

  - The number of documents in a related documents FactBox should be displayed in parentheses.

  - The documents should be displayed in ascending alphabetical order unless some other logical sequence is preferred.
    
    Related documents FactBox
    
      
    ![Related documents FactBox](images/Gg853328.ListpageC_018(AX.60).png "Related documents FactBox")Related documents FactBox

#### A status bar

  - A details form with lines should have a full status bar at the bottom of the form that contains browse buttons, a **View/Edit** toggle button, and a **Close** button.

### What a details form with lines should not have

  - An **Overview** tab.

  - Buttons in a button group on the right side of the form.

  - Regular tabs to display fields in Header view.

  - A line item grid in Header view.

## See also

[Action Pane User Experience Guidelines](action-pane-user-experience-guidelines.md)

[Action Pane Strip User Experience Guidelines](action-pane-strip-user-experience-guidelines.md)

[FastTab User Experience Guidelines](fasttab-user-experience-guidelines.md)

