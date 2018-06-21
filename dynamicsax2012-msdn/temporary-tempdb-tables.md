---
title: Temporary TempDB Tables
TOCTitle: Temporary TempDB Tables
ms:assetid: 56fc5a11-968f-4583-8208-458e2e14847d
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg845661(v=AX.60)
ms:contentKeyID: 35244333
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Temporary TempDB Tables [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

In Microsoft Dynamics AX, one type of temporary table is a TempDB table. We call them TempDB tables because their **TableType** property value is **TempDB**. This value comes from the TableType::TempDB enum value. The **TableType** property value can be set at **AOT** \> **Data Dictionary** \> **Tables** \> MyTempDBTable \> **Properties** \> **TableType**.

All types of temporary tables are automatically dropped by the system when the table variable in X++ goes out of scope. A TempDB table is not dropped when you set its record buffer variable to null.

TempDB tables are a different type of temporary table than InMemory tables. For more information, see [Temporary InMemory Tables](temporary-inmemory-tables.md).

## Capabilities of TempDB Tables

The following table describes the capabilities of TempDB tables.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Capability</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Can be <a href="select-statement-examples.md">joined</a>.</p></td>
<td><p>Your X++ SQL code can join a TempDB table to a regular table to perform multi-row operations in a single call.</p></td>
</tr>
<tr class="even">
<td><p>Can be either per company or global.</p></td>
<td><p>The <strong>SaveDataPerCompany</strong> property on a TempDB table can be set to either <strong>Yes</strong> or <strong>No</strong>. The value of <strong>No</strong> makes it a global table. For more information, see <a href="https://msdn.microsoft.com/en-us/library/aa871620(v=ax.60)">Table Properties</a>.</p></td>
</tr>
<tr class="odd">
<td><p>Can be used from Enterprise Portal by using <a href="net-business-connector-overview.md">.NET Business Connector</a>.</p></td>
<td><p>TempDB tables can be used by forms, and in X++ code that is not tied to any user interface. But TempDB tables cannot be used directly by Enterprise Portal data sets.</p></td>
</tr>
<tr class="even">
<td><p>Can have <a href="how-to-add-a-relation-to-a-table.md">foreign key</a> columns.</p></td>
<td><p>A TempDB table can have a foreign key column that references the primary key of another table. However, no table can have a foreign key column that references the primary key of a TempDB table.</p></td>
</tr>
<tr class="odd">
<td><p>TempDB tables can be instantiated from the client or server tier.</p></td>
<td><p>TempDB tables can be used by logic that runs on the client tier or the Application Object Server (AOS) tier.</p></td>
</tr>
<tr class="even">
<td><p>Can have <a href="how-to-create-an-index.md">indexes</a> columns.</p></td>
<td><p>A TempDB table can have indexes defined for it in the AOT.</p></td>
</tr>
<tr class="odd">
<td><p>Can have methods, but cannot <a href="overriding-a-method.md">override</a>.</p></td>
<td><p>You can add methods to a TempDB table. However, you cannot override any methods that come with a new TempDB table.</p></td>
</tr>
<tr class="even">
<td><p>Usable as a query <a href="how-to-add-multiple-data-sources-to-a-query.md">How to: Add Multiple Data Sources to a Query</a>.</p></td>
<td><p>A query under <strong>AOT</strong> &gt; <strong>Queries</strong> can reference a TempDB table as a data source.</p></td>
</tr>
<tr class="odd">
<td><p><a href="how-to-use-the-unitofwork-class-to-manage-database-transactions.md">Transaction support</a>.</p></td>
<td><p>The underlying database management system does provide transaction support for each instance of a TempDB table, just as it does for any regular table. Each instance is a separate table that is unrelated to the other instances, and each instance has a brief lifetime.</p></td>
</tr>
<tr class="even">
<td><p>No <a href="how-to-create-and-apply-a-configuration-key.md">configuration key</a>.</p></td>
<td><p>No configuration key is needed for you to use a TempDB table.</p>
<p>Also, tables are treated as TempDB tables while their configuration key is turned off.</p></td>
</tr>
</tbody>
</table>


## Limitations of TempDB Tables

The following table describes the limitations of TempDB tables.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Limitation</p></th>
<th><p>Descriptions</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Cannot be a <a href="valid-time-state-tables-and-date-effective-data.md">valid time state table</a>.</p></td>
<td><p>The <strong>ValidTimeStateFieldType</strong> property is restricted to the default value of <strong>None</strong>. This means the system cannot managed date effective data in a TempDB table.</p></td>
</tr>
<tr class="even">
<td><p>Cannot have any <a href="how-to-create-delete-actions.md">delete actions</a>.</p></td>
<td><p>A TempDB table cannot have any delete actions defined under its <strong>DeleteActions</strong> node in the AOT.</p></td>
</tr>
<tr class="odd">
<td><p>No Record Level Security (<a href="record-level-security.md">RLS</a>).</p></td>
<td><p>RLS is not applied to TempDB tables.</p></td>
</tr>
<tr class="even">
<td><p>Cannot use the <a href="overriding-a-method.md">Table browser form</a>.</p></td>
<td><p>To add records to a regular table you can right-click its node in the AOT, and then click <strong>Open</strong>. This opens the <strong>Table browser</strong> form. By pressing the keys Ctrl+N, you can add records. However, the <strong>Table browser</strong> form is not supported for TempDB tables. This is because a TempDB table exists only during the scope of a method that instantiates it.</p></td>
</tr>
<tr class="odd">
<td><p>Cannot be in a <a href="best-practices-for-table-collections.md">table collection</a>.</p></td>
<td><p>No type of temporary table can be in a table collection.</p></td>
</tr>
<tr class="even">
<td><p>No <a href="view-basics.md">view</a> support.</p></td>
<td><p>No view in the AOT can reference a TempDB table. When a view is created under <strong>AOT</strong> &gt; <strong>Data Dictionary</strong> &gt; <strong>Views</strong> and is saved, the view is synchronized to the underlying database system. At that moment the view must be created by the database system. But each TempDB table is rarely present in the database, because the TempDB table exists only during the scope of the method that instantiates the table. Therefore, the TempDB table is usually not available in the database for any database view to reference the TempDB table.</p></td>
</tr>
</tbody>
</table>


## Lifetime of TempDB Tables

A TempDB table is instantiated in the underlying database management system when the first SQL operation is sent to the database system from the AOS. The SQL operation can be either select, insert, update, or delete.

The following table describes the situations that cause a TempDB table to be dropped.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Cause of drop</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Variable goes out of scope.</p></td>
<td><p>The typical case is that a method declares a variable for the particular TempDB type. The method inserts data into the TempDB table. The insert causes the table to be instantiated in the database. When the method finishes, all variables declared in the method go out of scope. The AOS tells the database system to drop the TempDB table when its corresponding variable does out of scope.</p></td>
</tr>
<tr class="even">
<td><p>Controlled restart of the AOS.</p></td>
<td><p>When you stop and restart the AOS, the AOS tells the database system to drop all TempDB tables.</p></td>
</tr>
<tr class="odd">
<td><p>Restart of the database system.</p></td>
<td><p>All TempDB table instances are dropped whenever the database management system is stopped and restarted.</p>
<p>TempDB tables could be left in the underlying database if the AOS service ends suddenly, such as by a hardware power failure. There would be no automatic mechanism to promptly drop the tables.</p></td>
</tr>
<tr class="even">
<td><p>Closure of the AX32.exe client.</p></td>
<td><p>Suppose that from your AX32.exe client you start a job from <strong>AOT</strong> &gt; <strong>Jobs</strong>. The job calls a server method that instantiates a TempDB table. Then you close your AX32.exe program when the server method is still running. This ends your Microsoft Dynamics AX session and immediately ends the server method. All variables declared in the method are now out of scope. Therefore, the AOS tells the database system to drop the TempDB table.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Online Users</strong> form.</p></td>
<td><p>The <strong>Online Users</strong> form can be used to end any Microsoft Dynamics AX session that is associated with TempDB tables that have not been dropped automatically. The form is available in the content pane at <strong>Administration</strong> &gt; <strong>Administration Area</strong> &gt; <strong>Common forms</strong> &gt; <strong>Online users</strong>.</p></td>
</tr>
</tbody>
</table>


## TempDB Tables for Disabled Tables

You can disable a regular persisted database table by disabling the [configuration key](how-to-create-and-apply-a-configuration-key.md) that controls the table. Disabling the key causes the system to automatically create a TempDB style of temporary table that matches the fields and schema of the database table. This temporary table exists in the underlying SQL Server database and is managed by the Application Object Server (AOS).

The purpose of automatically creating this TempDB table is to enable AOT objects that reference the disabled table to continue to compile and run. You can read and write to this TempDB table even though the configuration key is disabled.

All table buffer variables inherit the methods of the xRecord class. One such method is setTmp, which creates an InMemory temporary table that has the same schema as the regular table. However, the setTmp method cannot create an InMemory table from a TempDB table. You can call the method isTempDb to determine whether the setTmp method is available.

## X++ Code Example

The following X++ code example assumes that a TempDB table which is named **MyTempdb** has already been defined under **AOT** \> **Data Dictionary** \> **Tables**. The **MyTempdb** table has one column that is the same type as the **AccountNum** column on the **CustTable** table. The while select statement in the example contains a JOIN clause that cannot be used with temporary InMemory tables.

    server public static void main(Args _args)
    {
        MyTempdb xrecMyTempdb;
        CustTable xrecCustTable;
        TableType tableTypeEnum;
        str stringWork;
    
        Global::info("Start of main.");
    
        xrecMyTempdb.AccountNum = "4004";
        xrecMyTempdb.doInsert();
        xrecMyTempdb.AccountNum = "4005";
        xrecMyTempdb.doInsert();
    
        tableTypeEnum = xrecMyTempdb.getTableType();
        stringWork = "MyTempdb.TableType is: " + enum2Str(tableTypeEnum);
        info(stringWork);
    
        while select *
                from xrecCustTable
                    JOIN xrecMyTempdb
                where
                    xrecMyTempdb.AccountNum == xrecCustTable.AccountNum
        {
            stringWork = xrecCustTable.AccountNum
                    + " , "
                    + int2Str(xrecCustTable.MandatoryCreditLimit);
            info(stringWork);
        }
    }
    /*** Infolog outputMessage (05:21:28 pm)
    Start of main.
    MyTempdb.TableType is: TempDB
    4004 , 0
    4005 , 1
    ***/

## See also

[Temporary Tables and the TableType Property](temporary-tables-and-the-tabletype-property.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

