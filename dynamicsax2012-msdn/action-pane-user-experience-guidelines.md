---
title: Action Pane User Experience Guidelines
TOCTitle: Action Pane
ms:assetid: 150289fd-1387-4d22-83a7-5c7a00b7c977
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg853354(v=AX.60)
ms:contentKeyID: 35267933
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# Action Pane User Experience Guidelines [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

An *action pane* is the part of a form that organizes and displays buttons that represent the actions the form supports. An action is a task or operation that occurs when users click an action pane button. Actions enable users to use data from the current form to perform commands, open related forms, or execute custom X++ code.

Example of an action pane

  
![Action pane](images/Gg847253.ActionPane01(en-us,AX.60).png "Action pane")Example of an action pane

## Overview

An action pane contains the global actions for the following:

  - List pages

  - Details forms

The action pane divides the actions into RoleTailored tabs and groups to make it easy for users to locate the relevant action. The action pane can also contain a **General** tab.

Example of an action pane with callouts

  
![Action pane with callouts](images/Gg853354.ActionPane02(AX.60).png "Action pane with callouts")Example of an action pane with callouts

### Tabs

  - **File menu**
    
    The first tab on an action pane is the **File** menu, which contains general actions for Microsoft Dynamics AX. The content on this menu is the same for all pages and forms.

  - **RoleTailored tabs**
    
    All tabs, except for the **General** tab, are RoleTailored, meaning they are related to an activity or to a set of related activities performed by one or more roles. For example, on the list of sales orders, the **Sell** tab is used by all personas who are performing sales activities (Susan, Michael), and the **Sell** tab contains all the actions they need. The **Collect** tab is used by all personas receiving money from customer and performing invoicing (Arnie, Annie).

  - **Home tab**
    
    The home tab (sometimes referred to as the entity tab) is the first tab and contains common actions that are used by all personas on a frequent basis.

  - **General tab**
    
    The **General** tab is not associated with a specific activity. Instead, it contains actions that are used by all personas on an infrequent basis.
    
    The **General** tab is not intended to be the catch-all location for actions that do not seem to fit in some other place. Every effort should be made to categorize tabs based upon roles, and only infrequently used actions common to all personas should be placed here. Frequent actions common to all personas should be placed on the home tab.

### Groups

Each tab contains groups of actions. The group contains actions that are related by being of a similar type or by belonging to the same process.

### Actions

Actions can be displayed by using big or small buttons. Frequent actions should appear as big buttons. There are three types of buttons: push buttons, drop-dialog buttons, and menu buttons.

  - A push button is a regular button with an icon and a label.

  - A drop-dialog button is a button that will display a form immediately below the button requesting that the user supply additional information and confirm the action.

  - A menu button contains several actions that can be accessed through the drop-down menu on the button.

### Key tips

The tabs and buttons on the action pane are automatically assigned key tips based on the first character of their label. Key tips allow users to access these actions from the keyboard by pressing the Alt key. When the Alt key is pressed when a list page or details form is displayed, the assigned key tip will be displayed for each tab. Pressing an assigned key tip for the tab will display the assigned key tip for the group. Finally, pressing the key tip for the group will display the assigned key tip for the actions in the group.

### Personalization

Users can customize the action pane by hiding the commands that they do not need. They can also move the commands or redisplay commands that they have previously hidden.

### Resizing

The action pane has a build-in resize behavior that hides the actions in drop-down buttons as the page or form shrinks. Hiding is from right to left and is based upon whether an action has been marked as primary or not. Non-primary actions will be placed in the drop-down buttons first. Once all non-primary actions have been placed in the drop-down buttons, the process is repeated again from left to right, this time for the primary actions.

## Design concepts

For each page, the actions that the user can carry out should be displayed in one central location. Some actions are used more frequently than others and should be more easily accessed. Users should easily find the actions that they need, and actions for similar tasks should be found together. Different roles need different sets of actions, and they do not need to see the actions for other roles. An action pane addresses all these issues. Additionally, an action pane resembles the ribbon in Microsoft® Office, making its use familiar to Office users.

## Guidelines

This section includes both general and specific guidelines for an action pane.

### General guidelines

  - All labels across all action panes for similar tabs, groups, and actions should be used consistently.

  - All actions should have a unique icon that is used consistently across all action panes for this action.

  - An action pane should have between 1 and 10 tabs.

  - No action pane tab should contain all small or all big buttons.

  - An action pane should have no collapsed groups when the application window is 1280 pixels wide.

  - When the list page is resized smaller and there is no longer room to display all of the actions, the groups should collapse, starting with the rightmost groups.

  - An action pane should have 1 to 8 actions per group.

  - Actions in an action pane group should be laid out in one of the following configurations.
    
    ![Action pane configuration](images/Gg853328.ListpageC_02(AX.60).png "Action pane configuration")

  - The leftmost group should have a large button as the first item in the group.

### Specific guidelines

**First Tab**

The first tab should be the home tab and should have the same name as the entity. The name should be singular.

  - For list pages, the home tab should contain the **New**, **Maintain**, **List**, and **Attachments** groups in the following order.
    
    ![List page home tab](images/Gg853328.ListpageC_04(AX.60).png "List page home tab")

  - For details forms, the home tab should contain:
    
      - In view and edit mode, a **Maintain**, **New**, and **Attachments** groups in the order shown below.
    
      - In edit in grid mode, a **Maintain**, **New**, **List**, and **Attachments** groups in the order shown below.
        
        ![Details form in view mode](images/Gg853354.ActionPane04(AX.60).png "Details form in view mode") ![Details form in edit in grid mode](images/Gg853354.ActionPane03(AX.60).png "Details form in edit in grid mode")

The **New** group should contain:

  - The **New** action that opens the details form in new mode. In some cases, it may open a dialog box before it opens the details form (two-phase create).
    
      - The label should be “\<name of entity\>” with the \<name of entity\> singular.
    
      - The button should be large.
    
      - The button should be set as a primary action.
    
      - Optionally, other **New** actions if these actions insert a new record into the list.
        
        **Examples**
        
        ![New group example 1](images/Gg853328.ListpageC_05(AX.60).png "New group example 1") ![New group example 2](images/Gg853328.ListpageC_06(AX.60).png "New group example 2") ![New group example 3](images/Gg853328.ListpageC_07(AX.60).png "New group example 3")

  - The label of the group should be “New”.

The **Maintain** group should contain:

  - The **Edit** action that opens the details form in edit mode.
    
      - The icon should be AXID 10040 ![AXID 10040](images/Gg886581.AXID10040(EditGeneric)16x16(AX.60).png "AXID 10040").
    
      - The label should be “Edit”.
    
      - The button should be large.
    
      - The button should be set as a primary action.

  - For a list page only, the **Maintain** group should also include an **Edit in grid** action that opens the details form in edit in grid mode, displaying all of the records from the list in an editable grid (never in view mode).
    
      - The icon should be AXID 10011 ![AXID 10011](images/Gg853328.AXID10011(EditGridLine)16x16(AX.60).png "AXID 10011").
    
      - The label should be “Edit in grid”.
    
      - The button should be small.
    
      - The button should be set as a primary action.

  - Optionally, other **Maintain** actions that relate to maintaining the entity that are not related to a specific activity.

  - The **Delete** action that deletes the selected record in the list.
    
      - The icon should be AXID 10121 ![AXID 10121](images/Gg886581.AXID10121(DeleteRed)16x16(AX.60).png "AXID 10121").
    
      - The label should be “Delete”.
    
      - The button should be small.
    
      - The button should be set as a primary action.
        
        **Examples for a list page**
        
        ![Maintain group example 1](images/Gg853328.ListpageC_08(AX.60).png "Maintain group example 1") ![Maintain group example 2](images/Gg853328.ListpageC_09(AX.60).png "Maintain group example 2") ![Maintain group example 3](images/Gg853328.ListpageC_010(AX.60).png "Maintain group example 3")
        
        **Examples for a details form**
        
        ![Example 1 of Maintain group for detail form](images/Gg853354.detail-form-12(AX.60).png "Example 1 of Maintain group for detail form") ![Example 2 of Maintain group for detail form](images/Gg853354.detail-form-13(AX.60).png "Example 2 of Maintain group for detail form")

  - The label for this group should be “Maintain”.

Between the **Maintain** group and **List** group, common actions that are not related to a specific activity that is important or used frequently should be displayed.

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

  - The **List** group should always be to the left of the **Attachments** group on the home tab.
    
    ![List group example](images/Gg853328.ListpageC_012(AX.60).png "List group example")

  - The label for this group should be “List”.

The **Attachments** group should contain:

  - The **Attachments** action that opens the **Attachments** form that displays the documents attached to this entity.
    
      - The icon should be AXID 10442 ![AXID 10442](images/Gg886570.AXID10442(Attachments)16x16(AX.60).png "AXID 10442").
    
      - The label should be “Attachments”.
    
      - The button should be large.
    
      - The button should not be set as a primary action.

  - The **Attachments** group should always be the rightmost group on the home tab.
    
    ![Attachment group example](images/Gg853328.ListpageC_013(AX.60).png "Attachment group example")

  - The label for this group should be “Attachments”.

**Activity tabs**

All actions that relate to a specific activity should be grouped by those activities.

  - These tabs should be given names of activities that the user of this list page or details form will understand. These names should consist of action verbs.
    
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

  - If there are common infrequent actions that are not related to a specific activity, these actions should be displayed on the last tab that should be named “General”.

  - Actions displayed on the **General** tab should not be repeated on other tabs.

## Labels and text

This section contains general labels and text guidelines for an action pane, and labels and text guidelines for groups and actions.

### General labels and text guidelines

  - Tab titles, group titles, and action labels should be in sentence case.

  - There should be no abbreviations or acronyms on the action pane.

**Activity tabs**

  - Tab titles should be activity-based and be expressed in the imperative mood, for example, Receive, Purchase, and Invoice.
    

    > [!NOTE]
    > <P>The "General" tab name is an exception to this guideline.</P>



  - Tab titles should not exceed 20 characters.

  - Tab titles should not be the same as the title of the list that the tab "lives" in.

The following table has suggested tab names for specific customer model process groups.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Customer model process group</p></th>
<th><p>Suggested tab name</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Analyze Marketplace</p></td>
<td><p>Analyze</p></td>
</tr>
<tr class="even">
<td><p>Develop Marketing Plan / Conduct Campaign</p></td>
<td><p>Market</p></td>
</tr>
<tr class="odd">
<td><p>Establish Sales Forecast</p></td>
<td><p>Forecast</p></td>
</tr>
<tr class="even">
<td><p>Manage Sales Force</p></td>
<td><p>–</p></td>
</tr>
<tr class="odd">
<td><p>Generate Sales / Schedule Customer Activities</p></td>
<td><p>Quote</p></td>
</tr>
<tr class="even">
<td><p>Make the Sale / Process Sales Orders</p></td>
<td><p>Sell</p></td>
</tr>
<tr class="odd">
<td><p>–</p></td>
<td><p>Invoice</p></td>
</tr>
<tr class="even">
<td><p>Product Design / Project Engineering</p></td>
<td><p>Design</p></td>
</tr>
<tr class="odd">
<td><p>Operation Planning</p></td>
<td><p>Schedule</p></td>
</tr>
<tr class="even">
<td><p>–</p></td>
<td><p>Requisition</p></td>
</tr>
<tr class="odd">
<td><p>Purchasing</p></td>
<td><p>Purchase</p></td>
</tr>
<tr class="even">
<td><p>–</p></td>
<td><p>Return</p></td>
</tr>
<tr class="odd">
<td><p>Receiving</p></td>
<td><p>Receive</p></td>
</tr>
<tr class="even">
<td><p>Quality Assurance</p></td>
<td><p>Inspect products</p></td>
</tr>
<tr class="odd">
<td><p>Warehouse Operations</p></td>
<td><p>Manage inventory / Pick and pack</p></td>
</tr>
<tr class="even">
<td><p>Production</p></td>
<td><p>Perform / Produce</p></td>
</tr>
<tr class="odd">
<td><p>Shipping</p></td>
<td><p>Deliver</p></td>
</tr>
<tr class="even">
<td><p>Plan Service / Fulfill Service Contracts /Handle Customer Enquiries</p></td>
<td><p>Manage performance</p></td>
</tr>
<tr class="odd">
<td><p>Deliver Service</p></td>
<td><p>Deliver</p></td>
</tr>
<tr class="even">
<td><p>Project Management</p></td>
<td><p>Manage projects</p></td>
</tr>
<tr class="odd">
<td><p>Pay</p></td>
<td><p>Pay</p></td>
</tr>
<tr class="even">
<td><p>Collect</p></td>
<td><p>Collect</p></td>
</tr>
<tr class="odd">
<td><p>Treasury Management / Capital Assets / Close</p></td>
<td><p>Manage accounts / Manage assets</p></td>
</tr>
<tr class="even">
<td><p>Recruit Workforce /Retain Workforce</p></td>
<td><p>Manage workers</p></td>
</tr>
<tr class="odd">
<td><p>Motivate Workforce</p></td>
<td><p>–</p></td>
</tr>
<tr class="even">
<td><p>Manage Organization</p></td>
<td><p>Manage organization</p></td>
</tr>
</tbody>
</table>


### Groups labels and text guidelines

  - Group titles that are named after an activity should be in the imperative mood.

  - Group titles should not have the same title as the tab that the group "lives" in.

  - Group titles should be only one or two words and should not exceed 20 characters.

### Actions labels and text guidelines

  - Action button names should be in sentence case and should use as few prepositions and conjunctions as possible without losing the meaning of the button.

  - The action buttons should generally carry out actions and have names to match those actions. The purpose is to ensure that users understand what action they will invoke by clicking a button.

  - The following prefixes should not be used in an action button label if users can view, edit, and add in the form:
    
      - Open
    
      - View
    
      - Edit
    
      - Modify
    
      - Add
    
    Instead, the action should just be named after the content it is showing. For example, it should be named "Customer" if the customer who is related to the record can be viewed but also edited.

  - If the form allows only viewing, then the prefix “View” can be used in the action label.

  - If the action is a specific action in which the user is adding an item, then the prefix “Add” can be used in the action label.

  - An action that points to another list should use plural in the action label if possible.
    
    **Example**: The action "Purchase Orders" in the **Related Information** group uses plural in the action label.

  - Action labels should inherit the same name as other buttons or actions that link to the same menu item.
    
    **Exception**: If the existing name is ambiguous or misleading, the text properties of the action label should be changed, but UI text in existing forms should not be modified. (The menu item name should not be changed.)

  - Action labels should not exceed 25 characters.

  - Action button names for buttons in the **New** group should be nouns. For example, use "Customer" instead of "Create customer."

