---
title: Best Practices for Perspectives
TOCTitle: Perspectives
ms:assetid: 56ef9f7e-1972-4f0d-a428-1db516d4f363
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa640388(v=AX.60)
ms:contentKeyID: 35244332
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Best Practices for Perspectives [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

This topic contains best practice information for setting perspective properties, perspective field properties, table reference properties, and view reference properties.

## Perspective Properties

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Property</p></th>
<th><p>Rules</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span id="rx91labeqhelpt"></span></p>
<p>Label</p></td>
<td><p>Mandatory property.</p>
<p>Do not set the Label property to the same property as the HelpText property. <img src="images/Aa872655.ErrorIcon(AX.60).gif" title="Error icon" alt="Error icon" /></p></td>
</tr>
<tr class="even">
<td><p><span id="rx92helpteqlab"></span></p>
<p>HelpText</p></td>
<td><p>Mandatory property.</p>
<p>Do not set the HelpText property to the same property as the Label property; the user should be provided with more detailed information than is available in the label. <img src="images/Aa872655.ErrorIcon(AX.60).gif" title="Error icon" alt="Error icon" /> For more information, see <a href="helptext-guidelines.md">HelpText Guidelines</a>.</p></td>
</tr>
<tr class="odd">
<td><p><span id="rx90persconfigkeymand"></span></p>
<p>ConfigurationKey</p></td>
<td><p>This property must have a value, to allow the perspective to be disabled. <img src="images/Aa872655.ErrorIcon(AX.60).gif" title="Error icon" alt="Error icon" /></p></td>
</tr>
</tbody>
</table>


## Perspective Field Properties

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Property</p></th>
<th><p>Rules</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DataField</p></td>
<td><p>Mandatory property. Must be selected by using the drop-down box next to the property.</p></td>
</tr>
</tbody>
</table>


## Table Reference Properties

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Property</p></th>
<th><p>Rules</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Table</p></td>
<td><p>Mandatory property. Must be selected by using the drop-down box next to the property.</p></td>
</tr>
</tbody>
</table>


## View Reference Properties

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Property</p></th>
<th><p>Rules</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>View</p></td>
<td><p>Mandatory property. Must be selected by using the drop-down box next to the property.</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

