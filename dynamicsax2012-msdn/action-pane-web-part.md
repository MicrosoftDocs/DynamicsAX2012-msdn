---
title: Action Pane Web Part
TOCTitle: Action Pane
ms:assetid: b3b8d00c-298f-4e37-8d00-d38c02d780d3
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg846112(v=AX.60)
ms:contentKeyID: 35245664
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# Action Pane Web Part 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The Action pane web part displays the action pane for a page. The Action pane has the same functionality as the SharePoint Ribbon. An Action pane web part is shown in the following illustration.

![Action Pane](images/Gg846112.EP_ActionPane(AX.60).gif "Action Pane")

**Action Pane**

## Page Types Used On

Task pages

Entity overview pages

## Microsoft Dynamics AX Properties

The following property specific to Microsoft Dynamics AX is available for this web part.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Property</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Web menu</p></td>
<td><p>Specifies the Web Menu item in the AOT that defines the groups and buttons displayed in the action pane.</p></td>
</tr>
</tbody>
</table>


## Connections

Can subscribe to an AxContextList published by a User Control web part.

## Comments

The hierarchy of elements in the web menu defines the layout of the action pane. The top level of the web menu defines the action pane. The next level defines the tabs that appear in the action pane. The level underneath that defines the groups that appear in the tab. Finally, the lowest level defines the buttons that appear within each group.

For example, the following illustration shows the structure of the RoomsActionPane web menu.

![Web menu for an action pane](images/Gg846112.EP_ActionPaneWebMenu(AX.60).gif "Web menu for an action pane")

This web menu defines the layout of the action pane for the **Room details** page, which is shown in the following illustration. Notice how the structure of the web menu matches the structure of the action pane. The one exception is the Close button. This button is not part of the web menu, and is added to the action pane by the AxForm control that is used on the page.

![Action pane buttons](images/Gg846112.EP_ActionPaneButtonExample(AX.60).gif "Action pane buttons")

The two factors control the layout of the buttons within each group of the action pane. The first is the setting of the **Big** property for the web menu item. If the **Big** property for the web menu item is set to Yes, the button will be displayed in full size and placed at the start of the group. If the **Big** property for the web menu item is set to No, the button will be displayed in the smaller size and positioned in the right side of the group. Within the “big” and “small” groups, the buttons are displayed in the order that they are defined in the web menu in the AOT. The following illustration shows the big and small ordering in a button group.

![Action pane button layout](images/Gg846112.EP_ActipnPaneButtonLayout(AX.60).gif "Action pane button layout")

