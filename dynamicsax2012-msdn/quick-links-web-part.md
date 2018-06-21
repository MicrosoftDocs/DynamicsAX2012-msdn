---
title: Quick Links Web Part
TOCTitle: Quick Links
ms:assetid: bb8484a2-5bbd-4f91-bf07-88e695445445
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc618354(v=AX.60)
ms:contentKeyID: 35246126
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# Quick Links Web Part [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The Quick Links web part displays a collection of links that the Enterprise Portal administrator or a user can modify. The links can provide quick access to other resources, such as locations in Enterprise Portal or external web sites.


> [!IMPORTANT]
> <P>You can link only to web menu items that are included in the navigation for Enterprise Portal.</P>



A Quick Links web part is shown in the following illustration.

![Quick Links](images/Cc618354.EP_QuickLinks(AX.60).gif "Quick Links")

**Quick Links**

## Page Types Used On

Role center pages

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
<td><p>Quick links group ID</p></td>
<td><p>The unique ID for the set of links.</p></td>
</tr>
<tr class="even">
<td><p>Default Title</p></td>
<td><p>The default title that the Quick Links web part will display.</p></td>
</tr>
</tbody>
</table>


## Connections

None

## Comments

Each set of quick links has a unique ID. If you want to package the set of quick links, you can do so by using the **Edit quick links** form in Microsoft Dynamics AX. To open this form, go to **Organization administration** \> **Setup** \> **Role center** \> **Edit quick links**. You use this form to locate your set of links based on the ID in the **Link group ID** column. From the **Export** menu, choose **Export to AOT**. The set of links will be added as a resource in the **Resources** node of the AOT. You can package the quick links resource in the AOT in the same way you would package other resources.

To add a set of links to Enterprise Portal, you will also use the **Edit quick links** window. From the **Import** menu, choose **Import all from AOT**. This will deploy all of the sets of links to Enterprise Portal. Quick links are also deployed to Enterprise Portal during the process that deploys role center profiles.

