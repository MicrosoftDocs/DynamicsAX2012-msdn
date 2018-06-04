---
title: Valid Time State Tables and Date Effective Data
TOCTitle: Valid Time State Tables and Date Effective Data
ms:assetid: 3b7dd117-e196-4f4c-b575-be24c350a81e
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg861781(v=AX.60)
ms:contentKeyID: 35242902
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Valid Time State Tables and Date Effective Data 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

A valid time state table lets you simplify the maintenance of data for which changes must be tracked at different points in time. For example, the interest rate on a loan can be 5% for the first year, and 6% for the second year. During the second year you still want to know that the rate was 5% in the previous year. An application can combine logic and corresponding table designs to track such date effective data. But the valid time state feature makes this task much simpler in Microsoft Dynamics AX.

On a table in the AOT, you can set the **ValidTimeStateFieldType** property to make it a valid time state table. That causes the system to automatically add the ValidFrom and ValidTo columns which track a date range in each row. The system guarantees that the values in these date or date-time fields remain valid by automatically preventing overlap among date ranges.


> [!NOTE]
> <P>The <STRONG>ValidTimeStateFieldType</STRONG> property cannot be set for any table that inherits from another table.</P>



The ValidFrom and ValidTo columns can both be of the date data type, or can both be of the utcDateTime data type.

Each valid time state table relies on an alternate key index. For example, suppose the table manages the relationship between employees and the projects they work on. The table would have employeeID and projectID as foreign key fields. The alternate key index would have the employeeID and projectID fields, plus the ValidFrom and ValidTo fields. On the index you set the **ValidTimeStateMode** property to either enable or disable gaps between date ranges.

The X++ select statement has the validTimeState keyword to filter rows by date or date range. The Query class has methods that provide filtering by date range, such as validTimeStateAsOfDateTimeRange.


> [!NOTE]
> <P>Some people search for Help topics about the valid time state feature by using the phrase date effectivity.</P>



## In This Section

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><a href="walkthrough-creating-a-valid-time-state-table.md">Walkthrough: Creating a Valid Time State Table</a></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><a href="effects-of-valid-time-state-tables-on-read-and-write-operations.md">Effects of Valid Time State Tables on Read and Write Operations</a></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><a href="cardinality-in-valid-time-state-table-relationships.md">Cardinality in Valid Time State Table Relationships</a></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>


## See also

[Tables, Views, and Maps](tables-views-and-maps.md)

[How to: Use the Query Class to Read From a Valid Time State Table](how-to-use-the-query-class-to-read-from-a-valid-time-state-table.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

