---
title: Action Pane Button Overview
TOCTitle: Action Pane Button Overview
ms:assetid: 14315715-ab82-458c-9daa-a701f87337b6
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc583412(v=AX.60)
ms:contentKeyID: 35240601
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Action Pane Button Overview [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

A Microsoft Dynamics AX action pane button is a control that represents a specific action. A button action is the task or operation that occurs when you click a button. Examples of button actions include opening another form, deleting a specified record, and printing a list of records.

The action pane uses the same button controls as other Microsoft Dynamics AX forms. When you create an action pane button, you populate properties that specify the appearance of the button, how it displays in the action pane, and the action that occurs when the button is clicked.

## Action Pane Button Types

When you add a button to an action pane button group, the application object tree (AOT) enables you to select the following types of buttons:

  - Command button

  - Menu item button

  - Menu button

  - Button

### ![Cc583412.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc583412.collapse_all(en-us,AX.60).gif")Command Button

A command button performs a specified Microsoft Dynamics AX command. Examples of commands include **Export to Excel**, **Print Preview**, **Delete Record**, and **Print**.

### ![Cc583412.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc583412.collapse_all(en-us,AX.60).gif")Menu Item Button

A menu item button opens a specified form in a new window. Use a menu item button when you want to open a detailed form to create or update a record.

### ![Cc583412.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc583412.collapse_all(en-us,AX.60).gif")Menu Button

A menu button is a control that displays a list of buttons. Use a menu button to make buttons available that are rarely used and do not have to be visible in the action pane.

### ![Cc583412.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc583412.collapse_all(en-us,AX.60).gif")Button

The button type does not have a predefined action. Use this button to execute custom X++ code. To create the button action, use the AOT to override the **clicked** method and enter the X++ code that you want to run.

## Action Pane Button Features

Action pane buttons use a set of properties that define the action pane look and behavior. When you create a new action pane button, consider the following action pane button characteristics:

  - Text label

  - Image

  - Size

  - Overflow

  - Position

  - Primary

  - Multiselect

  - Key tips

### ![Cc583412.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc583412.collapse_all(en-us,AX.60).gif")Text Label

All action pane buttons should display a text label. Use the label to identify the button and to briefly describe the action that the button performs. For example, use **Print** to label a command button that prints a list of records.

### ![Cc583412.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc583412.collapse_all(en-us,AX.60).gif")Image

An action pane button displays an image. Use an image that makes the button easy to find and suggests the type of action that the button performs. If you do not supply an image, the button will use the default action pane button image.

When a button is disabled, the action pane automatically displays a shaded version of the icon. For more information about supplying button images, see [How to: Add an Image to an Action Pane Button](how-to-add-an-image-to-an-action-pane-button.md).

### ![Cc583412.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc583412.collapse_all(en-us,AX.60).gif")Size

The action pane supports two sizes of buttons. Use large buttons for the most frequently used tasks in a button group. Use small buttons to represent less frequently used tasks.

### ![Cc583412.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc583412.collapse_all(en-us,AX.60).gif")Overflow

If you have a rarely used button that has to be available but not visible, add that button to the button group overflow menu. The overflow menu provides access to any buttons that are not displayed on the action pane. To access the button, click the overflow menu indicator on the right side of the button group.

Overflow also occurs when the size of the action pane decreases. When the size of the action pane decreases, the buttons that cannot be displayed are automatically added to the button group overflow menu. The button group uses the position of each button and whether a button is a primary button to determine the order in which buttons are added into overflow.

### ![Cc583412.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc583412.collapse_all(en-us,AX.60).gif")Position

The AOT enables you to specify the location of buttons in a button group. When you expand a button group node in the AOT, the AOT displays a list of the buttons in that group. The order of that list determines where each button is located. The first button in the list displays at the left side of the button group. Each subsequent button displays next to or under the previous button.

In addition, the position of a button determines when that button is added to the button group overflow menu. When the size of the action pane decreases, the first buttons added to the overflow menu are the buttons on the right side of the button group. To keep the most frequently used button visible, move that button to the top of the list of buttons in the button group.

### ![Cc583412.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc583412.collapse_all(en-us,AX.60).gif")Primary

A primary button is a button that overrides the position rules that the button group uses to add buttons to the overflow menu. Specify a button as primary when you want that button to be the last button added to button group overflow menu.

### ![Cc583412.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc583412.collapse_all(en-us,AX.60).gif")Multiselect

A multiselect button can be used with more than one record. Use multiselect when a button can perform an action that includes a list of records. For example, a command button that exports a list of records to Microsoft Excel is a common multiselect button.

When a multiselect button displays in the action pane, the button remains enabled when more than one record is selected in the grid. A non-multiselect button is disabled when a second record is selected in the grid.

### ![Cc583412.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc583412.collapse_all(en-us,AX.60).gif")Key Tips

Key tips enable you to click action pane tabs, button groups, and buttons using the keyboard. When you press ALT the action pane displays a letter next to each tab, button group, or button that you can access. To click a button, press the key that represents the button that you want to use.

The key tip letter is automatically created by the action pane. The key tip uses the first letter of the button label.

## Action Pane Button Customization

To use some action pane buttons, you must add X++ code that implements the button action. The following button actions require X++ code:

  - Open a record in a task page.

  - Override the clicked event.

  - Disabling a button.

### ![Cc583412.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc583412.collapse_all(en-us,AX.60).gif")Open a Record in a Task Page

A menu item button is often used to open a list page record in a specified task page. To open a record in the targeted task page, use X++ to add the SysListPageHelper class to the form **init** and **run** methods. The SysListPageHelper class provides methods that simplify the opening of the record in a task page. For more information, see [How to: Create an Action Pane Button](how-to-create-an-action-pane-button.md).

### ![Cc583412.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc583412.collapse_all(en-us,AX.60).gif")Override the Clicked Event

The Button type of an action pane button enables you to execute custom code when the button is clicked. To customize the button, use the AOT to override the **clicked** event and add the X++ code that you want to execute. For more information, see [How to: Create an Action Pane Button](how-to-create-an-action-pane-button.md).

### ![Cc583412.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc583412.collapse_all(en-us,AX.60).gif")Disabling Buttons

A button should be disabled if that button does not apply to the selected record in the list page grid. To control how buttons are enabled and disabled you have to add X++ code that specifies which buttons to enable or disable.

## See also

[List Page Overview](list-page-overview.md)

[How to: Create an Action Pane Button](how-to-create-an-action-pane-button.md)

[Walkthrough: Creating a List Page and Adding an Action Pane](walkthrough-creating-a-list-page-and-adding-an-action-pane.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

