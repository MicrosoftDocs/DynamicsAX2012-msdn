---
title: Form Data Source Properties
TOCTitle: Form Data Source Properties
ms:assetid: 7f4b9239-5f6b-47e6-9516-8406757047e4
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa676742(v=AX.60)
ms:contentKeyID: 35132734
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Form Data Source Properties 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The following table describes the properties that are available for form data sources.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Property</p></th>
<th><p>Description</p></th>
<th><p>New in this version of<br />
 Microsoft Dynamics AX</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>AllowCheck</strong></p></td>
<td><p>Specifies whether security checking occurs early, before the form opens.</p>
<p><strong>Yes</strong> – Before the form opens, check that the user has access to the form. A message is displayed if the form cannot open. <strong>Yes</strong> is the default, and is generally recommended.</p>
<p><strong>No</strong> – After the form opens, check whether the user has access to the form. If the user lacks access to the form, or to the underlying data sources, the form does not display any data.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>AllowCreate</strong></p></td>
<td><p>Specifies whether users can create new records in the data source (in the table).</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>AllowDelete</strong></p></td>
<td><p>Specifies whether users can delete records in the data source (in the table).</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>AllowEdit</strong></p></td>
<td><p>Specifies whether users can make modifications to fields on the form.</p>
<div class="mtps-table">
<div class="mtps-row">
<img src="images/Aa589339.alert_note(en-us,AX.60).gif" title="Tip" alt="Tip" class="note" /><strong>Tip</strong>
</div>
<div class="mtps-row">
You can set the AllowEdit property for the entire form here, but to prohibit modifications for individual fields, the same property exists on each field in the data source.
</div>
</div></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>AutoNotify</strong></p></td>
<td><p>Determines whether the system receives a notification if a record is changed. The default value is Yes.</p>
<div class="mtps-table">
<div class="mtps-row">
<img src="images/Hh404129.alert_caution(en-us,AX.60).gif" title="Caution note" alt="Caution note" class="note" /><strong>Caution</strong>
</div>
<div class="mtps-row">
The <strong>AutoNotify</strong> property is no longer used. The property will be removed in a future version of Microsoft Dynamics AX.
</div>
</div>
<p>This property forms part of the <a href="autojoin-system.md">AutoJoin System</a>.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>AutoQuery</strong></p></td>
<td><p>Determines whether a query is automatically generated for the data source that joins it with the data source that is specified in the JoinSource property. The default value is Yes.</p>
<p>This property forms part of the <a href="autojoin-system.md">AutoJoin System</a>.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>AutoSearch</strong></p></td>
<td><p>Determines whether the system automatically performs a search on the data source. The default value is Yes.</p>
<p>This property forms part of the <a href="autojoin-system.md">AutoJoin System</a>.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>CounterField</strong></p></td>
<td><p>Enables you to specify one of the fields in the data source as a counter for the form. The field must be an index on the table that underlies the data source, and must be of type real.</p>
<p>The CounterField property is used to ensure that a record inserted in a form is supplied with a line number that corresponds to the actual sequential position in the form. For example, if a new line is inserted between lines 3 and 4, the new line is supplied with line number 3.5.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>CrossCompanyAutoQuery</strong></p></td>
<td><p>Specifies whether the data source retrieves data from more than one company database.</p>
<div class="mtps-table">
<div class="mtps-row">
<img src="images/Aa589339.alert_note(en-us,AX.60).gif" title="Tip" alt="Tip" class="note" /><strong>Tip</strong>
</div>
<div class="mtps-row">
To display company information, add the <strong>DataAreaId</strong> field from the data source to the form.
</div>
</div>
<p>For more information about cross-company queries, see <a href="cross-company-data-access.md">Cross-Company Data Access</a>.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>DelayActive</strong></p></td>
<td><p>Enables you to delay the execution of the data source’s active method.</p>
<p>If this property is set to Yes, the active method is activated only after a delay of 20 milliseconds. When a user scrolls through a data source, the active method is not called on every record—on only the final record that the user selects.</p>
<div class="mtps-table">
<div class="mtps-row">
<img src="images/Aa589339.alert_note(en-us,AX.60).gif" title="Tip" alt="Tip" class="note" /><strong>Tip</strong>
</div>
<div class="mtps-row">
This property is particularly useful when two data sources are linked (when the LinkType property is set to Delayed).
</div>
</div>
<p>This property forms part of the <a href="autojoin-system.md">AutoJoin System</a>.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>Index</strong></p></td>
<td><p>Sets the index used to specify a sorting order. You can choose any of the indexes on the table.</p>
<p>If you specify an index in this way, it is used as an index hint on each of the queries to the database. It specifies both an access path and a sort order for the records shown in the form, based on this data source.</p>
<p>The initial sort order for the records shown in a form is prioritized as follows:</p>
<ul>
<li><p>If sort fields are added to the data source query, the sort specification is used.</p></li>
<li><p>If an index is specified in the Index property on the data source, the sort order used is implicitly specified in that index.</p></li>
<li><p>If the data source is autojoined with another data source, the system locates the most adequate index for this join, and then sorts the data according to that index.</p></li>
<li><p>If nothing else is specified, the sort order is the one that is implicitly specified in the first index (the one with the lowest ID) on the table that is used in the form data source.</p></li>
</ul>
<p>When no index hints are specified, the database management system locates an applicable access path. It is based on the information in the supplied query.</p>
<p>The sort order for a form can be changed by a user by using the query dialog.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>InsertAtEnd</strong></p></td>
<td><p>Determines whether a new record is created when the user moves focus past the last record in the table (for example, by pressing F8).</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>InsertIfEmpty</strong></p></td>
<td><p>Determines whether a blank record is displayed in the form if there are no records in the table.</p>
<p>If InsertIfEmpty is set to No, the user must manually create a new record (for example, by pressing CTRL+N).</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>JoinSource</strong></p></td>
<td><p>Enables you to join two data sources.</p>
<p>Set this property when two or more tables are used as the data source, and you want to join them.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>LinkType</strong></p></td>
<td><p>Enables you to maintain an active link between two data sources. When focus changes in the first data source, the corresponding record(s) in the other data source are selected.</p>
<p>An example of using this property is a customer table and a table of transactions for each customer. Scrolling from one customer to the next also automatically updates the transaction list to display transactions for the current customer.</p>
<p>Set this property to Delayed for the outer (externally linked) data source. The linked data source is updated only after a delay of 100 milliseconds. This ensures that the linked data source does not update while a user is scrolling through a data source—only after the user finally focuses on a record.</p>
<p>This property forms part of the <a href="autojoin-system.md">AutoJoin System</a>.</p>
<p>For more information about link types, see <a href="how-to-join-data-sources-for-a-form.md">How to: Join Data Sources for a Form</a>.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>Name</strong></p></td>
<td><p>Sets the name of the data source. This should be the same as the name of the underlying table.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>OnlyFetchActive</strong></p></td>
<td><p>Determines whether all fields in the data source should be fetched, or only those that are used by controls on the form.</p>
<p>This property is designed to be used in lookup forms. There is no code in these forms, and they open more quickly because the result set is smaller.</p>
<p>When the OnlyFetchActive property has been set to Yes, records cannot be deleted from within the form. This is to preserve data integrity by ensuring that a delete operation is never attempted on incomplete records. If the user attempts to delete a record, an error message is issued.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>OptionalRecordMode</strong></p></td>
<td><p>Specifies the create and delete behavior for records that have an outer joined table.</p>
<p>May be set to one of the following options:</p>
<ul>
<li><p><strong>ImplicitCreate</strong> – When no record is saved in the database, create an outer joined record and joined tables as soon as the parent record becomes active. If the outer joined record or its children are not changed, they will be deleted when the parent record is no longer active.</p></li>
<li><p><strong>ExplicitCreate</strong> – When no record is saved in the database, treat this record as disabled until the user explicitly triggers creation with the <strong>Optional Record</strong> checkbox. When the record exists, unchecking the checkbox deletes the record.</p></li>
<li><p><strong>None</strong> – No special create or delete happens with an outer joined record.</p></li>
</ul></td>
<td><p>AX 2012</p></td>
</tr>
<tr class="odd">
<td><p><strong>StartPosition</strong></p></td>
<td><p>Defines whether the first or the last record should be the current one when the form opens.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p><strong>Table</strong></p></td>
<td><p>Sets the table used as the data source.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p><strong>ValidTimeStateAutoQuery</strong></p></td>
<td><p>Specifies the type of query for date effective data (<strong>AsOfDate</strong> or <strong>DateRange</strong>).</p></td>
<td><p>AX 2012</p></td>
</tr>
<tr class="even">
<td><p><strong>ValidTimeStateUpdate</strong></p></td>
<td><p>Specifies the types of updates for an existing date effective record. The options are as follows:</p>
<ul>
<li><p><strong>CreateNewTimePeriod</strong> – CreateNewTimePeriod – On the record that is becoming the previous record, its <strong>ValidTo</strong> date field is set to a date that is no later than now. In the same transaction, the new current record has its <strong>ValidFrom</strong> field set to immediately after <strong>ValidTo</strong> date of the previous record.</p></li>
<li><p><strong>Correction</strong> – The ValidFrom or ValidTo values of existing rows must be modified to keep the date effective data valid after it updates the record set</p></li>
<li><p><strong>EffectiveBased</strong> – Records in the past cannot be edited. Records that are currently active are edited in a manner similar to <strong>CreateNewTimePeriod</strong> mode. Future records are edited in a manner similar to <strong>Correction</strong> mode.</p></li>
</ul>
<p>The default value is <strong>CreateNewTimePeriod</strong>.</p></td>
<td><p>AX 2012</p></td>
</tr>
</tbody>
</table>


## See also

[Form Data Source Field Properties](form-data-source-field-properties.md)

[Form Control Properties](form-control-properties.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

