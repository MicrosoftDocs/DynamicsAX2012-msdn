---
title: Table Groups
TOCTitle: Table Groups
ms:assetid: 3330d438-ab53-44db-9a9b-a044ed19608d
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa623733(v=AX.60)
ms:contentKeyID: 35241993
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Table Groups [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Table groups provide a method for categorizing tables according to the type of data they contain. Determining group membership is not an exact science but more of a conceptual definition. When determining group membership for your own tables, follow the standards in the Microsoft Dynamics AX application.

When exporting data, you can use table groups to filter records. For example, if you wanted to specify that customers should be exported but customer transactions should not. The table group that a table belongs to is defined by the TableGroup property of the table.

The available table group values are listed in the following table.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Table group</p></th>
<th><p>Use this group for a table with these characteristics</p></th>
<th><p>Examples</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Parameter</p></td>
<td><p>The table contains data primarily used as parameters or setup information for one of the main tables (a table that has a TableGroup property of Main).</p>
<p>The table typically contains only one record per company.</p></td>
<td><p>CustParameters, VendParameters</p></td>
</tr>
<tr class="even">
<td><p>Group</p></td>
<td><p>The table contains data primarily used to categorize one of the main tables (a table that has a TableGroup property of Main).</p>
<p>There is a one-to-many relationship between a Group table and a Main table.</p></td>
<td><p>CustGroup, VendGroup</p></td>
</tr>
<tr class="odd">
<td><p>Main</p></td>
<td><p>The table is one of the principal tables in the application and contains data for a central business object.</p>
<p>The table typically holds static, base information.</p>
<p>There is a one-to-many relationship between a Main table and a Transaction table.</p></td>
<td><p>CustTable, VendTable</p></td>
</tr>
<tr class="even">
<td><p>Transaction</p></td>
<td><p>The table contains transaction data.</p>
<p>The table is typically not used for data entry directly.</p></td>
<td><p>CustTrans, VendTrans</p></td>
</tr>
<tr class="odd">
<td><p>WorksheetHeader</p></td>
<td><p>The table typically categorizes information in the WorkSheetLine tables.</p>
<p>There is a one-to-many relationship between a WorkSheetHeader table and a WorkSheetLine table.</p></td>
<td><p>SalesTable</p></td>
</tr>
<tr class="even">
<td><p>WorksheetLine</p></td>
<td><p>The table contains information to be validated and made into transactions.</p>
<p>In comparison to the data contained in a Transaction table, the data in WorkSheetLine tables is temporary and may be deleted without affecting system stability.</p></td>
<td><p>SalesLine</p></td>
</tr>
<tr class="odd">
<td><p>Miscellaneous</p></td>
<td><p>The table does not fit in any of the other categories. This is the default value for a new table.</p></td>
<td><p>TableExpImpDef</p></td>
</tr>
</tbody>
</table>


Typically, the table groups Miscellaneous, Transaction, WorksheetHeader, and WorksheetLine are used for large tables. If you have checked the fields **Use literals in complex joins from X++** or **Use literals in join queries from forms and reports** in the server configuration, then the kernel will add a forceliterals statement to the SQL query if two or more large tables have been joined.

The groups available are defined by the system enum TableGroup.

## Table Prompts

You can specify by table group whether a prompt is displayed when records are deleted or updated in a table. These prompts are defined by navigating to **Tools** \> **Options** \> **Confirmation**.


> [!NOTE]
> <P>Regardless of what table group prompts you define, explicitly defined delete actions are respected.</P>



## See also

[Table Properties](https://msdn.microsoft.com/en-us/library/aa871620\(v=ax.60\))

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

