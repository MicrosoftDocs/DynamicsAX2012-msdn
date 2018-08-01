---
title: Wizard Page Reference
TOCTitle: Wizard Page
ms:assetid: 1473f48d-748e-4396-9104-0d26f20e18ab
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc583495(v=AX.60)
ms:contentKeyID: 35244943
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# Wizard Page Reference [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

A wizard page displays one step in a process that is completed using a wizard. See [Enterprise Portal Wizard User Experience Guidelines](enterprise-portal-wizard-user-experience-guidelines.md) for guidelines to follow when creating a wizard page. The Wizard control provided by ASP.NET is helpful for managing that state of the wizard pages.

## Page Content

The wizard page uses the **Header, Left Column, Body** layout template. The page typically contains the following items.

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


### Body

The items in the Body are listed in the following table.

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
<td><p>User Control</p></td>
<td><p>The <a href="user-control-web-part.md">User Control Web Part</a> displays the content for the wizard panel. Typically, the <a href="axform.md">AxForm</a> component is used to define the content.</p></td>
</tr>
</tbody>
</table>


## Web Part Communication

No Web part communication is used on this page type.

