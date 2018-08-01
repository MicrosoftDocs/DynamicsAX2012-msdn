---
title: ReleaseUpdateTransformDB50_Transptn.ltAssetPackingSlipPreUpgradeProcess Upgrade Script
TOCTitle: ReleaseUpdateTransformDB50_Transptn.ltAssetPackingSlipPreUpgradeProcess Upgrade Script
ms:assetid: aaee49f2-046e-078f-74df-fcfecc25889a
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ686465(v=AX.60)
ms:contentKeyID: 49710419
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# ReleaseUpdateTransformDB50\_Transptn.ltAssetPackingSlipPreUpgradeProcess Upgrade Script 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>Class</strong></p></td>
<td><p>ReleaseUpdateTransformDB50_Transptn</p></td>
</tr>
<tr class="even">
<td><p><strong>Method</strong></p></td>
<td><p>ltAssetPackingSlipPreUpgradeProcess</p></td>
</tr>
<tr class="odd">
<td><p><strong>Description</strong></p></td>
<td><p>Creates records in &lt;c&gt;Shadow_LtAssetPackingSlip&lt;/c&gt; table related to transportation address and other information stored in &lt;c&gt;PurchAdditionalProperties_W&lt;/c&gt;. PurchAdditionalProperties_W is marked for deletion in Ax 6.2. A record in &lt;c&gt;TransportationDocument&lt;/c&gt; is also created.</p></td>
</tr>
<tr class="even">
<td><p><strong>Script Type</strong></p></td>
<td><p>Preprocessing 60: Delta</p></td>
</tr>
<tr class="odd">
<td><p><strong>Ax Version</strong></p></td>
<td><p>Microsoft Dynamics AX 2009</p></td>
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
<td><p>Fixed Asset</p></td>
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
<td><p>LtAssetPackingSlip</p></td>
</tr>
</tbody>
</table>

  


