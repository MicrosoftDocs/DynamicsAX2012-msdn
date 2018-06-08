---
title: 'How to: Specify the Default Action for the List Page Grid'
TOCTitle: 'How to: Specify the Default Action for the List Page Grid'
ms:assetid: 96bd228d-c030-4b77-9bb0-e18ae144c3a6
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh457523(v=AX.60)
ms:contentKeyID: 37009278
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Specify the Default Action for the List Page Grid 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

This topic describes how you can use a list page to open a record in another form. The specified form opens when you double-click a record in the list page grid. The following steps show how to use a button to open the form.


> [!WARNING]
> <P>To complete this procedure, you must have a form that can show the data for the specified record. For information about how to create a details form, see <A href="how-to-create-a-details-form.md">How to: Create a Details Form</A>. In addition, you must have a menu item for that form. For information about how to create the menu item for a form, see <A href="how-to-create-menus-and-menu-items.md">How to: Create Menus and Menu Items</A>.</P>



## Specifying the Default Action for the List Page Grid

The following procedures show you how to configure a menu item button and the data grid. The procedures use the form structure and element names that the **ListPage** template uses to create the list page form. For more information about how to use a template to create a list page, see [How to: Create a List Page Form](how-to-create-a-list-page-form.md).

The **ListPage** template creates the Action Pane, action pane tab, button group, and a menu item button named **ViewButton**. In addition, the template sets the **Visible** property of the button to **No**.

If you did not use the **ListPage** template, you must first add the Action Pane, Action Pane tab, button group, and the menu item button. You then configure your menu item button using the steps for the **ViewButton** in the following procedures. For information about how to add an action pane to the form, see [How to: Create an Action Pane](how-to-create-an-action-pane.md).

### To specify the menu item for the ViewButton control

1.  In the AOT, expand the form, expand **Designs**, expand **Design**, and then expand the action pane node.

2.  In the Action Pane node, expand the action pane tab labeled **HomeTab**, expand the button group labeled **MaintainGroup**, right-click the menu item button labeled **ViewButton**, and then click **Properties**.
    
    For example, you can view the **ViewDetails** button of the **CustTableListPage**. To find the button, expand **CustTableListPage**, expand **Designs**, expand **Design**, expand **ActionPaneTab** named **HomeTab**, expand the **ButtonGroup** named MaintainGroup, and then click the **MenuItemButton** named **ViewDetails**.

3.  In the property sheet for the button, click the **MenuItemName** property, and then click the name of the menu item that opens the form you want to use. The form specified by the menu item will open when you double-click a record in the grid.
    
    For example, the **MenuItemName** property of the **ViewDetails** button for the **CustTableListPage** specifies the **CustTableDetails** menu item.

4.  Click the **CopyCallerQuery** property and then click **Yes**.

5.  Right-click the form, and then click **Save**.

### To specify the default action for the grid

1.  In the **Design** node, right-click the grid control, and then click **Properties**.

2.  In the property sheet for the grid, verify that the **DefaultAction** property is set to **ViewButton**.
    
    If you created a button or want to use a different button, expand the drop-down list, and then click the name of that button. For example, the **DefaultAction** property of the grid in the **CustTableListPage** specifies the **ViewDetails** button.

3.  Verify the label that populates the **DefaultActionLabel** property is **Open**. The label appears in the menu you see when you right-click a record in the grid.
    

    > [!NOTE]
    > <P>If you do not specify a value for the <STRONG>DefaultActionLabel</STRONG>, the shortcut menu uses the text or label value from the menu item or button specified by the <STRONG>DefaultAction</STRONG> property.</P>



4.  Right-click the form, and then click **Save**.

After you specify the default action for the grid, you can add fields to the grid control. For information about how to add fields to a list page grid, see [How to: Add Fields to the List Page Grid](how-to-add-fields-to-the-list-page-grid.md).

You might also want to add controls to the action pane. For information about how to add buttons to the action pane of the list page, see [Walkthrough: Creating a List Page and Adding an Action Pane](walkthrough-creating-a-list-page-and-adding-an-action-pane.md).

## See also

[How to: Add Fields to the List Page Grid](how-to-add-fields-to-the-list-page-grid.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

