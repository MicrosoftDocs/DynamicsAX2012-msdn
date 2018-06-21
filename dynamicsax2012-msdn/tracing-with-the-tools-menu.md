---
title: Tracing with the Tools Menu
TOCTitle: Tracing with the Tools Menu
ms:assetid: adb215f5-8f9a-4143-a046-f8fc5f0aa52f
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa854677(v=AX.60)
ms:contentKeyID: 35249726
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Tracing with the Tools Menu [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Tracing and logging are useful ways to monitor the system. They can help diagnose both errors and performance problems.

To set the tracing options, click the **Tools** menu, click **Options**, and then click the **SQL** link. You can configure the following SQL tracing areas:

  - Multiple SQL statements

  - Long queries

  - Warnings

  - Deadlocks

For information about setting up tracing in these areas, see [Setting Up the Tracing Tools](setting-up-the-tracing-tools.md).

## Multiple SQL Statements

The tracing of SQL statements enables you to do the following:

  - Examine all the SQL statements issued, including the degree of statement reuse.

  - Compare complex X++ queries with the actual output.

  - Examine the vendor-specific, SQL-generated statements against the SQL backend database. A generated SQL statement might include Select or Insert.

  - Copy Microsoft Dynamics AX SQL statements and re-execute them in the SQL vendor tools.

## Long Queries

Long queries tracing enables you to define the maximum time (in milliseconds) that a SQL query can execute before the system terminates it.

## Warnings

The warning system alerts you when code fragments or constructions force the kernel to modify its interpretation of your SQL statements. Performance-related warnings are also issued.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Warning text</p></th>
<th><p>ID</p></th>
<th><p>Possible actions</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>XXX records in table 'myTable' retrieved from the database, but never used. Consider using FIRSTONLY, or a more selective WHERE clause.</p></td>
<td><p>W-101</p></td>
<td><p>A change might not be needed because the client doesn't have to iterate through every record available in the buffer of retrieved records. However, sometimes a more selective WHERE clause can reduce this inefficiency.</p></td>
</tr>
<tr class="even">
<td><p>No fields will be selected from table 'myTable'.</p></td>
<td><p>W-102</p></td>
<td><p>Check the source code. You might be selecting only virtual fields.</p>
<p>You might be selecting feature key disabled fields. If so, consider disabling the table or module.</p></td>
</tr>
<tr class="odd">
<td><p>No fields will be selected from table 'myTable' in join-statement containing GROUP BY.</p></td>
<td><p>W-103</p></td>
<td><p>Consider whether an EXISTS join statement might be more efficient.</p></td>
</tr>
<tr class="even">
<td><p>The field 'myTable.myField', which appears in the GROUP BY list, is not stored in the database, and is thus ignored.</p></td>
<td><p>W-104</p></td>
<td><p>Replace the display or virtual field that is listed in the GROUP BY clause with a field that is stored in a database table.</p>
<div class="mtps-table">
<div class="mtps-row">
<img src="images/Aa589339.alert_note(en-us,AX.60).gif" title="Note" alt="Note" class="note" /><strong>Note</strong>
</div>
<div class="mtps-row">
Fields that are calculated during query execution are not stored in the database.
</div>
</div></td>
</tr>
<tr class="odd">
<td><p>Field 'myTable.myField' appears more than once in select-list, only the first is actually used.</p></td>
<td><p>W-105</p></td>
<td><p>Remove the extra occurrences of the field from the select list.</p></td>
</tr>
<tr class="even">
<td><p>Field 'myTable.myField' is invalid in ORDER BY clause because an aggregate function is used.</p></td>
<td><p>W-106</p></td>
<td><p>Remove the field from the ORDER BY clause, or replace the field with another field whose values haven't been aggregated.</p></td>
</tr>
<tr class="odd">
<td><p>About to delete a record in table 'myTable', which was not selected for update (RecId is XXX).</p></td>
<td><p>W-107</p></td>
<td><p>Add the ForUpdate keyword to the query that populated the table variable.</p></td>
</tr>
<tr class="even">
<td><p>About to update a record in table 'myTable', which was not selected for update (RecId is XXX).</p></td>
<td><p>W-108</p></td>
<td><p>Add the ForUpdate keyword to the query that populated the table variable.</p></td>
</tr>
<tr class="odd">
<td><p>Index hint to index 'myIdx' on table 'myTable' eliminated in For Update query, as index is NON unique.</p></td>
<td><p>W-109</p></td>
<td><p>Remove the index hint or consider whether the index could be changed to unique.</p></td>
</tr>
<tr class="even">
<td><p>Index hint to index 'myIndex' on table 'myTable' is eliminated, since the index is disabled.</p></td>
<td><p>W-110</p></td>
<td><p>Remove the index hint or consider whether the index could be enabled.</p></td>
</tr>
<tr class="odd">
<td><p>Downloading the EntireTable-cached table 'myTable' in company 'DAT' exceeds the time-threshold (1000 ms): 1234 milliseconds used.</p></td>
<td><p>W-111</p></td>
<td><p>Modify the query to process a limited portion of the table in any one iteration or consider increasing the time threshold.</p>
<div class="mtps-table">
<div class="mtps-row">
<img src="images/Aa589339.alert_note(en-us,AX.60).gif" title="Note" alt="Note" class="note" /><strong>Note</strong>
</div>
<div class="mtps-row">
Increasing the time threshold might risk creating long database locks, or blocking or deadlocking other queries.
</div>
</div></td>
</tr>
<tr class="even">
<td><p>Downloading the EntireTable-cached table 'myTable' in company 'DAT' exceeds the record-threshold (2000): 12345 record(s) retrieved.</p></td>
<td><p>W-112</p></td>
<td><p>Modify the query to process a limited portion of the table in any one iteration, or consider increasing the record-threshold.</p>
<div class="mtps-table">
<div class="mtps-row">
<img src="images/Aa589339.alert_note(en-us,AX.60).gif" title="Note" alt="Note" class="note" /><strong>Note</strong>
</div>
<div class="mtps-row">
Increasing the record threshold might risk creating long database locks, or blocking or deadlocking other queries.
</div>
</div></td>
</tr>
<tr class="odd">
<td><p>Calls to NEXT, update(), or delete() must be performed on the buffer on the selection transaction level, or within the same transaction (TTS) scope (RecId is XXX).</p></td>
<td><p>W-113</p></td>
<td><p>Consider using the Optimistic Concurrency Control, which compares and increments record version identification values each time a record is updated. This can provide the flexibility of programmer-controlled transactions. This helps guarantee that the code is notified if another thread updates the record between the read and update of the current thread.</p></td>
</tr>
<tr class="even">
<td><p>The field 'myField' in table 'myTable' is used in a WHERE clause, but not stored in the SQL database (i.e. has no effect). The field may have been disabled by a configuration key.</p></td>
<td><p>W-114</p></td>
<td><p>Remove the derived field from the WHERE clause.</p></td>
</tr>
<tr class="odd">
<td><p>The field 'myTable.myField' appears in ORDER BY, but not in the GROUP BY list, and is ignored.</p></td>
<td><p>W-115</p></td>
<td><p>Add the field to the GROUP BY list or remove the field from the ORDER BY list.</p></td>
</tr>
<tr class="even">
<td><p>The field 'myTable.myField ' in the SELECT list, or ORDER BY is invalid and ignored because it is not contained in the GROUP BY clause.</p></td>
<td><p>W-116</p></td>
<td><p>Add the field to the GROUP BY clause or remove the field from both the SELECT list and the ORDER BY list.</p></td>
</tr>
<tr class="odd">
<td><p>Since no unique index exists for table 'myTable', the kernel will internally make index 'myIndex' unique and use that. At least one unique index is required to update or delete records in the database.</p></td>
<td><p>W-117</p></td>
<td><p>Create a unique index on 'myTable'.</p></td>
</tr>
<tr class="even">
<td><p>Since no indexes exist for table 'myTable', the kernel will internally enable the 'CreateRecidIndex' table-property and use the 'myIndex' index. At least one unique index is required to update or delete records in the database.</p></td>
<td><p>W-118</p></td>
<td><p>Create a unique index on 'myTable'.</p></td>
</tr>
<tr class="odd">
<td><p>SELECT on table 'myTable' has a WHERE part, but no index match. Query might table scan.</p></td>
<td><p>W-119</p></td>
<td><p>Create an index on 'myTable' to improve performance.</p></td>
</tr>
<tr class="even">
<td><p>Call to WWW on XXX was converted into a simpler and less optimal record-by-record operation (YYY records affected by the operation). Reason: ZZZ.</p></td>
<td><p>W-120</p></td>
<td><p>Create an index to avoid the record-by-record access plan.</p></td>
</tr>
<tr class="odd">
<td><p>FORUPDATE cannot be used on view 'myView', since views are read-only. The directive is discarded.</p></td>
<td><p>W-121</p></td>
<td><p>Rewrite FORUPDATE to target a table rather than a view.</p></td>
</tr>
<tr class="even">
<td><p>Update must be performed inside a transaction.</p></td>
<td><p>W-122</p></td>
<td><p>Place a transaction scope around your Update.</p></td>
</tr>
<tr class="odd">
<td><p>Delete must be performed inside a transaction.</p></td>
<td><p>W-123</p></td>
<td><p>Place a transaction scope around your Delete.</p></td>
</tr>
</tbody>
</table>


## Deadlocks

Deadlock detection is an integrated part of Microsoft Dynamics AX. Deadlock detection remains in effect even if you disable the Deadlocks trace feature.

Most deadlocks are caught within try blocks in X++, meaning that the operation is re-executed. Potential problems might be hidden.

Tracing deadlocks can be used to identify tables or other database resources that cause conflicts between concurrent queries.

## See also

[Extending the Tracing Tools](extending-the-tracing-tools.md)

[Optimistic Concurrency Control](optimistic-concurrency-control.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

