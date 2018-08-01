---
title: Details Form User Experience Guidelines
TOCTitle: Details Form
ms:assetid: 2a867e24-2c5c-4a7e-9611-ffd9012a7192
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg886581(v=AX.60)
ms:contentKeyID: 35267947
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# Details Form User Experience Guidelines [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

A *details form* is the primary method for entering data into Microsoft Dynamics AX. A details form allows the user to view data, edit data, and act upon data.

Example of a details form

  
![Details form](images/Aa844397.detail-form-01(en-us,AX.60).png "Details form")Example of a details form

## Design concepts

The following sections describe the design concepts for the structure and elements of a details form.

### View and edit mode

A details form opens in view mode. A user can then click the pencil icons to switch to edit mode. Allowing the user to switch modes prevents unintended changes to the data.

Example of Edit record button and edit mode button

  
![Edit Record button and edit mode button](images/Gg886581.detail-form-02(AX.60).png "Edit Record button and edit mode button")Example of Edit record button and edit mode button

### Action pane

Like a list page, a details form uses an action pane for commands that a user can use in the details form. This similarity will make a details form easier to use.

Example of an action pane

  
![Action pane](images/Gg886581.detail-form-03(AX.60).png "Action pane")Example of an action pane

### Title and summary

To make orientation easy, each details form has a title that contains the record ID and name. The most important information about the record can also be summarized just below the title. This makes it easy for the user to identify the record.

Example of a title and summary

  
![Details form title and summary](images/Gg886581.detail-form-04(AX.60).png "Details form title and summary")Example of a title and summary

### FastTabs

All content of the entity/document is structured into FastTabs that can be expanded and collapsed, allowing for multiple FastTabs to be open at the same time. The FastTabs can contain fields or a grid, and each FastTab can have a local action pane strip.

Example of FastTabs

  
![FastTabs](images/Gg886581.detail-form-05(AX.60).png "FastTabs")Example of FastTabs

In most cases, the system will display two columns of data by default on a FastTab. The user can change the number of columns displayed from one to five columns.

**Summary fields**:

FastTabs can display summary fields. Summary fields display key fields contained on the FastTab to the user so that the user does not have to expand the FastTab.

Example of summary fields

  
![FastTab summary fields](images/Gg886581.detail-form-06(AX.60).png "FastTab summary fields")Example of summary fields

### FactBoxes

Related information is shown in the FactBoxes on the right side of the details form. Each FactBox shows information that is relevant to the record, but that comes from different data sources from both within and outside of the system.

FactBoxes are the same between all modes of a details form (editable list, details, and line details).

Example of FactBoxes

  
![FactBoxes](images/Gg886581.detail-form-07(AX.60).png "FactBoxes")Example of FactBoxes

### Status bar

A details form has a status bar that is updated to display back and forward buttons, a toggle button for view and edit mode, focus-specific Help text, and a **Close** button to close the form.

### Editable list

A details form has an alternate mode, the editable list form. The editable list allows the user to edit the items from the list page within a list on a details form. The rationale for sharing this mode with the details form is one of practicality–the business logic for editing is on the details form.

Example of an editable list

  
![Editable list](images/Gg886581.detail-form-08(AX.60).png "Editable list")Example of an editable list

The user can access the editable list in two ways: the primary way is through the **Edit in grid** command on the list page; the second way is through the status bar icon in the form itself.

## Guidelines

This section includes both general and specific guidelines for a details form. It also includes guidelines about what a details form should not have.

### General guidelines

A details form should open in one of the following ways, depending on how it was initiated:

  - In view mode when the user clicks the **Open** action (or double-clicks a record) from its corresponding list page. This mode does not allow any fields to be edited until the user switches the form to edit mode.

  - In edit mode when the user clicks the **Edit** action from its corresponding list page.

  - In edit in grid mode when the user clicks the **Edit in grid** action from its corresponding list page.

  - In new mode when the user clicks the **New** action from its corresponding list page or from any other place where the **New** action is initiated.

A details form should adhere to the following standard form requirements:

  - All labels in the form should be in sentence case.

  - All labels in the form should be spelled correctly.

  - The window should allow vertical and horizontal resizing.

  - The window should retain its last size when reopened.

  - The window should retain its last position when reopened.

  - The contents of the form should be aligned by using the fewest vertical gridlines possible.

  - No user experience (UX) guidelines should be violated when security is applied for the various roles that have access to this form.

In its default state:

  - The first FastTab should be fully visible without scrolling.

  - The action pane should have no collapsed groups by default when opened in this size.

  - Focus should be on the first editable field on the **General** FastTab.

### Specific guidelines

#### Action pane

A details form should have an action pane at the top that contains the **File** menu on the left side and the **Layout** and **Help** menus on the right side.

  - Labels should be used consistently across all action panes for similar tabs, groups, and actions.

  - Each action should have a unique icon that is used consistently across all action panes for this action.

  - An action pane should have 1 to 10 tabs.

  - No action pane tab should contain all small or all big buttons across all groups.

  - There should be no collapsed groups on the action pane when the application window is 1280 pixels wide.

  - When the details form is resized smaller and there is no longer room to display all of the actions, the groups should collapse, starting with the rightmost groups.

  - There should be from 1 to 8 actions per group.

  - The leftmost group should have a large button as the first item in the group.

**First tab**

The first tab is the home tab. It should have the same name as the entity and should be singular.

  - In view and edit mode, the home tab should contain the **Maintain**, **New**, and **Attachments** groups in the following order.
    
    Home tab in view and edit mode
    
      
    ![Home tab in view and edit mode](images/Gg886581.detail-form-09(AX.60).png "Home tab in view and edit mode")Home tab in view and edit mode

  - In edit in grid mode, the home tab should contain the **Maintain**, **New**, **List**, and **Attachments** groups in the following order.
    
    Home tab in edit in grid mode
    
      
    ![Home tab in edit in grid mode](images/Gg886581.detail-form-10(AX.60).png "Home tab in edit in grid mode")Home tab in edit in grid mode

The **Maintain** group should contain:

  - An **Edit** action.
    
      - In view mode, the **Edit record** action toggles the details form to edit mode.
    
      - In edit mode, the **Edit record** action toggles the details form to view mode.
        

        > [!NOTE]
        > <P>It is intentional that the label is "Edit" in both modes (edit/view).</P>

    
      - In edit in grid mode, the **Edit** action opens another details form in edit mode.
    
      - In edit in detail mode, the label should be “Edit record”.
    
      - In edit in grid mode, the label should be “Edit”.
    
      - In view mode, the icon should be AXID 10040 ![AXID 10040](images/Gg886581.AXID10040(EditGeneric)16x16(AX.60).png "AXID 10040").
    
      - The button should be large.
    
      - The button should be set as a primary action.

  - Optionally, other maintain actions that relate to maintaining the entity that are not related to a specific activity.

  - A **Delete** action that deletes the selected record.
    
      - The icon should be AXID 10121 ![AXID 10121](images/Gg886581.AXID10121(DeleteRed)16x16(AX.60).png "AXID 10121").
    
      - The label should be "Delete".
    
      - The button should be small.
    
      - The button should be set as a primary action.

  - The label of this group should be "Maintain".

The **New** group should contain:

  - The **New** action that opens the details form in new mode. In some cases, it may open a dialog box before opening the details form (two-phase create).
    
      - The label should be "\<name of entity\>" with the \<name of entity\> singular.
    
      - The button should be large.
    
      - The button should be set as a primary action.

  - Optionally, other new actions if there are multiple ways to create a new record.

  - The label of this group should be "New".

Between the **New** and **List** groups, common actions that are not related to a specific activity that is important or used frequently should be displayed.

  - These common actions should be the same actions that are displayed on the list page.

The **List** group should contain:

  - The **Refresh** action that refreshes the contents of the grid.
    
      - The icon should be AXID 11437 ![AXID 11437](images/Gg886581.AXID11437(Refresh)16x16(AX.60).png "AXID 11437").
    
      - The label should be "Refresh".
    
      - The button should be large.
    
      - The button should not be set as a primary action.

  - The **Export to** **Microsoft Excel** action that opens Excel with the contents of the grid.
    
      - The icon should be AXID 10156 ![AXID 10156](images/Gg886581.AXID10156(Excel)16x16(AX.60).png "AXID 10156").
    
      - The label should be "Export to Microsoft Excel".
    
      - The button should be a large button.
    
      - The button should not be set as a primary action.

  - The **List** group should be to the left of the **Attachments** group on the home tab.

  - The label of this group should be "List".

The **Attachments** group should contain the **Attachments** action that opens the **Attachments** form displaying the documents attached to this entity.

  - The icon should be AXID 10442 ![AXID 10442](images/Gg886570.AXID10442(Attachments)16x16(AX.60).png "AXID 10442").

  - The label should be "Attachments".

  - The button should be large.

  - The button should not be set as a primary action.

  - The **Attachment** action should be the rightmost action on the home tab.

  - The label of this group should be "Attachments".

**Activity tabs**

The **Activity** tabs with all actions that relate to a specific activity should be grouped by those activities.

  - These tabs should be given names of activities that the user of this details form would understand. These names should consist of action verbs.
    
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

If there are common, infrequent actions that are not related to a specific activity, they should be displayed on the last tab, which should be named "General".

  - Commands displayed on the **General** tab should not be repeated on other tabs.

#### Page title area

A details form should have a page title area at the top of the page.

**In view and edit mode**:

  - For the name of the record being viewed or edited, the following format should be used: "\<Record ID\> : \<Description\>".

  - The status of the record should be displayed in the upper-right corner of the page title area without a label.

  - One to three fields should be repeated in the page title area in read-only mode to provide context as to which record is being viewed. Note that these fields will never get scrolled out of view.

  - If the entity has no description, then just the ID should be displayed.

  - If the entity has no ID, then just the name or description should be displayed.

**In new mode**:

  - The string "New record" should be displayed.

**In edit in grid mode**:

  - No page title area should be displayed.

#### FastTabs

A master data details form should have FastTabs to group the fields instead of traditional tabs.

  - FastTabs should display summary information.
    
    **Exceptions:**
    
      - FastTabs that contain only a grid are not expected to display summary fields.
    
      - **Dimensions** FastTab pages cannot display summary fields because it is currently not supported.

  - The height of a FastTab should not grow when the details form is resized to be taller.

  - FastTabs should display two columns of fields by default.
    

    > [!NOTE]
    > <P>The user will be able to switch to a three-column layout.</P>



The first FastTab should be the **General** FastTab.

  - The label should be "General".

  - The FastTab should be expanded initially.

  - The **General** FastTab should contain the most important fields for this entity that will be edited most frequently.

  - If the list page for this entity displays a thumbnail image in the Preview pane, this thumbnail image should be displayed on the right side of the **General** FastTab.
    
      - If no image exists for the current record, an empty image should be displayed.

FastTabs that contain an editable grid should have **Add** and **Remove** buttons as the first two actions on the action pane strip above the grid in the FastTab.

For the **Add** button:

  - The icon should be AXID 11421 ![AXID 11421](images/Gg886581.AXID11421(AddGeneric)16x16(AX.60).png "AXID 11421").

  - The label should be "Add".

  - The tooltip should be "Add a new record".

For the **Remove** button:

  - The icon should be AXID 11438 ![AXID 11438](images/Gg886581.AXID11438(RemoveGeneric)16x16(AX.60).png "AXID 11438").

  - The label should be "Remove".

  - The tooltip should be "Remove the selected record".

#### FactBoxes

A details form should have FactBoxes on the right side.

  - A details form should have at least two FactBoxes; however, they can be hidden.

  - The most important FactBox should be placed at the top because the first FactBox will be expanded by default, and the others will be collapsed.

  - All FactBoxes that pertain to data sources on the details form should be added and made invisible so that a user can add the FactBoxes through personalization.

  - All ID fields in a FactBox should be displayed as links that open the corresponding form when clicked.

  - FactBoxes should not display fields that allow a user to enter data by typing with the keyboard.

  - The title should accurately describe the content without being truncated by the default size of the FactBox area.

  - Each numeric field value should be formatted with a thousands separator.

  - A FactBox should not have a visible background or border.

  - The left side of the title should be aligned with the FactBox content.

  - The ID and name of the header or the line whose content is displayed in the FactBox should not be displayed.

#### Status bar

A details form should have a full status bar at the bottom of the form that contains browse buttons, a **View/Edit** toggle button, and a **Close** button.

### What a details form should not have

  - An **Overview** tab.

  - Buttons in a button group on the right side of the form.

  - Regular tabs to display fields.

  - A **Lines** FastTab.

## See also

[Action Pane User Experience Guidelines](action-pane-user-experience-guidelines.md)

[Action Pane Strip User Experience Guidelines](action-pane-strip-user-experience-guidelines.md)

[FastTab User Experience Guidelines](fasttab-user-experience-guidelines.md)

