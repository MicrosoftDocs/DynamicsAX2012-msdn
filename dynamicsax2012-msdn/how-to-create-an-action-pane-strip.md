---
title: 'How to: Create an Action Pane Strip'
TOCTitle: 'How to: Create an Action Pane Strip'
ms:assetid: 7ca9a2e6-1116-496e-8b0d-5d7210e1eebb
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh538482(v=AX.60)
ms:contentKeyID: 39508915
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Create an Action Pane Strip [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

You can add an action pane strip to the top of a form, or to a grid or FastTab that appears on a form. The following procedures show you how to add a new action pane strip. If you use a template to create the form, you might find that the controls for the action pane strip have already been added to the form. To use the existing action pane strip, you should follow the steps about how to add buttons to the strip. For more information about action pane strips, see [Action Pane Strip Overview](action-pane-strip-overview.md).

### To add the action pane strip

1.  In the AOT, expand **Forms** and then find the form where you want to add the action pane strip.

2.  Expand **Designs**, expand **Design**, and then find the node or control where you want the action pane strip to appear. You can add an action pane strip to the following form nodes:
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Node</p></th>
    <th><p>Description</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><strong>Design</strong></p></td>
    <td><p>You add an action pane strip to the <strong>Design</strong> node when you want the action pane strip to appear across the top of the form. If you use a template to create a simple list or a simple list and details form, the <strong>Design</strong> node will already include the controls for the action pane strip.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Group</strong></p></td>
    <td><p>You add an action pane strip to a group control when you want to associate specific actions with the grid control that appears in the group.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>TabPage</strong></p></td>
    <td><p>You add an action pane strip to a tab page control when you want to associate specific actions with the contents of a FastTab. If you use a template to create the form, the template will add the controls for the action pane strip to the tab page of the FastTab.</p>
    <p>You can also add an action pane strip to a tab page when you want to associate an action pane strip with a tab that contains a grid control.</p></td>
    </tr>
    </tbody>
    </table>


3.  To add an action pane strip, right-click the node where you want to add the action pane strip, point to **New Control**, and then click **ActionPane**. The action pane control is added. In addition, an action pane tab and a button group are added to the action pane control.
    

    > [!WARNING]
    > <P>If the node already includes an action pane control, you should use the existing control. You should not add more than one action pane control to the <STRONG>Design</STRONG> node, group control, or tab page control.</P>



4.  Right-click the action pane control and then click **Properties**. The property sheet opens in the **Properties** window.

5.  In the property sheet, click **Style** and then click **Strip**.

### To add a button to the action pane strip

1.  Expand the action pane control, expand the action pane tab, and then expand the button group control.
    

    > [!IMPORTANT]
    > <P>Do not add an action pane tab or button group control to the action pane control. An action pane strip should not have more than one action pane tab or button group.</P>



2.  Right-click the button group control, point to **New Control**, and then click the type of button you want to appear in the action pane strip.
    
    For example, click **CommandButton** to add a command button to the action pane strip.

3.  Click the new button. In the property sheet, set values for the button properties. The following table shows properties that are used by all action pane buttons. For information about how to set additional properties that are unique to each type of action pane button, see [How to: Create an Action Pane Button](how-to-create-an-action-pane-button.md).
    
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
    <td><p><strong>ButtonDisplay</strong></p></td>
    <td><p>Specify the appearance of the button. For example, use <strong>Text &amp; Image left</strong> to display an icon and a label for the button.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Name</strong></p></td>
    <td><p>Enter a name that uniquely identifies this button in the button group.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Text</strong></p></td>
    <td><p>Specify the label to display on the button. For example, enter <strong>Export to Excel</strong> for a command button that exports a list of records to Excel.</p></td>
    </tr>
    </tbody>
    </table>


4.  Right-click the form and then click **Save**.

## See also

[Action Pane Button Overview](action-pane-button-overview.md)

[Action Pane Overview](action-pane-overview.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

