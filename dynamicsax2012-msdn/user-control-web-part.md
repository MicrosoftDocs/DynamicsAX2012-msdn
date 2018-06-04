---
title: User Control Web Part
TOCTitle: User Control
ms:assetid: 5dc38ea6-67c1-4280-9203-486e1ddc8f85
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc554683(v=AX.60)
ms:contentKeyID: 35245347
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# User Control Web Part 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The User control web part hosts User Controls that have been developed in Visual Studio. User Controls are the primary way that developers create new functionality for Enterprise Portal.

## Page Types Used On

Any web part page

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
<td><p>Managed content item</p></td>
<td><p>The name of the Web Control (an item in the <strong>Web</strong> &gt; <strong>Web Files</strong> &gt; <strong>Web Controls</strong> node of the AOT) that will be displayed in the web part.</p></td>
</tr>
<tr class="even">
<td><p>Web part role</p></td>
<td><p>Specifies whether the User control web part is a provider or consumer in web part communication for the page.</p></td>
</tr>
<tr class="odd">
<td><p>Updatemode</p></td>
<td><p>When connected to another web part, specifies when the content of the web part will be updated. The value can be Conditional or Always. If it is set to Conditional, the content of the web part is updated only when the context changes. When set to Always, the web part will be updated even when the context has not changed.</p></td>
</tr>
</tbody>
</table>


## Connections

Can publish an AxContextList or subscribe to an AxContextList published by another User control web part.

Can publish an AxPageTitle to a Page title web part.

## See also

[User Controls Overview](user-controls-overview.md)

