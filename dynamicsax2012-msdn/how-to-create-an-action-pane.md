---
title: 'How to: Create an Action Pane'
TOCTitle: 'How to: Create an Action Pane'
ms:assetid: 2f55f7d3-d8d4-4cc0-be42-1edac7a20304
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg844658(v=AX.60)
ms:contentKeyID: 35241962
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Create an Action Pane [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

You use an action pane to provide access to tasks and operations that apply to the records that appear in a form. For information about the design of an action pane, see [Action Pane Overview](action-pane-overview.md).

If you use a template to create a list page or details form, the template adds many of the controls for the action pane to the form. You should start the action pane by modifying the existing controls and then add tabs, button groups, and button controls where they are needed.

The following procedures describe how to add each type of control that you use to create an action pane for a form. If you want to modify an existing action pane, determine what type of controls you need for your customization and then start with the procedure that adds a tab, button group, or buttons.

### To add the action pane

1.  In the AOT, expand **Forms** and then find the form where you want to add an action pane. Expand the form, expand **Designs**, right-click **Design**, point to **New Control**, and then click **ActionPane**. An action pane control is added to the **Design** node of the form.
    
    An action pane tab with a single button group control is also added to the action pane. You should first update the properties for the tab and button group and then add button controls to the button group.
    

    > [!WARNING]
    > <P>If you used a template to create the form, the template might have added an action pane and related controls. You should not add a second action pane to a form. To modify the action pane from the template, view the sections that describe how to add a tab, button group, or button.</P>



2.  To make the action pane appear at the top of the form, you might have to reorder the controls in the **Design** node. The **ActionPane** must be the first control in the **Design** node of the form. To move the control, expand **Design**, click the action pane, and then press ALT+UP ARROW or ALT+DOWN ARROW.

3.  Right-click the action pane control and then click **Properties**. Use the property sheet to set values for the following properties.
    
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
    <td><p><strong>Name</strong></p></td>
    <td><p>Enter a name that identifies your action pane.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Style</strong></p></td>
    <td><p><strong>Standard</strong></p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>VerticalSpacing</strong></p></td>
    <td><p><strong>0</strong></p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Width</strong></p></td>
    <td><p><strong>Column width</strong></p></td>
    </tr>
    </tbody>
    </table>


If you add an action pane to a form, you must add one or more action pane tabs to the action pane. The following procedure shows how to add an action pane tab to an action pane.

If you use a template to create the form, you will find an action pane tab was already added to the action pane. You can use the following procedure to customize the existing action pane tab or to add another action pane tab.

### To add an action pane tab

1.  Right-click the action pane control, point to **New Control**, and then click **ActionPaneTab**. An action pane tab control is added to the action pane.
    

    > [!NOTE]
    > <P>You can copy an action pane tab from an existing form. To copy the action pane tab, use the AOT to drag the existing action pane tab onto the action pane control of a form. The action pane tab, button groups, and buttons are all added to the action pane.</P>



2.  To view the properties for the control, click the action pane tab. Use the property sheet to set values for the following properties.
    
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
    <td><p><strong>Name</strong></p></td>
    <td><p>Enter a name that uniquely identifies your tab control in the action pane.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Caption</strong></p></td>
    <td><p>Specify the label you want to appear on the tab. For example, you use <strong>General</strong> for a tab that displays a set of frequently used actions.</p></td>
    </tr>
    </tbody>
    </table>


3.  To add another action pane tab, repeat the steps in this procedure.

After you add an action pane tab, you must add one or more button groups to that tab. The following procedure shows how to add a button group control to an action pane tab.

If you use a template to create the form, you might find that action pane button groups were already added to the action pane tab. You can use the following procedure to customize the existing action pane button group or to add another button group to the action pane tab.

### To add an action pane button group

1.  Right-click the action pane tab, point to **New Control**, and then click **ButtonGroup**. A new button group control is added in the AOT.

2.  To view the properties for the control, click the button group. Use the property sheet to set values for the following button group properties.
    
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
    <td><p><strong>Name</strong></p></td>
    <td><p>Enter a name that uniquely identifies your button group in the action pane tab.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Caption</strong></p></td>
    <td><p>Specify the label you want to appear on the button group. For example, you use <strong>List</strong> to label a group of buttons that export data.</p></td>
    </tr>
    </tbody>
    </table>


3.  To add another button group to an action pane tab, repeat the steps in this procedure.

After you add a button group, you must add one or more button controls to that group. The following procedure shows how to add a button to an action pane button group.

If you use a template to create the form, you might find that action pane buttons were already added to the action pane button group. You can use the following procedure to customize the existing action pane buttons or to add buttons to the action pane button group.

### To add an action pane button

1.  Right-click the button group control, point to **New Control**, and then click the type of button you want to add to the group. The new button is added to the button group.
    
    For example, you click **CommandButton** to add a button that performs a specified Microsoft Dynamics AX command.

2.  To view the properties for the control, click the button. Use the property sheet to set values for the following button properties. The following represent properties that are common to all action pane buttons. For information about the properties that are unique to each type of action pane button, see [How to: Create an Action Pane Button](how-to-create-an-action-pane-button.md).
    
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
    <td><p>Specify how to display the button. Click <strong>Yes</strong> to make the button a large button.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>ButtonDisplay</strong></p></td>
    <td><p>Specify how the button displays its text and image. For example, use <strong>Text &amp; Image above</strong> to display an icon and a label on a large action pane button.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Name</strong></p></td>
    <td><p>Enter a name that uniquely identifies this button in the button group.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Primary</strong></p></td>
    <td><p>Specifies whether to keep the button displayed when the action pane size decreases.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>ShowShortCut</strong></p></td>
    <td><p><strong>No</strong></p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Text</strong></p></td>
    <td><p>Specify the label to display on the button. For example, you use <strong>Export to Excel</strong> for a command button that exports a list of records to Excel.</p></td>
    </tr>
    </tbody>
    </table>


3.  To add another action pane button to a button group, repeat the steps in this procedure.

4.  Right-click the form and then click **Save**.

## See also

[Action Pane Buttons](action-pane-buttons.md)

[Walkthrough: Creating a List Page and Adding an Action Pane](walkthrough-creating-a-list-page-and-adding-an-action-pane.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

