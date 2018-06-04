---
title: Best Practices for Index Properties
TOCTitle: Index Properties
ms:assetid: 2adbbd1c-77bd-4b64-8bd6-7c32296fc63c
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa621872(v=AX.60)
ms:contentKeyID: 35241771
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Best Practices for Index Properties 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The following table describes the standards and best practices in Microsoft Dynamics AX for setting the properties for an index. For a description of each property, see [Table Index Properties](https://msdn.microsoft.com/en-us/library/aa881522\(v=ax.60\)).

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
<td><p>Use the field name for a single field index. You must use &quot;Idx&quot; as a postfix for index names.</p>
<p>If you attempt to create an index with a name that has already been used for an index in Microsoft Business Solutions—Axapta, an error occurs. <img src="images/Aa872655.ErrorIcon(AX.60).gif" title="Error icon" alt="Error icon" /></p></td>
</tr>
<tr class="even">
<td><p><span id="rx43allowduplic"></span> AllowDuplicates</p></td>
<td><p>The primary index must have the AllowDuplicates property set to No.</p>
<p><img src="images/Aa872655.ErrorIcon(AX.60).gif" title="Error icon" alt="Error icon" /></p>
<p>There should be one unique index per table for tables that belong to the table groups Group, Main, and WorksheetHeader. If set to <strong>Yes</strong>, the index can be non-unique.</p>
<p>If you do not create at least one unique index, Microsoft Dynamics AX creates one by combining the first index and the RecId.</p></td>
</tr>
<tr class="odd">
<td><p>Enabled</p></td>
<td><p>This property is usually set to <strong>Yes</strong>.</p></td>
</tr>
<tr class="even">
<td><p>ConfigurationKey</p></td>
<td><p>You should use a configuration key so that the index is disabled for features that are disabled.</p></td>
</tr>
</tbody>
</table>



> [!NOTE]
> <P>If forms are opened with no specific ranges or specific sort orders, and no index is specified in the index property of the form's data source, forms sort on the first index.</P>



## See also

[Best Practices for Indexes](best-practices-for-indexes.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

