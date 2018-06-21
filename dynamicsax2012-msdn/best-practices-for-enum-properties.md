---
title: Best Practices for Enum Properties
TOCTitle: Enum Properties
ms:assetid: 816be633-24a6-4ee0-be39-265d7f2d4b95
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa657395(v=AX.60)
ms:contentKeyID: 35246139
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Best Practices for Enum Properties [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The best practices for enum properties are shown in the following table. For more information about the properties, see [Base Enum Properties](https://msdn.microsoft.com/en-us/library/aa856690\(v=ax.60\)).

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
<td><p>Name</p></td>
<td><p>An enum name must either indicate the possible enum values or indicate the type of the enum value.</p>
<p>Examples of enums that are named according to the possible values are InclExcl and NextPrevious.</p>
<p>Examples of enums that are named according to the type of the enum value are ArrivalPostingType and ListStatus.</p>
<p>If you try to create an enum with a name that has already been used for an enum in the previous version of Microsoft Dynamics AX, you will get an error. <img src="images/Aa872655.ErrorIcon(AX.60).gif" title="Error icon" alt="Error icon" /></p></td>
</tr>
<tr class="even">
<td><p>Label</p></td>
<td><p>Mandatory.</p></td>
</tr>
<tr class="odd">
<td><p>Help</p></td>
<td><p>Mandatory.</p>
<p>The Help property should not be identical to the Label property; give the user a more thorough explanation.</p></td>
</tr>
<tr class="even">
<td><p>DisplayLength</p></td>
<td><p>Set to Auto (to allow IntelliMorph features).</p></td>
</tr>
</tbody>
</table>


## See also

[Best Practices for Base Enums](best-practices-for-base-enums.md)

[Enums](enums.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

