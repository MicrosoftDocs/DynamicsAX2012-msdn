---
title: 'How to: Create a New Module with Workflow'
TOCTitle: 'How to: Create a New Module with Workflow'
ms:assetid: f8785f2d-848c-4046-87f0-6c3465118a8c
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc624367(v=AX.60)
ms:contentKeyID: 35253748
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Create a New Module with Workflow 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

In Microsoft Dynamics AX, modules are enabled for workflow. However, in some cases, you will need to create a new module that contains workflow. In each module that contains workflow, a **Workflows** list menu item must be added to the **Setup** pane. The following procedures are described in this topic:

  - Creating a new module enumeration.

  - Creating a display menu item for the **Workflows** list.

  - Creating a menu for the new module.

  - How to display the new menu in the client.

### To Add a Module to the ModuleAxapta Base Enum

1.  In the Application Object Tree (AOT), expand the **Data Dictionary** node, expand **Base Enums**, right-click **ModuleAxapta**, and then click **New Element**. A new enumeration displays under the **ModuleAxapta** node.

2.  Right-click the new enumeration, and then click **Properties**.

3.  In the **Properties** sheet, select the **Label** property, and then enter the label of the new module.

### To Create a Display Menu Item for the Workflows List

1.  In the AOT, expand the **Menu Items** node.

2.  Right-click the **Display** node, and then click **New Menu Item**. A new menu item displays under the **Display** node.

3.  Right-click the new display menu item, and then click **Properties**.

4.  In the **Properties** sheet, set the following properties.
    
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
    <td><p>Set to WorkflowConfigurations&lt;xxx&gt; where &lt;xxx&gt; is replaced by a reference to the name of the new module. For example, you could set this value to WorkflowConfigurationsRecruit for a new module named Recruiting.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Label</strong></p></td>
    <td><p>Set text or a label that represents the text for the workflows list in the client.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>ObjectType</strong></p></td>
    <td><p>Set to Form.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Object</strong></p></td>
    <td><p>Set to WorkflowTableListPage.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>EnumTypeParameter</strong></p></td>
    <td><p>Set to ModuleAxapta.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>EnumParameter</strong></p></td>
    <td><p>Set to the enum created in the preceding procedure.</p></td>
    </tr>
    </tbody>
    </table>


5.  In the AOT, right-click the new display menu item, and then click **Save**.

After the new module enum and display menu item are created, you can add them to the **Menus** node.

### To Create a Menu for a New Module

1.  In the AOT, right-click the **Menus** node, and then click **New Menu**. A new menu displays under the **Menus** node.

2.  Right-click the new menu, and then click **Properties**.

3.  In the **Properties** sheet, set the following properties.
    
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
    <td><p>Set to a label or name of the new module.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Label</strong></p></td>
    <td><p>Set to a label that represents the text to display for the new menu in the client.</p></td>
    </tr>
    </tbody>
    </table>


4.  In the AOT, right-click the new menu, point to **New**, and then click **New Submenu**. A submenu node displays under menu node created in the previous step.

5.  Right-click the new submenu node, and then click **Properties**.

6.  In the **Properties** sheet, set the following properties.
    
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
    <td><p>Set to <strong>Setup</strong> or another label that represents the text for the <strong>Setup</strong> pane in the client.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Label</strong></p></td>
    <td><p>Set to <strong>Setup</strong> or another label that represents the text for the <strong>Setup</strong> pane in the client.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>NormalImage</strong></p></td>
    <td><p>Set to 3478. This will display a gears icon for the setup pane.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>ImageLocation</strong></p></td>
    <td><p>Set to <strong>EmbeddedResource</strong>.</p></td>
    </tr>
    </tbody>
    </table>


7.  In the AOT, right-click the **Setup** node created in the previous step, point to **New**, and then click **New Menu item**. A new menu item displays under the **Setup** node.

8.  Right-click the new menu item, and then click **Properties**.

9.  In the **Properties** sheet, set the **MenuItemName** property to the display menu item created in the previous procedure.

10. In the AOT, right-click the new menu item, and then click **Save**.

After the menu for the new module is created, you must add a reference to the menu in the **MainMenu** node to display the menu in the client.

### To Add a Menu to the Client

1.  In the AOT, expand the **Menus** node, right click **MainMenus**, point to **New**, and then click **Menu reference**. The **Select: Menus** window is displayed.

2.  In the **Select: Menus** window, select the new module menu that you created in the previous procedure, and drag the menu to the **MainMenu** node in the AOT.

3.  In the AOT, right-click the **MainMenu** node, and then click **Save**.

## See also

[Requirements for Enabling Workflow in an Application Module](requirements-for-enabling-workflow-in-an-application-module.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

