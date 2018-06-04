---
title: Enterprise Portal Details Form User Experience Guidelines
TOCTitle: Enterprise Portal Details Form
ms:assetid: 16a514fb-8879-4c77-9b28-37e2530cc750
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg886570(v=AX.60)
ms:contentKeyID: 35267934
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# Enterprise Portal Details Form User Experience Guidelines 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

An Enterprise Portal details form is the primary method for entering information into Microsoft Dynamics AX. The details form allows the user to view, edit, and act upon data.

Example of an Enterprise Portal details form

  
![An Enterprise Portal details form](images/Gg886570.EPDetailsForm_01(AX.60).png "An Enterprise Portal details form")Example of an Enterprise Portal details form

## Guidelines

This section includes both general and specific guidelines for an Enterprise Portal details form.

### General guidelines

  - A details form should close and display a message when there is an error on save.

  - Labels should be in sentence case.

  - All labels should be spelled correctly.

  - Fonts, colors, and margins should follow the visual specifications.

  - When security is applied, no user experience (UX) guidelines should be violated.

### Specific guidelines

  - The details form should open in a modal pop-up window.

  - The form should be read-only by default when opened from the record link in the list page or from the **View** action on the list page action pane.
    
      - The form should open in edit mode when the **Edit** action is clicked on its corresponding list page.
    
      - The form should open in new mode when the **New** action is clicked on its corresponding list page or anywhere else that the **New** action is initiated.

  - The first FastTab should be open by default.

  - The **Line Items** FastTab should display five to eight rows.

  - The view and edit forms for the same entity should have the same FastTabs and field groupings.

  - The fields on the FastTabs should be in a two-column format.

  - Window title:
    
      - When opened in **view** mode, the form title should be “View \<entity type\> - \<entity type\>: \<record name or ID\>”.
    
      - When opened in **edit** mode, the form title should be “Edit \<entity type\> - \<entity type\>: \<record name or ID\>”.
    
      - When opened in **new** mode, the form title should be “New \<entity type\>”.

  - In a view form, the first action pane tab should be named “View”.

  - In new or edit forms, the first action pane tab should be named “Edit”.

  - An action pane should be at the top of the form.
    
      - All labels should be used consistently across all action panes for similar tabs, groups, and actions.
    
      - An icon for an action should be unique, and should be used consistently across all action panes for this action.
    
      - No action pane tab should contain all small or all big buttons across all groups.
    
      - There should be one to eight actions per group.
    
      - Action pane groups should lay out the actions using the valid configurations displayed below.
        
        ![Action pane groups](images/Gg886570.EPDetailsForm_02(AX.60).png "Action pane groups")
    
      - The leftmost group should have a large button as the first item in the group.

**View form specifics**

  - On the **view** form action pane, the **Maintain** group should contain the **Edit** and **Close** actions.

  - On the **view** form action pane, the **Close** action should be the last action in the **Maintain** group.

  - In **view** mode, the line items toolbar should not have an action that adds a new line to the line items list.

  - In **view** mode, clicking **Edit** should open the form in edit mode.
    
    ![View form action pane](images/Gg886570.EPDetailsForm_03(AX.60).png "View form action pane")

**Edit form specifics**

  - In the **edit** form, the first tab of the action pane should be named “Edit”.

  - In the **edit** form, the first action pane group should be named “Commit”.

  - On the **edit** form action pane, the **Commit** group should contain the **Save and close** action and the **Close** action.

  - The **line items detail** form action pane should contain a **Save and close** action.

  - The **line items detail** form should be closed when the **Save and close** action is clicked.

  - After clicking **Save and close** in the **edit** form, focus should be given back to the list page from which the entity was opened.
    
    ![Edit form action pane](images/Gg886570.EPDetailsForm_04(AX.60).png "Edit form action pane")

**First tab**

The first tab is the home tab, which should be selected by default. The label of the first tab should be the same as the entity name. If the entity name is a verb, the label should be in imperative mood. (For example, as shown in the image above, you would use “Create” instead of “Creating.”) If the entity name is a noun, it should be singular.

  - There should not be any **New** groups or actions on the details action pane of the first tab.

  - There should be an **Attachments** group at the far right of the action pane.
    
      - The **Attachments** group should be named “Attachments”.
    
      - The **Attachments** action should be named “Attachments”.
    
      - The **Attachments** action should have a large button.
    
      - The icon should be 10442 ![AXID 10442](images/Gg886570.AXID10442(Attachments)16x16(AX.60).png "AXID 10442").

  - There should not be a **Modify** group on any action pane.

  - There should not be a **Delete** action on the action pane for any details form.

**Activity tabs**

  - All actions that relate to a specific activity should be grouped by that activity.

  - Activity tabs should be given names of activities that are used and understood by the user of the details form. These names should be verbs, and they should be in the imperative mood.
    
    **Examples:**
    
    Vendors—Purchase, Invoice
    
    Customers—Sell, Invoice, Collect, Manage Projects, Market
    
    Sales Orders—Sell, Pick and Pack, Invoice

**General tab**

  - If there are common infrequent actions that do not relate to a specific activity, these actions should be grouped on the last tab, named “General”.

  - Commands displayed on the **General** tab should not be repeated on other tabs.

**Line items toolbar**

If the entity contains line items, a toolbar should be placed above the list, and the toolbar should contain **Add**, **Remove**, **Details**, and **Actions** commands, as shown in the following graphic.

![Line items toolbar](images/Gg886570.EPDetailsForm_05(AX.60).png "Line items toolbar")

  - The **Add line** action adds a new line into the list.
    
      - The icon should be AXID 10009 ![AXID 10009](images/Gg886570.AXID10009(AddGridLine)16x16(AX.60).png "AXID 10009").
    
      - The label should be “Add line”.
    
      - The button should be set as a primary action.
    
      - The button should be the first action on the toolbar.

<!-- end list -->

  - The **Remove** action deletes the selected record.
    
      - The icon should be AXID 11400 ![AXID 11400](images/Gg886570.AXID11400(Deleted_line)16x16(AX.60).png "AXID 11400").
    
      - The label should be “Remove”.
    
      - The button should be set as a primary action.

<!-- end list -->

  - The **Details** action opens the details of the line item in a modal pop-up window on top of the details form. The pop-up window should be smaller than the details form, if possible.
    
      - The icon should be AXID 10010 ![Details button](images/Gg886570.AXID(AX.60).png "Details button").
    
      - The label should be “Details”.
    
      - The button should be set as a primary action.
    
      - The **Details** button should be placed after the **Remove** button.
    
      - The tooltip for the button should be “Open details for \<new of entity\>”.
        
          - There should be no other mechanisms—such as hyperlinks or icons in a list column—for viewing details in the lines list.
    
      - Other than **Add**, **Remove**, and **Details**, actions in the line items toolbar are not required to have icons.
    
      - The details form should close when the **Close** action is clicked.

**Line items action pane**

The line items detail mode should have an action pane at the top of the form.

  - The **Attachments** action opens the **Attachments** form that displays the documents attached to this entity.
    
      - The icon should be AXID 10442 ![AXID 10442](images/Gg886570.AXID10442(Attachments)16x16(AX.60).png "AXID 10442").
    
      - The label should be “Attachments”.
    
      - The button should be large.
    
      - The button should not be set as a primary action.

  - The **Attachments** group should always be the rightmost group on the home tab.

  - The label for this group should be “Attachments”.

  - The tooltip for the **Attachment** action on the line item action pane should be “Open/view the documents attached to this \<name of entity\>”.

Details forms in single record mode should use FastTabs to group the fields instead of using traditional tabs.

  - All FastTabs should display summary information when collapsed.
    
    **Exceptions:**
    
      - **Lines** FastTabs—or any other FastTab that contains only a list—cannot display summary fields.
    
      - A **Dimensions** FastTab cannot display summary fields because that functionality is currently not supported.

  - FastTabs should display only two columns of fields.

#### General FastTab

  - The first FastTab should be named “General”.

  - The **General** FastTab should be expanded by default.

  - The **General** FastTab should contain the entity’s most important fields that will be edited most frequently.

#### Lines FastTab

  - If the details form contains line items, the second FastTab should be named “Lines” if the entity has line items.

  - In a transaction form, the **Lines** FastTab should be expanded by default.

  - The **Lines** list should display six to eight line items.

  - The filter pane should not be visible in the **Lines** FastTab; instead, it should be turned off.

#### Commit buttons

  - The view detail form should have a **Close** button on the lower-right side of the form.

  - The edit detail form should have a **Save and close** button and a **Close** button on the lower-right side of the form.

#### Workflow message bar

  - The details form should not have a workflow message bar in the scrollable content area. It should be fixed on the page and be visible at all times.

