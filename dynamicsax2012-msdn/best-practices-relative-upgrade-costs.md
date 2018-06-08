---
title: 'Best Practices: Relative Upgrade Costs'
TOCTitle: Relative Upgrade Costs
ms:assetid: 5fe8a32f-c3b0-4556-a7c4-08777bbd207a
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa608217(v=AX.60)
ms:contentKeyID: 35244474
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Best Practices: Relative Upgrade Costs 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The following table provides an overview of the relative upgrade cost for a change to an existing application object.

The upgrade cost is not an absolute value. This table is meant to give only an approximation of the work involved.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Application Object Type</p></th>
<th><p>Cost if functionality added</p></th>
<th><p>Cost if functionality changed</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Form</p></td>
<td><p>High</p></td>
<td><p>High</p></td>
</tr>
<tr class="even">
<td><p>Report[1]</p></td>
<td><p>High</p></td>
<td><p>High</p></td>
</tr>
<tr class="odd">
<td><p>Report Template</p></td>
<td><p>Low</p></td>
<td><p>Low</p></td>
</tr>
<tr class="even">
<td><p>Query</p></td>
<td><p>Medium</p></td>
<td><p>Medium</p></td>
</tr>
<tr class="odd">
<td><p>Menu</p></td>
<td><p>Medium</p></td>
<td><p>Medium</p></td>
</tr>
<tr class="even">
<td><p>Table collection</p></td>
<td><p>Medium</p></td>
<td><p>Medium</p></td>
</tr>
<tr class="odd">
<td><p>Table</p></td>
<td><p>Low</p></td>
<td><p>Medium</p></td>
</tr>
<tr class="even">
<td><p>Class</p></td>
<td><p>Low</p></td>
<td><p>Medium</p></td>
</tr>
<tr class="odd">
<td><p>Extended data Type</p></td>
<td><p>Medium</p></td>
<td><p>Medium</p></td>
</tr>
<tr class="even">
<td><p>Base Enum</p></td>
<td><p>Medium</p></td>
<td><p>Medium</p></td>
</tr>
<tr class="odd">
<td><p>Menu Items</p></td>
<td><p>Medium</p></td>
<td><p>Medium</p></td>
</tr>
</tbody>
</table>


\[1\] Modifications to a report can be done by adding a new design. In this case, the upgrade cost is considered Medium.

If new functionality is added to a Microsoft Dynamics AX application as new stand-alone application objects, the cost of upgrading is likely to be much lower than if the functionality was created by modifying existing objects.

## See also

[Best Practice Design Guidelines for Cost-Efficient Upgrades](best-practice-design-guidelines-for-cost-efficient-upgrades.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

