---
title: Toolbar Web Part
TOCTitle: Toolbar
ms:assetid: d377c089-a991-4c19-9ed1-5eb65b2b8481
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc620734(v=AX.60)
ms:contentKeyID: 35246152
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# Toolbar Web Part [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The Toolbar web part provides access to actions that can be performed for the items in a page. A Toolbar web part is shown in the following illustration.

![Toolbar](images/Cc620734.EP_DynamicsToolbar(AX.60).gif "Toolbar")

**Toolbar**

## Page Types Used On

Task pages

## Microsoft Dynamics AX Properties

The following properties specific to Microsoft Dynamics AX are available for this web part.

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
<td><p>Specifies the Web Menu item in the AOT that defines the items displayed in the toolbar.</p></td>
</tr>
</tbody>
</table>


## Connections

Can subscribe to an AxContextList published by a User Control web part.

## Comments

Toolbar web parts were used more frequently in Microsoft Dynamics AX 2009. In Microsoft Dynamics AX 2012, the [Action Pane Web Part](action-pane-web-part.md) is used to provide access to actions.

Toolbars can be used in Task pages. Rather than using a Toolbar web part on the Task page, a toolbar is often defined using the [AxToolbar](axtoolbar.md) component that is part of a User Control.

You can use images in web menu items that are displayed by the toolbar. To do this, set the **ImageLocation** property for the web menu item to the type of image to display. Typically, this will be EmbeddedResource. Set the **NormalImage** property to the value corresponding to the image to display for the web menu item.

