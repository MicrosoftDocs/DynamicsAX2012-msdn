---
title: Best Practices for Table Properties
TOCTitle: Table Properties
ms:assetid: 5def498e-107d-4a2b-a621-fbbe0243e399
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa632254(v=AX.60)
ms:contentKeyID: 35244415
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Best Practices for Table Properties 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The following table describes the Microsoft Dynamics AX standards and best practices (rules) for setting table properties. The properties are in the same order as the UI and related properties are grouped together.

For a description of each property, see [Table Properties](https://msdn.microsoft.com/en-us/library/aa871620\(v=ax.60\)).

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
<td><p>Prefix with the module name. For example, Cust, Vend, or Invent.</p>
<p>Infix with a logical description of the contents. For example, CustCollectionLetterTrans, where CollectionLetter is the infix. For temporary tables, infix with Tmp. For example, CustTmpLedger.</p>
<p>Postfix with the type of contents. For example, Trans, Jour, Line, Table, Group, Parameters, or Setup.</p>
<p>The primary tables for the major business areas are postfixed with Table. For example, CustTable, InventTable, and VendTable.</p></td>
</tr>
<tr class="even">
<td><p>Label</p></td>
<td><p>Mandatory unless the table has the Visible property set to No. An error occurs if:</p>
<ul>
<li><p>You do not set this property.</p>
<p>–and–</p></li>
<li><p>Visible is not set to Yes. <img src="images/Aa872655.ErrorIcon(AX.60).gif" title="Error icon" alt="Error icon" /></p></li>
</ul>
<p>The text value of the label must be unique across all tables (excluding temporary tables), views, and maps, in all languages. <img src="images/Aa872655.ErrorIcon(AX.60).gif" title="Error icon" alt="Error icon" /></p></td>
</tr>
<tr class="odd">
<td><p>FormRef</p></td>
<td><p>For tables where the FormRef property is set to a display menu item, the display menu item must exist. <img src="images/Aa872655.ErrorIcon(AX.60).gif" title="Error icon" alt="Error icon" /></p></td>
</tr>
<tr class="even">
<td><p>TitleField1, TitleField2</p></td>
<td><p>Mandatory unless:</p>
<ul>
<li><p>The Visible property for the table is set to <strong>No</strong>.</p>
<p>–or–</p></li>
<li><p>The TableGroup property is set to <strong>Parameter</strong>. <img src="images/Aa872655.ErrorIcon(AX.60).gif" title="Error icon" alt="Error icon" /></p></li>
</ul>
<p>Don't set this property if there are not enough fields (according to your needs) in the table. (Fields of type real or integer should not be used as title fields.)</p>
<p>Specify the two best fields for TitleField1 and TitleField2 according to the following:</p>
<ul>
<li><p>TitleField1 – The key field for the records in the table. Use a descriptive title if the key field has information for the user.</p></li>
<li><p>TitleField2 – A descriptive field for the records in the table.</p></li>
</ul>
<p>For example, for the Table InventItemGroup table, TitleField1 is ItemGroupId, and TitleField2 is Name.</p>
<p><span id="rx08title12diffval"></span>If the value of TitleField1 and TitleField2 is the same, an error occurs.<img src="images/Aa872655.ErrorIcon(AX.60).gif" title="Error icon" alt="Error icon" /></p></td>
</tr>
<tr class="odd">
<td><p>TableType</p></td>
<td><p>Starting in Microsoft Dynamics AX 2012, all tables have the TableType property that replaces the Temporary property found in Microsoft Dynamics AX 2009 and earlier versions.</p>
<p>Use the setTmp table method to make a non-temporary table temporary rather than creating a copy of the table, and then making it temporary. The two versions of the table can quickly become out of sync.</p></td>
</tr>
<tr class="even">
<td><p>TableContents</p></td>
<td><p>Leave this property set to <strong>Not Specified</strong> for most tables.</p>
<p>Set to <strong>Default Data</strong> for customer-independent data. For example, time intervals and unit conversions.</p>
<p>Set to <strong>Base Data</strong> for customer-dependent data. This data is often from an existing system that has been imported or entered into Microsoft Dynamics AX. For example, customers and vendors.</p>
<p>Set to <strong>Default+Base Data</strong> for data that can be customer-dependent in some countries/regions, but not in others.</p></td>
</tr>
<tr class="odd">
<td><p>SystemTable</p></td>
<td><p>Set this property to <strong>Yes</strong> if you want the table to be designated as a system table. For example, the information about the system table is used during export and import when system tables can be filtered out. Don't overuse this feature.</p></td>
</tr>
<tr class="even">
<td><p>ConfigurationKey</p></td>
<td><p>Set the ConfigurationKey property for most tables. This ensures that the table is removed when the key is disabled. Configuration keys allow a system administrator to enable and disable certain parts of an application.</p></td>
</tr>
<tr class="odd">
<td><p>SecurityKey</p></td>
<td><p>In Microsoft Dynamics AX 2012, security keys are obsolete and only remain for upgrade purposes.</p></td>
</tr>
<tr class="even">
<td><p>Visible</p></td>
<td><p>Mandatory.</p>
<p>If the table is a transactions table, set this property to <strong>Yes</strong>.</p></td>
</tr>
<tr class="odd">
<td><p><span id="rx27tabnocache"></span> CacheLookup</p></td>
<td><p>Set to the <strong>EntireTable</strong> value for the following tables:</p>
<ul>
<li><p>Contains static data (for example: some Main, and most Group and Parameter tables).</p></li>
<li><p>Are frequently accessed by the NotFound cache when it hits select statements. For example:</p>
<ul>
<li><p>while select.</p></li>
<li><p>== selects something that doesn't match the cache candidate key.</p></li>
<li><p>select using relational operators other than == (such as &lt;, &gt; and so on).</p></li>
</ul></li>
<li><p>Has a moderate number of records (hundreds or thousands, but not millions).</p></li>
<li><p>Is obvious that one select statement to the database outperforms select statements to the database.</p></li>
</ul>
<p>If a table performs poorly when the cache type is set to EntireTable, it is possible to change the cache setting to FoundAndEmpty or Found for a particular installation.</p>
<p>Tables with the cache type set to EntireTable should have a Cluster index. This ensures that the table loads as quickly as possible.</p>
<p>When your code attempts to find a record in a cache by using a utility class such as SysGlobalCache or SysGlobalObjectCache, your code might get a return code which indicates the record is not in the cache. You code must then get the record by using a normal query. After the query returns the record, your code should add the record to the cache. If most of the find attempts indicate the needed records are not already in the cache, it might make sense to discontinue caching the table.</p>
<p>Remove Found caching from tables that have no unique index.</p></td>
</tr>
<tr class="even">
<td><p><span id="yb07recididxunneed"></span> CreateRecIdIndex</p></td>
<td><p>Set this property to Yes only if you actually need an index on the Record ID field. <img src="images/Aa658028.WarningIcon(en-us,AX.60).gif" title="Warning icon" alt="Warning icon" /> All tables have a Record ID index, but the index is set to Passive when the CreateRecIdIndex property is set to No.</p></td>
</tr>
<tr class="odd">
<td><p>SaveDataPerCompany</p></td>
<td><p>Set to Yes for company-specific tables.</p>
<p>Set to No if the data is related to cross-companies, installation, a database, the AOT, tracing, or OLAP. For example, SysTraceTable or OLAPServerTable.</p>

> [!note]  
> <P>If the SaveDataPerCompany property on a table is set to Yes, the SetCompany property on a form design that uses that table as a data source must also be set to Yes.</P>

</td>
</tr>
<tr class="even">
<td><p><span id="yb97mandtabgrp"></span> TableGroup</p></td>
<td><p>Mandatory. <img src="images/Aa658028.WarningIcon(en-us,AX.60).gif" title="Warning icon" alt="Warning icon" /></p>
<p>Set to Group for tables that contain grouping and categorizing information. If the parent table is also a Group table, you only sometimes establish delete actions for a table that relates to a group table.</p>
<p>Deleting records from a group table can sometimes result in an unstable situation. Enable confirm deletion. For more information, see <a href="maintaining-data-integrity.md">Maintaining Data Integrity</a>.</p>
<p>Typical examples of Group tables from the standard application are CustGroup and VendGroup.</p>
<p>Set to Main for tables that contain base data.</p>

> [!note]  
> <P>Consider using an alias field for all tables that have the TableGroup property set to Main. Alias fields are set by using the AliasFor property on the field. For example, a phone number could be an alias for a customer ID. When the phone number is entered, it is automatically replaced by the customer's ID.</P>

</td>
</tr>
<tr class="odd">
<td><p><span id="yb96uniqidxneedprim"></span> PrimaryIndex</p></td>
<td><p>Mandatory property for tables that have a unique index. <img src="images/Aa658028.WarningIcon(en-us,AX.60).gif" title="Warning icon" alt="Warning icon" /></p>
<p>If there is more than one unique index, this property determines which index Found caching works on.</p></td>
</tr>
<tr class="even">
<td><p>ClusterIndex</p></td>
<td><p>Set the index that the table should be organized by.</p>
<p>Leave the index blank if performance tests on realistic data show that clustering does not work better. You can measure performance along the following dimensions:</p>
<ul>
<li><p>Amount of space that the index consumes on the disk and in memory.</p></li>
<li><p>Speed of CRUD operations (Create, Read, Update, Delete).</p></li>
</ul>
<p>For more information, see <a href="clustered-indexes.md">Clustered Indexes</a>.</p></td>
</tr>
<tr class="odd">
<td><p><span id="rx75typicrowcount"></span> TypicalRowCount</p></td>
<td><p>Select a value that corresponds to the number of rows that the table will probably have.</p></td>
</tr>
<tr class="even">
<td><p>IsLookup</p></td>
<td><p>Set to Yes if the table consists of only a primary key and one other field.</p></td>
</tr>
<tr class="odd">
<td><p><span id="rx72singlabel"></span> SingularLabel</p></td>
<td><p>Mandatory if you have set the AnalysisVisibility property to Yes. <img src="images/Aa872655.ErrorIcon(AX.60).gif" title="Error icon" alt="Error icon" /></p></td>
</tr>
<tr class="even">
<td><p>ModifiedDateTime</p></td>
<td><p>Set this property to Yes only if you need the information it provides.</p></td>
</tr>
<tr class="odd">
<td><p>ModifiedTime</p></td>
<td><p>Set this property to Yes only if you need the information it provides.</p></td>
</tr>
<tr class="even">
<td><p>ModifiedBy</p></td>
<td><p>Set this property to Yes only if you need the information it provides.</p></td>
</tr>
<tr class="odd">
<td><p>CreatedTransactionId</p></td>
<td><p>Enable the CreatedTransactionId property if your table has the TableGroup property set to Transaction.</p>
<p>If the TableGroup property is not set to Transaction, set the CreatedTransactionId property only if you need to use information about which transaction created each record in the table.</p></td>
</tr>
<tr class="even">
<td><p>CreatedBy, CreatedDateTime, and CreatedTransactionID</p></td>
<td><p>Read-only properties.</p></td>
</tr>
</tbody>
</table>


## Modified/Created Fields

The Modified/Created fields are available on all tables, but can be disabled so that space is not used for unnecessary information.

Information is also available about transaction changes for tables by doing the following:

  - Enable the TransactionLog system on all transaction tables.

  - Use the database log.

## See also

[Best Practices: Tables](best-practices-tables.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

