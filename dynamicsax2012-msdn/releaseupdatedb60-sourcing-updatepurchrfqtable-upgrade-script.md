---
title: ReleaseUpdateDB60_Sourcing.updatePurchRFQTable Upgrade Script
TOCTitle: ReleaseUpdateDB60_Sourcing.updatePurchRFQTable Upgrade Script
ms:assetid: 76360079-0247-d3ce-2f2e-8db1a59788a1
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ719323(v=AX.60)
ms:contentKeyID: 49709115
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateDB60\_Sourcing.updatePurchRFQTable Upgrade Script [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateDB60_Sourcing</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>updatePurchRFQTable</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Updates the &lt;c&gt;PurchRFQTable&lt;/c&gt; fields 'PurchPlacer' and 'ResponsibleWorkerId' with the worker recId corresponding to the emplId of the previous data. Updates the &lt;c&gt;PurchRFQTable&lt;/c&gt; table field ExpiryDateTime with the ExpiryDate of the previous data using a default time offset.</p></td>
</tr>
</tbody>
</table>


## Affected Modules and Tables

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Affected Modules</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>SRM</p></td>
</tr>
</tbody>
</table>


<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Affected Tables</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>PurchRFQTable</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

