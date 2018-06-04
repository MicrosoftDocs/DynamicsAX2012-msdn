---
title: Specify Whether a Form Opens for Modification and Data Entry
TOCTitle: Specify Whether a Form Opens for Modification and Data Entry
ms:assetid: 4d3bbfce-1802-4827-ad21-dea52d9137a0
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa629126(v=AX.60)
ms:contentKeyID: 35243409
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Specify Whether a Form Opens for Modification and Data Entry 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

When you create a form, you can specify what actions the user is allowed to perform on the data in the underlying table. You restrict access by using properties on the form data source. These properties are shown in the following table.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Property</p></th>
<th><p>Function</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>AllowEdit</p></td>
<td><p>Allows modifications to the data source</p></td>
</tr>
<tr class="even">
<td><p>AllowCreate</p></td>
<td><p>Allows new records to be created in the data source</p></td>
</tr>
<tr class="odd">
<td><p>AllowDelete</p></td>
<td><p>Allows deletions in the data source</p></td>
</tr>
</tbody>
</table>



> [!NOTE]
> <P>If you allow the contents of the data source to be modified, created, and/or deleted, they are exposed to a security risk. To help reduce this risk (if it is determined to be unacceptable for your data source), set the AllowEdit, AllowCreate, and/or AllowDelete property values on your form to <STRONG>No</STRONG>.</P>


  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

