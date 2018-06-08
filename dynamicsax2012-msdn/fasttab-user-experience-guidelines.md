---
title: FastTab User Experience Guidelines
TOCTitle: FastTab
ms:assetid: c4370846-6752-4490-bbf4-580caad4540a
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg886606(v=AX.60)
ms:contentKeyID: 35267970
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# FastTab User Experience Guidelines 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

A *FastTab* is a container for data entry controls. A FastTab organizes fields into related chunks. FastTabs are used primarily on task pages such as details forms, dialog forms, simple list and details forms, and table of content forms, where they facilitate data entry.

Example of a form with FastTabs

  
![Form with FastTabs](images/Gg886606.FastTab_01(AX.60).jpg "Form with FastTabs")Example of a form with FastTabs

## Design concepts

Users need an efficient way to enter data into the system and to see a comprehensive overview of the information for a data record. Users need to be able to view essential fields and hide fields that are not relevant. They also need to see actions that are local to a group of fields and distinct from the global commands of the form. A tab would be a good grouping mechanism to give users these features, but because only one tab can be open at one time, users might lose the overview of the data. FastTabs address this problem because more than one FastTab can be expanded in a form, allowing the user to see the content of several FastTabs at the same time.

Stacked FastTabs also allow users to read the form from top to bottom, just as they would a document. Users can easily scroll vertically between the FastTabs by using the keyboard or by using the wheel button on the mouse. Other benefits of using FastTabs include the following:

  - FastTabs can have user-defined summary fields on the FastTab title bar to provide quick access to important fields and to help build context.

  - Because summary fields remain visible when FastTabs are collapsed, the most important information is always available to users.

  - It is easy to expand or collapse FastTabs to see specific content by using either the keyboard or the mouse.

  - FastTabs will retain their expanded or collapsed state for each form. Therefore, if a user closes a form with FastTabs A and B expanded, but FastTab C collapsed, the next time that the user returns to the form, the expansion state for the FastTabs will be the same.

  - Users can personalize the order and visibility of FastTabs to meet their needs.

## Guidelines

This section includes general guidelines for FastTabs and guidelines for summary fields.

### General guidelines

  - FastTabs should be organized based on activity, similar to the way that tabs are organized on an action pane.

  - FastTabs should be used in forms as normal tabs would be used. FastTabs should not be used as a general replacement for tabs. In cases where the user does not need to see more than one tab at the same time or in cases where the content is complex, regular tabs should be used.

  - FastTabs should be ordered by work process rather than by logical content. For example, in a sales order, the first FastTab should be focused on the customer information, and the second FastTab should be focused on the lines. Only after the lines have been presented should some of the information traditionally found on the sales order be presented to the user.

  - Only 2 (or at most 3) columns should be shown on a FastTab. Two columns are optimal for scanability. If content is grouped into three columns, the time to find a particular piece of information will greatly increase. Columns of fields should be aligned across FastTabs.

  - Users should be allowed to choose the number of columns through the **View** menu of the form.

  - Field groups can be included on FastTabs. The general guideline is that there should be no more than 2 to 4 groups of fields on a FastTab.

  - The header of a group should be displayed only if the group contains more than 1 field, and if the label is not the same as one of the field labels.

  - A FastTab should not be tall. In general, the height of a FastTab should be less than 80 percent of its width.

  - The number of FastTabs in a form should be no fewer than 2 and no more than 12.

  - FastTabs should be used only in a details form, a dialog form, a simple list and details form, or a table of contents form.

  - A FastTab with a grid should display 5 lines by default. If the grid has line items, the FastTab should display 8 lines.

### Summary field guidelines

  - Because summary fields are visible when a FastTab is collapsed, summary fields should contain only critical information to help users decide whether they need to expand the collapsed FastTab.

  - If possible, at least one summary field should be defined for a FastTab. This summary field may simply be a status indicator that informs the user how many items are contained on the FastTab or the total number of items.

  - The summary area should not have more than one field of the same type because summary fields are presented without labels.

  - Field names should not consist of multiple lines. Only part of the field name would show when the FastTab is collapsed, which might confuse the user.

  - Summary fields should be chosen based on data that is the most frequently needed or data that is important to the user.

## Labels and text

### For FastTabs

  - FastTab titles should be in sentence case.

  - The naming should be noun-based. Therefore, information related to selling should use the term *Sales*, and information related to purchasing should use the term *Purchases*.

  - Generic labels for FastTabs, such as *Overview*, *General*, or *Details* should be avoided. These labels do not provide the user with any hint as to what the FastTab contains.

### For summary fields

Summary fields should not have labels for the following reasons:

  - **To reduce complexity**. Having labels in this area adds complexity, and therefore reduces readability. If labels were in the header, it would initially make it more readable. But over time, users would become frustrated because they would have to parse the content, which would slow them down.

  - **Because users will gain efficiency over time**. Over time, users will become efficient in knowing what the data is that they are looking at in the summary. Therefore, labels are not needed.

  - **Because of personalization**. Users can personalize summary fields.

## See also

[Action Pane User Experience Guidelines](action-pane-user-experience-guidelines.md)

[Details Form User Experience Guidelines](details-form-user-experience-guidelines.md)

[Dialog Box User Experience Guidelines](dialog-box-user-experience-guidelines.md)

[Simple List and Details User Experience Guidelines](simple-list-and-details-user-experience-guidelines.md)

[Table of Contents User Experience Guidelines](table-of-contents-user-experience-guidelines.md)

