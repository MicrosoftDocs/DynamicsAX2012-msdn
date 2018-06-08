---
title: Null Values for Data Types
TOCTitle: Null Values for Data Types
ms:assetid: 9b66b1ee-8a43-4a9a-8a59-75f76785b385
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa846236(v=AX.60)
ms:contentKeyID: 35248172
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Null Values for Data Types 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Microsoft Dynamics AX does not support the concept of null values that is available in many other Database Management Systems (DBMS). A field in Microsoft Dynamics AX always has a type and a value.

For each data type, however, one value is considered null (for example, when the validateField table method is executed).

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Type</p></th>
<th><p>Value treated as null</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Date</p></td>
<td><p>1900-01-01</p></td>
</tr>
<tr class="even">
<td><p>Enum</p></td>
<td><p>Element with its value set to 0.</p></td>
</tr>
<tr class="odd">
<td><p>Integer</p></td>
<td><p>0</p></td>
</tr>
<tr class="even">
<td><p>Real</p></td>
<td><p>0.0</p></td>
</tr>
<tr class="odd">
<td><p>String</p></td>
<td><p>An empty string</p></td>
</tr>
<tr class="even">
<td><p>Time</p></td>
<td><p>00:00:00</p></td>
</tr>
<tr class="odd">
<td><p><a href="utcdatetime.md">Utcdatetime</a></p></td>
<td><p>Any value with its date portion as 1900-01-01 is treated as null, regardless of the time portion value. Therefore the value 1900-01-01T22:33:44 is treated as null.</p>
<div class="mtps-table">
<div class="mtps-row">
<img src="images/Aa589339.alert_note(en-us,AX.60).gif" title="Note" alt="Note" class="note" /><strong>Note</strong>
</div>
<div class="mtps-row">
Any utcDateTime value with its date portion as 1900-01-01 is displayed as blank by the X++ print statement. Only the value 1900-01-01T00:00:00 is displayed as blank by the Global::info method. That is the value from the DateTimeUtil::MinValue method.
</div>
</div></td>
</tr>
</tbody>
</table>


As a result, when the validateField method checks whether a user has entered a value in a mandatory field, 0 is not accepted in an integer type field, the first entry is not accepted in an enum type field, and so on.

Also, the values that are listed in the previous table yield false in a Boolean comparison, in X++ SQL. In non-SQL X++ statements, the equal and relational operators work with these values the same normal way that they work with other values.

Variables of type container, and classes and variables of table type can be null in the traditional DBMS sense. A table type is null if all its fields have their null value.

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

