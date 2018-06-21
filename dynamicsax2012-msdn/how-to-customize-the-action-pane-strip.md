---
title: 'How to: Customize the Action Pane Strip'
TOCTitle: 'How to: Customize the Action Pane Strip'
ms:assetid: 5de9067d-c982-4ac1-8abc-91fecc03e05a
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh538478(v=AX.60)
ms:contentKeyID: 39508911
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Customize the Action Pane Strip [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

When you create a simple list or simple list and details form, the template you use to create the form adds an action pane strip. The action pane strip includes a **New** and **Delete** button. The default buttons enable you to add a record to the list or remove an existing record from the list. However, you might want to change the actions that appear in the action pane strip. The following sections describe the most common types of customizations.

## Adding a Button or Button Separator to the Action Pane Strip

You can add buttons to the action pane strip that appears on the form. You add a button for each action that you want to enable for the current record that appears in the form. For more information about the action pane strip, see [Action Pane Strip Overview](action-pane-strip-overview.md). The following steps show you how to add a button to the action pane strip.

### To add a button to the action pane strip

1.  In the AOT, expand **Forms**, and then expand the form that has the action pane strip you want to modify.

2.  Expand **Designs**, expand **Design**, expand **ActionPane**, expand **ActionPaneTab**, and then expand the **RecordBasics** button group. You should see the existing buttons for that form.
    

    > [!WARNING]
    > <P>If you are working with a form that was not created based on a template, or the form had changed template values, the names and sequence specified in this and the remaining steps might be different.</P>



3.  Right-click the button group control, click **New Control**, and then click **Button**, **CommandButton**, **DropDialogButton**, **MenuButton**, or **MenuItemButton**. The specified button is added to the action pane strip. To learn more about each type of button and the required property values, see [How to: Create an Action Pane Button](how-to-create-an-action-pane-button.md).

4.  To specify where the button appears in the action pane strip, click the button control and then press ALT+UP ARROW or ALT+DOWN ARROW.

5.  To save the change, right-click the form and then click **Save**.

You can also add a button separator that helps organize the buttons that appear in the action pane strip. Typically, you add a separator when you add buttons after the **New** and **Delete** buttons on the action pane strip.

### To add a button separator control to the action pane strip

1.  In the AOT, expand **Forms**, and then expand the form that has the action pane strip you want to modify.

2.  Expand **Designs**, expand **Design**, expand **ActionPane**, expand **ActionPaneTab**, and then expand the **RecordBasics** button group. You should see the existing buttons for that form.

3.  Right-click the button group control, click **New Control**, and then click **Separator**. A separator control is added to the button group.

4.  To specify where the separator appears in the action pane strip, click the separator control and then press ALT+UP ARROW or ALT+DOWN ARROW.
    
    For example, you move the separator to follow the **Delete** button in the list of buttons in the **RecordBasics** button group.

5.  To save the change, right-click the form and then click **Save**.

## Modifying Buttons on the Action Pane Strip

You might find that the action pane strip of a simple list or simple list and details form includes actions that you do not want that form to complete. For example, you might not want the form to create or remove a record. To prevent access to the action, you should remove the **New** or **Delete** button that appears in the action pane strip. The following steps describe how to remove a button from the action pane strip.

### To remove a button from the action pane strip

1.  In the AOT, expand **Forms**, and then expand the form that has the action pane strip you want to modify.

2.  Expand **Designs**, expand **Design**, expand **ActionPane**, expand **ActionPaneTab**, and then expand the **RecordBasics** button group. You should see the buttons for that form.
    
    For example, the default action pane strip for a new simple list or simple list and details form includes two command buttons named **NewButton** and **DeleteButton**.

3.  To delete a button, right-click the button and then click **Delete**. If you are asked to confirm the removal, click **OK**. The button is removed from the button group.
    

    > [!NOTE]
    > <P>If you remove all the buttons from the action pane button group, the action pane strip will no longer appear on the form. To be visible, the action pane strip must include at least one button.</P>



4.  To save the change, right-click the form and then click **Save**.

## See also

[How to: Create a Simple List Form](how-to-create-a-simple-list-form.md)

[How to: Create a Simple List and Details Form](how-to-create-a-simple-list-and-details-form.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

