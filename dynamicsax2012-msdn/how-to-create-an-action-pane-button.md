---
title: 'How to: Create an Action Pane Button'
TOCTitle: 'How to: Create an Action Pane Button'
ms:assetid: 8385cf53-09a6-4517-b674-b81b97afa7ef
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc601712(v=AX.60)
ms:contentKeyID: 35246156
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Create an Action Pane Button [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

A Microsoft Dynamics AX action pane button is a control that performs a specified action when it is clicked. The list page action pane displays buttons that represent each task and operation that the list page supports.

Before you add a button to a list page, the list page must have an action pane, action pane tab, and action pane button group. For more information about how to add an action pane to a list page, see [Walkthrough: Creating a List Page and Adding an Action Pane](walkthrough-creating-a-list-page-and-adding-an-action-pane.md).

The following procedures show how to use the AOT to create the following button types:

  - A command button that performs a Microsoft Dynamics AX command. In this procedure you will learn how to add a command button that deletes a record.

  - A menu item button that opens a task page in a new window.

  - A menu button that displays a list of buttons.

  - A button that executes custom code. In this procedure you will learn how to create a button that displays whether the list page can obtain records from more than one company.

## Creating a Command Button

In this procedure, you will add a command button that deletes a record.

### To add a command button

1.  In the AOT, expand **Forms**, and then expand the form node.

2.  To view the action pane, expand **Designs**, and then expand the **Design** node.

3.  Expand the action pane, expand the action pane tab, and expand the button group that will contain the new button. Right-click the button group control, click **New Control**, and then click **CommandButton**. A new button control is added to the button group.

4.  To specify the location of the button in the button group, use the ALT+UP ARROW or ALT+DOWN ARROW to position the button before or after an existing button.

5.  To view the button's properties, expand the button group, right-click the **CommandButton** node, and then click **Properties.** The button properties window opens and displays the default values. You can customize the button by replacing default property values with new values. For a command button, provide values for the following properties.
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Property</p></th>
    <th><p>Value</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><strong>Big</strong></p></td>
    <td><p>Click <strong>Yes</strong> to make the button a large button.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>ButtonDisplay</strong></p></td>
    <td><p>Specify how the button displays its text and image. For example, a large action pane button typically uses <strong>Text &amp; Image above</strong>.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Command</strong></p></td>
    <td><p>Specify the command that you want the button to perform when it is clicked. For example, click <strong>Delete Record</strong> for a button that deletes a record.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>ForcedToOverflow</strong></p></td>
    <td><p>Specify whether the button should always be in the button group overflow menu. Click <strong>Yes</strong> to add it to the overflow menu.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>ImageLocation</strong></p></td>
    <td><p>Specify the location of the image that you want to appear on the button. You can click <strong>File</strong>, <strong>AOTResource</strong>, or <strong>EmbeddedResource</strong>.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>MultiSelect</strong></p></td>
    <td><p>Click <strong>Yes</strong> to use the command when there is more than one highlighted record in the grid.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Name</strong></p></td>
    <td><p>Specify a name that uniquely identifies this button.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>NormalImage</strong></p></td>
    <td><p>Specify the value that represents the image to display on the button. For example, use <strong>10121</strong> for a button that deletes a record.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Primary</strong></p></td>
    <td><p>Click <strong>Yes</strong> to keep the button displayed when the action pane size decrease.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>ShowShortCut</strong></p></td>
    <td><p><strong>No</strong></p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Text</strong></p></td>
    <td><p>Specify the label to display on the button. For example, use <strong>Delete</strong> for a button that deletes a record.</p></td>
    </tr>
    </tbody>
    </table>


6.  Right-click the form, and then click **Save**.

To view the command button, right-click the form in the AOT, and then click **Open**. The client displays the button in the list page action pane. To perform the specified command, click the button.

## Creating a Menu Item Button

In this procedure, you will create a menu item button that opens a task page in a new window.

Before you create the button, verify that the menu item supports the client environment. The **RunOn** property of the menu item specifies where the action executes. The following table describes the **RunOn** setting for each type of menu item.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Menu item type</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Action</p></td>
<td><p>The default value for the <strong>RunOn</strong> property is <strong>Called from</strong>. For client actions, you can set <strong>RunOn</strong> to <strong>Called from</strong>, <strong>Server</strong>, or <strong>Client</strong>. For actions that open client forms or menu items, set the <strong>RunOn</strong> property to <strong>Client</strong>.</p>
<p>For actions that run on Enterprise Portal, set the <strong>RunOn</strong> property to <strong>Called from</strong>, or <strong>Server</strong>.</p></td>
</tr>
<tr class="even">
<td><p>Display</p></td>
<td><p>You can use all values in the <strong>RunOn</strong> property.</p></td>
</tr>
<tr class="odd">
<td><p>Output</p></td>
<td><p>Set the value of the <strong>RunOn</strong> property to <strong>Client</strong>.</p></td>
</tr>
</tbody>
</table>


### To create a menu item button

1.  In the AOT, expand **Forms**, and then expand the form node.

2.  To view the action pane, expand **Designs**, and then expand the **Design** node.

3.  Expand the action pane, expand the action pane tab, and expand the button group that will contain the new button. Right-click the button group control, click **New Control**, and then click **MenuItemButton**. A new button control is added to the button group in the AOT.

4.  To specify the location of the button in the button group, use the ALT+UP ARROW or ALT+DOWN ARROW to position the button before or after an existing button.

5.  To view the button's properties, expand the button group, right-click the **MenuItemButton** node, and then click **Properties.** The button properties window opens and displays the default values. You can customize the button by replacing default property values with new values. For a menu item button, provide values for the following properties.
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Property</p></th>
    <th><p>Value</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><strong>Big</strong></p></td>
    <td><p>Click <strong>Yes</strong> to make the button a large button.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>ButtonDisplay</strong></p></td>
    <td><p>Select the value that represents how you want the button to display its text and image values.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>ForcedToOverflow</strong></p></td>
    <td><p>Specify whether the button should always be in the button group overflow menu. Click <strong>Yes</strong> to add it to the overflow menu. Click <strong>No</strong> to have the button display in the button group.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>ImageLocation</strong></p></td>
    <td><p>Specify the location of the image that you want to appear on the button. You can click <strong>File</strong>, <strong>AOTResource</strong>, or <strong>EmbeddedResource</strong>.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>MenuItemName</strong></p></td>
    <td><p>Specify the menu item that you want the button to use when it is clicked.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>MenuItemType</strong></p></td>
    <td><p>To change the available <strong>MenuItemName</strong> list, select the type of the menu item that you want to use.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>MultiSelect</strong></p></td>
    <td><p>Click <strong>Yes</strong> to use the command against more than one highlighted record in the grid.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Name</strong></p></td>
    <td><p>Specify a name that uniquely identifies this button.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>NormalImage</strong></p></td>
    <td><p>Specify the value that represents the image to display on the button.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Primary</strong></p></td>
    <td><p>Click <strong>Yes</strong> to keep the button displayed when the action pane size decreases.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>ShowShortCut</strong></p></td>
    <td><p><strong>No</strong></p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Text</strong></p></td>
    <td><p>Specify the label to display on the button. For example, use <strong>Delete</strong> for a button that deletes a record.</p></td>
    </tr>
    </tbody>
    </table>


6.  Right-click the form, and then click **Save**.

To view the button, right-click the form name in the AOT, and then click **Open**. The client displays the button in the list page action pane. To open the specified menu item, click the button.

## Creating a Menu Button

In this procedure, you will create a menu button that displays a list of buttons.

### To create a menu button

1.  In the AOT, expand **Forms**, and then expand the form node.

2.  To view the action pane, expand **Designs**, and then expand the **Design** node.

3.  Expand the action pane, expand the action pane tab, and expand the button group that will contain the new button. Right-click the button group control, click **New Control**, and then click **MenuButton**. A new button control is added to the button group in the AOT.

4.  To specify the location of the button in the button group, use the ALT+UP ARROW or ALT+DOWN ARROW to position the button before or after an existing button.

5.  To view the button's properties, expand the button group, right-click the **MenuButton** node, and then click **Properties.** The button properties window opens and displays the default values. You can customize the button by replacing default property values with new values. For a menu button, provide values for the following properties.
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Property</p></th>
    <th><p>Value</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><strong>Big</strong></p></td>
    <td><p>Click <strong>Yes</strong> to make the button appear as a large button in the action pane.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>ButtonDisplay</strong></p></td>
    <td><p>Select the value that represents how you want the button to display its text and image values. A large action pane button typically uses <strong>Text &amp; Image above</strong>.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>ForcedToOverflow</strong></p></td>
    <td><p>Specify whether the button should always be in the button group overflow menu. Click <strong>Yes</strong> to add it to the overflow menu. Click <strong>No</strong> to have the button display in the button group.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>ImageLocation</strong></p></td>
    <td><p>Specify the location of the image that you want to appear on the button. You can click <strong>File</strong>, <strong>AOTResource</strong>, or <strong>EmbeddedResource</strong>.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Name</strong></p></td>
    <td><p>Specify a name that uniquely identifies this button.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>NormalImage</strong></p></td>
    <td><p>Specify the value that represents the image to display on the button.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Primary</strong></p></td>
    <td><p>Click <strong>Yes</strong> to keep the button displayed when the action pane size decreases.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>ShowShortCut</strong></p></td>
    <td><p><strong>No</strong></p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Text</strong></p></td>
    <td><p>Specify the label to display on the button.</p></td>
    </tr>
    </tbody>
    </table>


6.  To add buttons to the button list, right-click the button, click **New Control**, and then click the type of button.
    

    > [!NOTE]
    > <P>You can add a command button, menu item button, and button to the menu button list. After you add the button control, set the properties using the procedure for that button type.</P>



7.  Right-click the form, and then click **Save**.

To view the menu button, right-click the form name in the AOT, and then click **Open**. The client displays the button in the list page action pane. To view the button list, click the button.

## Creating a Button

In this procedure, you will create a button that displays whether the list page can obtain records from more than one company.

### To create a button

1.  In the AOT, expand **Forms**, and then expand the form node.

2.  To view the action pane, expand **Designs**, and then expand the **Design** node.

3.  Expand the action pane, expand the action pane tab, and expand the button group that will contain the new button. Right-click the button group control, click **New Control**, and then click **Button**. A new button control is added to the button group in the AOT.

4.  To specify the location of the button in the button group, use the ALT+UP ARROW or ALT+DOWN ARROW to position the button before or after an existing button.

5.  To view the button's properties, expand the button group, right-click the **Button** node, and then click **Properties.** The button properties window opens and displays the default values. You can customize the button by replacing default property values with new values. For a button, provide values for the following properties.
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Property</p></th>
    <th><p>Value</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><strong>Big</strong></p></td>
    <td><p>Click <strong>Yes</strong> to make the button appear as a large button in the action pane.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>ButtonDisplay</strong></p></td>
    <td><p>Select the value that represents how you want the button to display its text and image values.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>ForcedToOverflow</strong></p></td>
    <td><p>Specify whether the button should always be in the button group overflow menu. Click <strong>Yes</strong> to add it to the overflow menu. Click <strong>No</strong> to have the button display in the button group.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>ImageLocation</strong></p></td>
    <td><p>Specify the location of the image that you want to appear on the button. You can click <strong>File</strong>, <strong>AOTResource</strong>, or <strong>EmbeddedResource</strong>.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Name</strong></p></td>
    <td><p>Specify a name that uniquely identifies this button.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>NormalImage</strong></p></td>
    <td><p>Specify the value that represents the image to display on the button.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Primary</strong></p></td>
    <td><p>Click <strong>Yes</strong> to keep the button displayed when the action pane size decreases.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>ShowShortCut</strong></p></td>
    <td><p><strong>No</strong></p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Text</strong></p></td>
    <td><p>Specify the label to display on the button.</p></td>
    </tr>
    </tbody>
    </table>


6.  Expand this button node, right-click **Override Method**, and then click **clicked**.

7.  Right-click the **clicked** method and then click **Edit**. The AOT opens the code editor for the specified method. Add the code that you want to execute when the button is clicked. The code example that follows shows how to override the clicked method to display information about the form data source.

8.  Right-click the form, and then click **Save**.

To view the button, right-click the form name in the AOT, and then click **Open**. The client displays the button in the list page action pane. To test the button action, click the button.

The following code example shows how to override the **clicked** event. When the button is clicked, a dialog box opens and displays a message that states whether the list page displays data from a single company or from more than one company.
```X++  
    void clicked()
    {
        // Declare variables
        Dialog dialogBox;
        boolean isCrossCompany;
        ;
    
        super();
        
        // Determine whether the form supports cross company queries.
        isCrossCompany = Form.dataSource(1).crossCompanyAutoQuery();
        
        // Create a dialog box object.
        dialogBox = new Dialog("Cross Company Status");
        
        // Notify the user whether the form displays data from 
        // more than one company.
        if(isCrossCompany == true)
        {
            dialogBox.addText("The form data source retrieves records
              from all companies.");
        }
        else
        {
            dialogBox.addText("The form data source retrieves records 
              from a single company.");
        }
        
        dialogBox.run();
    }
```
## See also

[Action Pane Button Overview](action-pane-button-overview.md)

[How to: Add an Image to an Action Pane Button](how-to-add-an-image-to-an-action-pane-button.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

