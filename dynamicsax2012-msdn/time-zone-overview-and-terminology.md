---
title: Time Zone Overview and Terminology
TOCTitle: Time Zone Overview and Terminology
ms:assetid: 013a340b-831f-4217-8137-30e7411849c9
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc518263(v=AX.60)
ms:contentKeyID: 35240061
ms.date: 06/11/2016
mtps_version: v=AX.60
---

# Time Zone Overview and Terminology [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

One Microsoft Dynamics AX Application Object Server (AOS) installation can meet the business needs of a company that has operations across multiple time zones. All date/time values are stored in Coordinated Universal Time (UTC).

When a date/time value is retrieved and displayed on a form, the date/time is shown in the user's preferred time zone. If the date/time value is edited and stored again, the value is converted from local time to UTC for storage.

## Terminology

The following table defines terms that are used to discuss time zones.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Term</p></th>
<th><p>Definition</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Application <strong>DateTime</strong> fields</p></td>
<td><p><strong>DateTime</strong> fields in the database that are not automatically created by the AOS. Microsoft Dynamics AX ships with several application <strong>DateTime</strong> fields. Custom <strong>DateTime</strong> fields can also be added.</p>
<p>Examples could be ActivityStartDateTime or MeetingEndDateTime.</p></td>
</tr>
<tr class="even">
<td><p>Date/time</p></td>
<td><p>A generic name for a single value that contains both date and time.</p>
<p>The types that hold date/time data are:</p>
<ul>
<li><p>X++ – utcdatetime</p></li>
<li><p>Database table field – <strong>DateTime</strong></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>DST</p></td>
<td><p>Daylight Savings Time. A rule that governs sudden jumps in the local time within any given time zone. The jumps are usually one hour. The jumps revert back, usually at the end of the winter season.</p>
<p>Governments set DST rules within a time zone. Changes to DST can shift the meaning of date/time values already stored.</p>
<p>Microsoft Dynamics AX provides a mechanism to adjust date/time values to correct for changes to DST rules.</p></td>
</tr>
<tr class="even">
<td><p>GMT</p></td>
<td><p>Greenwich Mean Time. The local time at the longitudinal meridian that passes through Greenwich, England.</p>
<p>GMT is used as the common reference among all time zones.</p></td>
</tr>
<tr class="odd">
<td><p>Local time</p></td>
<td><p>Time for one particular time zone.</p></td>
</tr>
<tr class="even">
<td><p>System <strong>DateTime</strong> fields</p></td>
<td><p><strong>DateTime</strong> fields in the database that are automatically created, populated, and maintained by the AOS. The user cannot modify these fields.</p>
<p>Actual instances include CreatedDateTime and ModifiedDateTime.</p></td>
</tr>
<tr class="odd">
<td><p>Time zone</p></td>
<td><p>Any area of the Earth in which local time differs from its immediate neighbor. Consecutive time zones usually differ by one hour, or by DST rules.</p>
<p>Each time zone can have its own DST rules.</p></td>
</tr>
<tr class="even">
<td><p>Update of time zone rules</p></td>
<td><p>Microsoft occasionally releases patches that update time zone rule data, after governments change the time zone rules. Updating the rules does not involve any upgrade of executable code.</p></td>
</tr>
<tr class="odd">
<td><p>Upgrade of <strong>Date</strong> and <strong>Time</strong> fields to <strong>DateTime</strong></p></td>
<td><p>The upgrade from any product version prior to Microsoft Dynamics AX 2009 involves upgrading the product's executable code, database tables, and more. This is a one-time task.</p>
<p>This task replaces <strong>Date</strong> and <strong>Time</strong> field pairs with one <strong>DateTime</strong> field. It also updates time zone rule data.</p></td>
</tr>
<tr class="even">
<td><p>UTC</p></td>
<td><p>Coordinated Universal Time. UTC is GMT that is updated with leap seconds (to account for the slowing of the earth's rotation).</p>
<p>UTC is intended as the replacement for the older concept of GMT.</p></td>
</tr>
</tbody>
</table>


## Categories of Time Zone Feature Information

The time zone features in Microsoft Dynamics AX can be categorized as shown in the following table.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Feature</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="time-zone-related-types.md">Time Zone Related Types</a></p></td>
<td><ul>
<li><p>The utcdatetime intrinsic type in X++.</p></li>
<li><p>The <strong>DateTime</strong> field type on tables.</p></li>
<li><p>The date/time controls on forms and reports.</p></li>
<li><p>The Timezone enumeration.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><a href="convert-from-time-zone-before-persisting-in-x.md">Convert from Time Zone Before Persisting in X++</a></p></td>
<td><ul>
<li><p>X++ programmer's obligation to convert local date/time values to UTC before storing them by calling insert_recordset.</p></li>
<li><p>The use of several DateTimeUtil methods in X++.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><a href="time-zone-and-datetime-display-controls.md">Time Zone and DateTime Display Controls</a></p></td>
<td><ul>
<li><p><strong>DateTimeEdit</strong> on <strong>Form.</strong></p></li>
<li><p><strong>DateTime</strong> on <strong>Report.</strong></p></li>
<li><p><strong>WebDateTime</strong> on <strong>Web Form.</strong></p></li>
<li><p><strong>DateTime</strong> on <strong>Web Report.</strong></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><a href="time-zone-and-updating-the-hidden-tzid-field.md">Time Zone and Updating the Hidden *TZId Field</a></p></td>
<td><ul>
<li><p>How the system automatically coordinates a *TZId field for each <strong>DateTime</strong> field on a table.</p></li>
<li><p>How UTC values can become invalid when governments redefine time zones and DST rules.</p></li>
<li><p>The actions of updates that Microsoft can issue to adjust for time zone and DST redefinitions.</p></li>
<li><p>Details about time zone information hidden inside the utcdatetime intrinsic type.</p></li>
</ul></td>
</tr>
</tbody>
</table>


## Time Zones and Dates

Some fields in Dynamics AX contain information about dates, some fields contain information about time, and some fields contain information about both. The fields that contain both use UTC. UTC supports multiple time zone capabilities running server-based code. The fields that only contain date information or only contain time information do not have time zone capabilities. An example of a field that does not have time zone capabilities is the Invoice Date. Invoice Date extends a date type, carries no time information, is not based on UTC, and has no time zone capabilities. If you are using a field that does not have time zone capabilities and you need it to work across multiple time zones and you require transaction-level posting with the local date and time, then you must set up an AOS in each time zone.  If you do not setup a separate AOS for each time zone, then the posting date will be reflected by the time zone which the AOS is associated not the local time zone.  For example, if your AOS is based in Greenwich Mean Time (London) and a subsidiary of your company is based in the Central Time Zone (Chicago), the time difference is usually 6 hours behind.  Any transaction that is posted after 6:00 PM in Chicago will be recorded as a transactional date for the following day, thus you will have an incorrect posting date based on local time zone.

## In This Section

  - [Time Zone Related Types](time-zone-related-types.md)  

  - [Convert from Time Zone Before Persisting in X++](convert-from-time-zone-before-persisting-in-x.md)  

  - [Time Zone and DateTime Display Controls](time-zone-and-datetime-display-controls.md)  

  - [Time Zone and Updating the Hidden \*TZId Field](time-zone-and-updating-the-hidden-tzid-field.md)  

## See also

[datetime2Str Function](https://msdn.microsoft.com/en-us/library/cc637978\(v=ax.60\))

[utcdatetime](utcdatetime.md)

[Developing Applications Using the AOS](developing-applications-using-the-aos.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

