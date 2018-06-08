---
title: Layers
TOCTitle: Layers
ms:assetid: a5f4b5db-1faa-48ae-8962-e691c0ef0168
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa851164(v=AX.60)
ms:contentKeyID: 35248422
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Layers 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

In Microsoft Dynamics AX, a layer system is used to manage elements. The USR layer is the top layer and the SYS layer is the bottom layer, and each layer has a corresponding patch layer above it.

## Layers

The following table describes the application object layers in Microsoft Dynamics AX:

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Layer</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>USR</p></td>
<td><p>The user layer is for user modifications, such as reports.</p></td>
</tr>
<tr class="even">
<td><p>CUS</p></td>
<td><p>The customer layer is for modifications that are specific to a company.</p></td>
</tr>
<tr class="odd">
<td><p>VAR</p></td>
<td><p>Value Added Resellers (VAR) can make modifications or new developments to the VAR layer as specified by the customers or as a strategy of creating an industry specific solution.</p></td>
</tr>
<tr class="even">
<td><p>ISV</p></td>
<td><p>When an Independent Software Vendor (ISV) creates their own solution, their modifications are saved in the ISV layer.</p></td>
</tr>
<tr class="odd">
<td><p>SLN</p></td>
<td><p>The solution layer is used by distributors to implement vertical partner solutions.</p></td>
</tr>
<tr class="even">
<td><p>FPK</p></td>
<td><p>The FPK layer is an application object patch layer reserved by Microsoft for future patching or other updates. For more information, see <a href="patch-layers.md">Patch Layers</a>.</p></td>
</tr>
<tr class="odd">
<td><p>GLS</p></td>
<td><p>When the application is modified to match country or region specific legal demands, these modifications are saved in the GLS layer.</p>
<div class="mtps-table">
<div class="mtps-row">
<img src="images/Aa589339.alert_note(en-us,AX.60).gif" title="Note" alt="Note" class="note" /><strong>Note</strong>
</div>
<div class="mtps-row">
The GLS layer is consolidated into the SYS layer in Microsoft Dynamics AX 2012 R3.
</div>
</div></td>
</tr>
<tr class="even">
<td><p>SYS</p></td>
<td><p>The standard application is implemented at the lowest level, the SYS layer. The application objects in the standard application can never be deleted.</p></td>
</tr>
</tbody>
</table>


Each layer has a corresponding patch layer that can be used to incorporate updates to your application or to store conflicts when you import models into a layer. For more information about patch layers, see [Patch Layers](patch-layers.md).

## See also

[Patch Layers](patch-layers.md)

[How to: Compare Layers](how-to-compare-layers.md)

[Compare Tool](compare-tool.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

