---
title: 'How to: Add Fields to the List Page Grid'
TOCTitle: 'How to: Add Fields to the List Page Grid'
ms:assetid: 03d95263-0472-4abb-97c4-2b5b9b5da22a
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc580813(v=AX.60)
ms:contentKeyID: 35240245
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Add Fields to the List Page Grid [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

You use a grid control to display the list of records retrieved by the list page data source. The grid control is automatically added to the form when you set the **FormTemplate** property to **ListPage**. Before you add fields to the grid, you have to complete the following procedures:

  - You have to create the list page form. For information about how to create a list page form, see [How to: Create a List Page Form](how-to-create-a-list-page-form.md).

  - You have to add the data source to the list page form. For information about how to add a data source, see [How to: Add a Data Source to a Primary List Page](how-to-add-a-data-source-to-a-primary-list-page.md).

### To add fields to the grid

1.  In the AOT, expand the **Forms** node. Find and expand the list page form.

2.  Expand **Designs**, expand **Design**, right-click **Grid**, and then click **Properties**.

3.  To specify the data source for the grid, open the drop down list for the **DataSource** property, and then click the name of the data source.

4.  In the AOT, expand the **Data Sources** node of the list page form, and then follow these steps.
    
    1.  Right-click the data source you specified for the **DataSource** property, and then click **Open New Window**. A separate AOT window opens that contains the specified data source.
    
    2.  Expand the data source, and then expand **Fields**.
    
    3.  To add a field to the grid, drag a field from the window that is displaying data source fields and drop it onto the grid control. A control for that field will be added to the grid. Repeat this step for each data field that you want to appear in the grid.
    
    4.  Close the AOT window that shows the individual data source.

5.  Review the list of fields that you added to the grid. To change the order that fields appear on the grid, drag the individual field controls to the desired location. You can also highlight a field and press ALT+UP ARROW or ALT+DOWN ARROW to move individual fields.

6.  Right-click the form, and then click **Save**.

To view the list page, right-click the form name in the AOT, and then click **Open**. To specify the form that opens when you double-click a record in the grid, see [How to: Specify the Default Action for the List Page Grid](how-to-specify-the-default-action-for-the-list-page-grid.md). For information about how to customize the grid, see [How to: Customize a List Page Grid](how-to-customize-a-list-page-grid.md).

After you have defined the grid contents, you can add controls to the action pane of the list page. For information about how to add buttons to the action pane of the list page, see [Walkthrough: Creating a List Page and Adding an Action Pane](walkthrough-creating-a-list-page-and-adding-an-action-pane.md).

## See also

[Overview of Form Control Types](overview-of-form-control-types.md)

[How to: Add a Control to a Form](how-to-add-a-control-to-a-form.md)

[User Personalization of Forms](user-personalization-of-forms.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

