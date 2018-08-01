---
title: Partitions, Companies, and Data Isolation in Microsoft Dynamics AX
TOCTitle: Partitions, Companies, and Data Isolation in Microsoft Dynamics AX
ms:assetid: 1fdc4428-e235-4cd6-ae2f-f8f58f806db8
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ677285(v=AX.60)
ms:contentKeyID: 49384056
ms.date: 05/18/2015
mtps_version: v=AX.60
dev_langs:
- sql
---

# Partitions, Companies, and Data Isolation in Microsoft Dynamics AX [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

This topic provides comprehensive information about most aspects of the partition feature for the developer audience.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Section</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1. Overview of Partitions and Legal Entities</p></td>
<td><p>Explains the definition and purpose of partitions.</p></td>
</tr>
<tr class="even">
<td><p>2. The Partitions Table</p></td>
<td><p>Identifies the infrastructure that supports partitions.</p></td>
</tr>
<tr class="odd">
<td><p>3. Steps for Working with Partitions</p></td>
<td><p>Lists the sequence of major actions you can perform when you work with partitions.</p></td>
</tr>
<tr class="even">
<td><p>4. Data Access within Partitions and Companies</p></td>
<td><p>Describes the special processing that the Application Object Server (AOS) applies to queries that involve partitions.</p></td>
</tr>
<tr class="odd">
<td><p>5. Data at Different Isolation Levels</p></td>
<td><p>Describes the type of data that is shared across partitions and companies at different levels of data isolation.</p></td>
</tr>
</tbody>
</table>


## 1\. Overview of Partitions and Legal Entities

### ![JJ677285.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "JJ677285.collapse_all(en-us,AX.60).gif")1.1 Definition of Partition

In the [glossary](https://msdn.microsoft.com/en-us/library/hh208626\(v=ax.60\)) for Microsoft Dynamics AX, the formal definition of a partition is: “A division of an application’s processing into logical or functional parts.”

Partitions divide and isolate the business data of an installation by using special processing that the AOS applies to data queries. This special processing occurs immediately before the queries are sent to the underlying Microsoft SQL Server database when a system field named **Partition** is present in a queried table.

### ![JJ677285.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "JJ677285.collapse_all(en-us,AX.60).gif")1.2 Purpose of Partitions

The purpose of a partition is to logically separate the data within its boundaries from the data in other partitions. A partition enables the AOS to isolate the data in the partition from users who are not authorized to access the data.

For example, a holding corporation might have several subsidiaries or other legal entities. An installation of Microsoft Dynamics AX for the corporation can have several partitions, perhaps one for each subsidiary.

### ![JJ677285.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "JJ677285.collapse_all(en-us,AX.60).gif")1.3 Relation between Legal Entities and Partitions

Each partition contains at least one company or legal entity. A legal entity occurs in only one partition. When you create a legal entity, the system assigns it to the current partition. The legal entity can never be moved to another partition. However, its data can be exported from the partition and then imported to another company in another partition.


> [!NOTE]
> <P>Partitions were added starting in Microsoft Dynamics AX 2012 R2. When you upgrade from a version that did not support partitions, you must assign the existing companies or legal entities to one or more partitions during upgrade.</P>



For more information including a diagram of the partition architecture, see [Data partitioning architecture](https://msdn.microsoft.com/en-us/library/jj728665\(v=ax.60\)).

## 2\. The Partitions Table

The system stores information about partitions in the **Partitions** system table. The **Partitions** table is located in the AOT under **System Documentation** \> **Tables**.

### ![JJ677285.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "JJ677285.collapse_all(en-us,AX.60).gif")2.1 Fields of the Partitions Table

The **Partitions** table has the following fields:

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Field name</p></th>
<th><p>Data type</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>PartitionKey</p></td>
<td><p>String, 8 characters is the maximum length.</p></td>
<td><p>This is the short identifier that you use and see most often when interacting with the partition. For example, you can specify this value in the message header when you use AIF services.</p>
<p>The values in this field are unique. A few tables have a foreign key field that refers to this field. The AOS has no special process for foreign keys to this field.</p></td>
</tr>
<tr class="even">
<td><p>Name</p></td>
<td><p>String, 40 characters is the maximum length.</p></td>
<td><p>This is long name of the partition. This value is displayed or used in only a few places in the system.</p></td>
</tr>
<tr class="odd">
<td><p>RecId</p></td>
<td><p>This is a standard RecId system field that most tables have, of type int64.</p></td>
<td><p>The AOS has special processing for foreign key fields that reference this field. The processing adds filters to the Where clause.</p></td>
</tr>
</tbody>
</table>


Under **AOT** \> **System Documentation** \> **Types**, the following two types match fields on the **Partitions** table:

  - **Partition** – corresponds to the RecId field of the **Partitions** table.

  - **PartitionKey** – corresponds to the **PartitionKey** field of the **Partitions** table.

### ![JJ677285.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "JJ677285.collapse_all(en-us,AX.60).gif")2.2 Tables that are Affected by Partitions

The properties of tables in the AOT can indicate whether a given table is affected by data partitions. The following table describes database tables and their partition-related fields.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>AOT path</p></th>
<th><p>Property value</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>AOT</strong> &gt; <strong>Data Dictionary</strong> &gt; <strong>Tables</strong> &gt; SystemTable</p></td>
<td><p><strong>Systemtable</strong> = <strong>Yes</strong></p>
<p>or</p>
<p><strong>TableGroup</strong> = <strong>Framework</strong></p></td>
<td><p>These tables are used by the Microsoft Dynamics AX system. They do not contain business data. An example is the <strong>AifAction</strong> framework table.</p>
<p>The <strong>AifAction</strong> table is one of the few tables for which you can modify the <strong>SaveDataPerPartition</strong> property by using the <strong>Properties</strong> window. Do not modify the value of this property. The system might change this value.</p></td>
</tr>
<tr class="even">
<td><p><strong>AOT</strong> &gt; <strong>Data Dictionary</strong> &gt; <strong>Tables</strong> &gt; BusinessTable</p></td>
<td><p><strong>Systemtable</strong> = <strong>No</strong></p>
<p>and</p>
<p><strong>TableGroup</strong> != Framework</p></td>
<td><p>Most tables that contain business-related data are in this category. These tables have a system field named <strong>Partition</strong>.</p>
<p>Examples include the <strong>BankAccountTable</strong> and <strong>CustTable</strong> tables.</p>
<p>When you create a new table, the system adds the <strong>Partition</strong> field.</p>
<p>The Partition field never appears in the Fields list for the table. However, the Partition field is visible in the underlying SQL Server database.</p></td>
</tr>
<tr class="odd">
<td><p><strong>AOT</strong> &gt; <strong>Data Dictionary</strong> &gt; <strong>Tables</strong> &gt; InformalPartitionedTable</p></td>
<td><p>Not applicable.</p></td>
<td><p>A small number of tables do not have the system <strong>Partition</strong> field, but do have a <strong>PartitionKey</strong> field as a foreign key. Examples include the <strong>AifGatewayQueue</strong> and <strong>AifInboundPort</strong> tables.</p></td>
</tr>
<tr class="even">
<td><p><strong>AOT</strong> &gt; <strong>System Documentation</strong> &gt; <strong>Tables</strong></p></td>
<td><p>Not applicable.</p></td>
<td><p>Some tables in this area of the AOT do have a <strong>Partition</strong> field. An example is the <strong>DataArea</strong> table.</p>
<p>Other tables in this area do not have a <strong>Partition</strong> field. An example is the <strong>TimeZonesList</strong> table.</p></td>
</tr>
</tbody>
</table>


## 3\. Steps for Working with Partitions

The following subsections show the high-level steps that you perform when you work with partitions.

### ![JJ677285.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "JJ677285.collapse_all(en-us,AX.60).gif")3.1 Add a Partition by using the Partitions Form

You add a new partition by using the **Partitions** form. You can access the form from the following locations:

  - **System administration** \> **Area page** \> **Setup** \> **Partitions**

  - **AOT** \> **Forms** \> **PartitionAdministration** \> **Open**

The following columns are displayed in the **Partitions** form:

  - **Partition Key** – The short 8 character name or identifier of the partition. This name must be unique across the installation.  
    The values in this column correspond to the PartitionKey fields that are in some tables in the system.

  - **Name** – A short description of the partition, with a maximum length of 40 characters.

The **Partitions** form does not display the RecId value. The values in a **RecId** column correspond to values in the Partition fields on tables throughout the system.

A new installation of Microsoft Dynamics AX creates a default partition named **initial**. The following image shows the **Partitions** form after some partitions have been added.

![Partitions administration form](images/JJ677285.PartitionAdministration-Form-c(en-us,AX.60).png "Partitions administration form")

You can never delete a partition.

#### ![JJ677285.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "JJ677285.collapse_all(en-us,AX.60).gif")3.1.1 To add a partition

1.  Click the **Add** button. This creates a new row in the grid.

2.  Enter string values into the cells of the new row.

3.  To commit the add, give focus to another row, or click the **Close** button to exit the form.

### ![JJ677285.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "JJ677285.collapse_all(en-us,AX.60).gif")3.2 Switch to another Partition

When you start the AX32.exe client, your session is assigned to one partition context for that whole session. You can switch to another partition only by starting a new client session.

When you start a new client session, the system reads a variety of items to determine which partition is specified for your session. The process reads items in the sequence that they are listed in the following table. The process stops when it finds that a partition is specified.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Item</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Command-line option</p></td>
<td><p>You can start the client at a command prompt in a cmd.exe window. You can add the –partition parameter with a <strong>Partition Key</strong> value, by using the following format:</p>
<p>ax32.exe -partition=partition_key</p></td>
</tr>
<tr class="even">
<td><p>The <strong>Partition</strong> setting in the client configuration tool.</p></td>
<td><p>This text box control is located in the <strong>General</strong> tab. By default, the text box is empty.</p>
<p>The client configuration for each user is stored as an entry in the following subkey in the registry:<br />
 <strong>HKEY_CURRENT_USER\Software\Microsoft\Dynamics\6.0\Configuration\</strong>.</p></td>
</tr>
<tr class="odd">
<td><p>The default partition for the user.</p></td>
<td><p>In the <strong>Users</strong> form, the system administrator can select one user record in the grid, and then click the <strong>Edit</strong> menu. The form then shows a check box that is labeled <strong>Current partition is default partition</strong>. If the user is authorized for more than one partition, the administrator can select the check box to make the current partition be the default partition for the user.</p>
<p>The <strong>Users</strong> form and its check box control are discussed further elsewhere in this topic.</p></td>
</tr>
<tr class="even">
<td><p>The <strong>initial</strong> partition.</p></td>
<td><p>The <strong>initial</strong> partition is used if no other partition is specified. The <strong>initial</strong> partition is part of every system.</p></td>
</tr>
</tbody>
</table>


If you specify a partition for which you do not have authorization, an error message is displayed, and then the empty client window closes.

### ![JJ677285.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "JJ677285.collapse_all(en-us,AX.60).gif")3.3 Perform the Partition Initialization Checklist

The **Partition initialization checklist** is displayed the first time that you start the client in the context of a newly created partition. All tasks in the checklist are optional. Even if you mark all checklist items as complete, you can return to the checklist at any time. To return to the checklist, navigate as follows:  
 Click **System administration** \> **Setup** \> **Checklists** \> **Partition initialization checklist**.

![The Partition initialization checklist.](images/JJ677285.PartitionInitalizationChecklist-AX62-c4(en-us,AX.60).png "The Partition initialization checklist.")

### ![JJ677285.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "JJ677285.collapse_all(en-us,AX.60).gif")3.4 Assign a User to One or More Partitions

A system might have several partitions. A typical user has authorization in only one partition. However, some users might be authorized to see data in more than one partition. System administrators are authorized to see data in all partitions.

Use the **Users** form to add a user to the current partition. You can open the **Users** form as follows:  
 Click **System administration** \> **Common** \> **Users** \> **Users**.

The **Users** form contains a check box that is labeled **Current partition is default partition**. This setting is considered in the startup sequence that determines the partition context for a client session.

### ![JJ677285.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "JJ677285.collapse_all(en-us,AX.60).gif")3.5 Administer the Legal Entities in a New Partition

When you create a new partition, the system adds one legal entity or company in the new partition. The short **Company** code value for the new company is always **DAT**. However, because each **DAT** company is in a different partition, each is a separate company from the others. You cannot change the value of the **Company** code. You can change the longer company **Name** value by using the **Legal entities** form. Or, you can add another company to the new partition.

To access the **Legal entities** form, navigate as follows:  
 Click **Organization administration** \> **Setup** \> **Organization** \> **Legal entities**.

The **Legal entities** form displays only the companies that are in the current partition.

## 4\. Data Access within Partitions and Companies

Queries of business data are restricted to the partition context of the current client session. Typically queries are also restricted to data for the current company, although you can sometimes query across multiple companies. These restrictions apply to **AOT** \> **Queries** and to X++ SQL.

### ![JJ677285.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "JJ677285.collapse_all(en-us,AX.60).gif")4.1 X++ SQL is Restricted to Current the Partition

The SQL statements in your X++ code are sent to the AOS for additional processing. The AOS generates Transact-SQL statements for SQL Server. The generated T-SQL often includes additional filters that are applied under the Where clause. The AOS adds filters for the current partition and the current company of your session. The filters target the fields named **Partition** and **DataAreaId**.

Do not add filters for partition and company to your X++ SQL source code.

### ![JJ677285.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "JJ677285.collapse_all(en-us,AX.60).gif")4.2 Caching, Flushing, and Partitions

Suppose a table has its **SaveDataPerPartition** property set to **Yes**, meaning the table has the **Partition** system field. The system can maintain data from the table in a data cache. Cached data for one partition can never be access from a second partition. However, a cache flush command that is issued in one partition can sometimes flush data for all partitions.

The value of the table’s **CacheLookup** property affects whether a cache flush that is issued in one partition affects all partitions. The details are shown in the following table.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p><strong>CacheLookup</strong> value</p></th>
<th><p>Effect of flush</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><ul>
<li><p><strong>EntireTable</strong></p></li>
</ul></td>
<td><p>Data for only the current partition is flushed from the data cache.<br />
But data for other partitions is not flushed and remains unaffected.</p></td>
</tr>
<tr class="even">
<td><ul>
<li><p><strong>Found</strong></p></li>
<li><p><strong>FoundAndEmpty</strong></p></li>
<li><p><strong>NotInTTS</strong></p></li>
</ul></td>
<td><p>Data for the current partition is flushed from the data cache.<br />
And data for other partitions is also flushed.</p></td>
</tr>
<tr class="odd">
<td><ul>
<li><p><strong>None</strong></p></li>
</ul></td>
<td><p>Not applicable.</p></td>
</tr>
</tbody>
</table>


For more information about caching, see [Record Caching](record-caching.md).

### ![JJ677285.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "JJ677285.collapse_all(en-us,AX.60).gif")4.3 Effect of the X++ crossCompany keyword

The crossCompany keyword can be added to your X++ SQL statement. The keyword suppresses the restriction that limits data access to the current company. It causes your X++ SQL statement to retrieve data regardless of what company the data is for.

The crossCompany keyword applies only to the companies that are in the current partition. The X++ crossCompany keyword is shown in the following X++ SQL code example:

while select crossCompany AccountNum from xrecCustTable {...}

For more information, see [Cross-Company Data Access](cross-company-data-access.md).

A query under **AOT** \> **Queries** that has its **AllowCrossCompany** property set to **Yes** is also restricted to the companies in the current partition.


> [!NOTE]
> <P>There is no crossPartition keyword in X++. If you must access data from multiple partitions in one statement, consider issuing direct T-SQL by using the Statement class. This is explained in the next section.</P>



### ![JJ677285.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "JJ677285.collapse_all(en-us,AX.60).gif")4.4 Data Accessed by using Direct T-SQL can Span Partitions

If you have sufficient authorization, you can use the Statement system class to issue Transact-SQL commands in a manner that bypasses the AOS and goes directly to SQL Server. When you bypass the AOS, you must decide whether your code will access data outside the current partition. In many cases, you must enforce the same restrictions that the AOS enforces. We recommend that you use Transact-SQL sparingly, and only when it is necessary.

You can use the following Transact-SQL Select statement to obtain a report of all the partitions on the system, and of all the companies that are in each partition.

``` sql
-- T-SQL to run in the Dynamics AX database directly in SQL Server:
SELECT     da1.Partition, pt2.PartitionKey, pt2.Name, da1.ID as [Company-ID]
  FROM     DataArea as da1, Partitions as pt2 
  WHERE    da1.Partition = pt2.RecId 
  ORDER BY pt2.PartitionKey, da1.ID;
```

The following output was generated by the previous T-SQL Select statement. The output report shows that our test system had two partitions. It also shows that several companies existed in the **initial** partition:

Partition   PartitionKey  Name               Company-ID   
     
 5637144827  g2part        g 2 partition      DAT   
 5637144576  initial       Initial Partition  CEBD   
 5637144576  initial       Initial Partition  CEU   
 5637144576  initial       Initial Partition  DAT   
 5637144576  initial       Initial Partition  SDKA   
 5637144576  initial       Initial Partition  SUSA


> [!NOTE]
> <P>For code examples of enforcing the partition restriction in direct T-SQL commands issued through the Statement class, see <A href="how-to-include-a-filter-for-partition-in-direct-transact-sql.md">How to: Include a Filter for Partition in Direct Transact-SQL</A>.</P>



## 5\. Data at Different Isolation Levels

The following table describes the type of data that is shared across partitions and companies at different levels of data isolation.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Scope of sharing</p></th>
<th><p>Description</p></th>
<th><p>Example tables</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Shared across:</p>
<ul>
<li><p>Partitions</p></li>
<li><p>Companies</p></li>
</ul></td>
<td><p>Data that is required by the Microsoft Dynamics AX system are shared across the system.</p>
<p>The Application Object Tree (AOT) displays metadata. All elements in the AOT are shared across the system.</p></td>
<td><p>About 4% of tables belong in this sharing category. The following tables are representatives:</p>
<ul>
<li><p>AifPort</p></li>
<li><p>BatchJob</p></li>
<li><p>TimeZonesList</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Shared across:</p>
<ul>
<li><p>Companies only</p></li>
</ul></td>
<td><p>Companies that are managed together on one installation of Microsoft Dynamics AX can benefit from sharing relatively static business data when appropriate. For example, the data in code tables does not have to be provided separately for each company.</p>
<p>Tables in this sharing category have the following two system fields:</p>
<ul>
<li><p>Partition – for partition</p></li>
</ul></td>
<td><p>About 30% of tables belong in this sharing category. The following tables are representatives:</p>
<ul>
<li><p>BankStatementFormat</p></li>
<li><p>DirParyLocation</p></li>
<li><p>HCMReasonCode</p></li>
<li><p>NumberSequenceList</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Not shared.</p></td>
<td><p>Transactional business data is not shared and is specific to one company or legal entity.</p>
<p>Tables in this sharing category have the following two system fields:</p>
<ul>
<li><p>Partition – for partition</p></li>
<li><p>DataAreaId – for company</p></li>
</ul></td>
<td><p>About 66% of tables belong in this sharing category. The following tables are representative:</p>
<ul>
<li><p>BankAccountTable</p></li>
<li><p>BankAccountTrans</p></li>
<li><p>CustTable</p></li>
<li><p>SalesPool</p></li>
</ul></td>
</tr>
</tbody>
</table>


## See also

[Plan for data partitioning](https://msdn.microsoft.com/en-us/library/jj728668\(v=ax.60\))

[Configure clients to access data in a partition](https://msdn.microsoft.com/en-us/library/jj670112\(v=ax.60\))

[getCurrentPartition Function](https://msdn.microsoft.com/en-us/library/jj133001\(v=ax.60\))

[getCurrentPartitionRecId Function](https://msdn.microsoft.com/en-us/library/jj132936\(v=ax.60\))

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

