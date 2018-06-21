---
title: Temporary Tables and the TableType Property
TOCTitle: Temporary Tables and the TableType Property
ms:assetid: 9986b514-6079-499a-b491-9a95589f8229
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg863308(v=AX.60)
ms:contentKeyID: 35248035
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Temporary Tables and the TableType Property [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Starting in Microsoft Dynamics AX 2012, all tables have the **TableType** property that replaces the **Temporary** property found in Microsoft Dynamics AX 2009 and earlier versions.

## The TableType Property

The following table describes the **TableType** property.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Value</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Regular</strong></p></td>
<td><p>The default value. These are permanent tables.</p></td>
</tr>
<tr class="even">
<td><p>Temporary <strong>InMemory</strong></p></td>
<td><p>A temporary table that exists as an indexed sequential access method (ISAM) file. The ISAM file can exist on either the client tier of the Application Object Server (AOS) tier. The underlying Microsoft SQL Server has no connection to the ISAM file.</p>
<p>The system does allow you join an InMemory table in the X++ SQL syntax. However, joins and other set operations with InMemory tables are usually inefficient.</p>
<p>For more information, see <a href="temporary-inmemory-tables.md">Temporary InMemory Tables</a>.</p>
<p>An InMemory table is the same thing as what was previously called a temporary table in Microsoft Dynamics AX 2009.</p></td>
</tr>
<tr class="odd">
<td><p>Temporary <strong>TempDB</strong></p></td>
<td><p>A temporary table that resides in the TempDB database of the underlying SQL Server. The nonstandard format of a TempDB table causes the table to be dropped when it is no longer in use by the current method.</p>
<p>Joins and other set operations on TempDB tables can be efficient.</p>
<p>For more information, see <a href="temporary-tempdb-tables.md">Temporary TempDB Tables</a>.</p></td>
</tr>
</tbody>
</table>


## See also

[Tables, Views, and Maps](tables-views-and-maps.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

