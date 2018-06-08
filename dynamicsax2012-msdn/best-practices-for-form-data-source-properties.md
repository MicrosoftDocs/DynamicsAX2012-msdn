---
title: Best Practices for Form Data Source Properties
TOCTitle: Form Data Source Properties
ms:assetid: 01a58727-b809-4efe-9007-bae0bbce9fa2
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa498562(v=AX.60)
ms:contentKeyID: 35240100
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Best Practices for Form Data Source Properties 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Form data sources should be set up to use [AutoJoin system](autojoin-system.md) of Microsoft Dynamics AX. The first record in the data source should be shown when the user opens the form.

Best practices for some of the properties are shown in the following table. For a description of all form data source properties, see [Form Data Source Properties](form-data-source-properties.md). For information about lookup forms, see [Best Practices for Lookup Forms](best-practices-for-lookup-forms.md). You can also set properties on data source fields.

The following table describes best practice rules for form data source properties.

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
<td><p>Give the data source the same name as the underlying table. If there is more than one data source with the same table, give the data sources individual logical names that describe their purposes.</p></td>
</tr>
<tr class="even">
<td><p>Table</p></td>
<td><p>Should be identical to Name.</p></td>
</tr>
<tr class="odd">
<td><p>Index</p></td>
<td><p>If you specify an index for a form data source, it will be used as an index hint for queries to the database. It will specify an access path and a sort order for the records shown in the form, based on this data source.</p>
<p>The initial sort order for the records shown in a form is prioritized by the system:</p>
<ul>
<li><p>If sort fields are added to the data source query, the sort specification is used.</p></li>
<li><p>If an index is specified in the index property on the data source, the sort order that is implicitly specified in that index is used.</p></li>
<li><p>If the data source is auto joined to another data source, the system finds the index for this join and sorts the data according to that index.</p></li>
<li><p>If nothing else is specified, the sort order is the one that is implicitly specified in the first index (the one with the lowest ID) on the table that is used in the form data source.</p></li>
</ul>
<p>When no index hints are specified, it is up to the database management system to find an applicable access path that is based on the information in the supplied query.</p>
<p>The sort order can be changed by the user, by using the different sort options that are presented on the controls and in the query dialog box.</p></td>
</tr>
<tr class="even">
<td><p>AllowCheck, AllowEdit, AllowCreate, AllowDelete</p></td>
<td><p>Usually should be set to Yes, but you should decide what is appropriate for your application. Set to No for lookup forms.</p>
<div class="mtps-table">
<div class="mtps-row">
<img src="images/Aa589339.alert_note(en-us,AX.60).gif" title="Note" alt="Note" class="note" /><strong>Note</strong>
</div>
<div class="mtps-row">
AllowCheck on joined data sources (inner, outer, exist, not exist) must be set to Yes (which is the default) to enforce security checking across all data sources.
</div>
</div></td>
</tr>
<tr class="odd">
<td><p>StartPosition</p></td>
<td><p>Unless the form is used for postings, the StartPosition property should be set to First.</p></td>
</tr>
<tr class="even">
<td><p>AutoSearch</p></td>
<td><p>Must be set to Yes.</p></td>
</tr>
<tr class="odd">
<td><p>AutoNotify</p></td>
<td><p>Must be set to Yes.</p></td>
</tr>
<tr class="even">
<td><p>AutoQuery</p></td>
<td><p>Must be set to Yes.</p></td>
</tr>
<tr class="odd">
<td><p>OnlyFetchActive</p></td>
<td><p>This property is designed for use in lookup forms. It can also be used safely in a view-only form that has no code or buttons to start other application objects. Only the fields that are controls on the form will be selected from the database. This means that the form will open more quickly.</p></td>
</tr>
<tr class="even">
<td><p>JoinSource</p></td>
<td><p>Set this property only when two or more tables are used as the data source and you want to join them.</p></td>
</tr>
<tr class="odd">
<td><p>LinkType</p></td>
<td><p>Must be set to Delayed for the outer (externally linked) data source.</p></td>
</tr>
</tbody>
</table>


## See also

[Best Practices for Form Control Properties](best-practices-for-form-control-properties.md)

[Best Practices for Form Design Properties](best-practices-for-form-design-properties.md)

[Forms Best Practices](forms-best-practices.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

