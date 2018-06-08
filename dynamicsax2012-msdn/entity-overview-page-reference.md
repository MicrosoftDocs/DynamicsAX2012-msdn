---
title: Entity Overview Page Reference
TOCTitle: Entity Overview Page
ms:assetid: e043e8ad-77d4-4082-9d4c-d0bd96bd4312
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc652747(v=AX.60)
ms:contentKeyID: 35246162
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# Entity Overview Page Reference 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

An entity overview page displays detailed information about an entity, such as customer or item. The page is displayed in a SharePoint modal dialog. It typically contains several groups that categorize the information about the entity. An action pane at the top of the page allows for actions to be performed for the entity.

## Page Content

The entity overview page uses the **Header, Footer, 3 Columns** layout template. The page typically contains the following items.

### Title Bar

The items in the Title Bar are listed in the following table.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Item</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Page Title</p></td>
<td><p>The <a href="page-title-web-part.md">Page Title Web Part</a> displays the title for the page.</p></td>
</tr>
</tbody>
</table>


### Header

The items in the Header are listed in the following table.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Item</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Infolog</p></td>
<td><p>The <a href="infolog-web-part.md">Infolog Web Part</a> displays any status information for actions performed on the page.</p></td>
</tr>
</tbody>
</table>


### Left Column

The items in the Left Column are listed in the following table.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Item</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>QuickLaunch</p></td>
<td><p>The <a href="quicklaunch-web-part.md">QuickLaunch Web Part</a> displays the page-level navigation for the page. When the page is displayed in a SharePoint modal dialog, the entire left column is hidden.</p></td>
</tr>
</tbody>
</table>


### Middle Column or Right Column

The items in the Middle Column or Right Column are listed in the following table.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Item</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Action Pane</p></td>
<td><p>The <a href="action-pane-web-part.md">Action Pane Web Part</a> displays the web menu that defines the groups and buttons displayed in the Action Pane (the SharePoint ribbon). See <a href="enterprise-portal-action-pane-user-experience-guidelines.md">Enterprise Portal Action Pane User Experience Guidelines</a> for guidelines to follow when creating an Action Pane.</p></td>
</tr>
<tr class="even">
<td><p>User Controls</p></td>
<td><p>The <a href="user-control-web-part.md">User Control Web Part</a> displays detailed information about the entity. The <a href="axform.md">AxForm</a> control is used to define the content for these web parts.</p></td>
</tr>
</tbody>
</table>


### Footer

No items are included in the footer.

## Web Part Communication

The main User Control on the page and the Action Pane use web part communication to indicate what entity is being displayed on the page. For more information, see [How to: Connect User Controls to Action Panes or Toolbars](how-to-connect-user-controls-to-action-panes-or-toolbars.md).

