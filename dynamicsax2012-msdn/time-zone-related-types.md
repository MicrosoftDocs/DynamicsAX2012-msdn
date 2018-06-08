---
title: Time Zone Related Types
TOCTitle: Time Zone Related Types
ms:assetid: ad95690d-dda2-48d6-86c8-03b1545b03d7
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc617101(v=AX.60)
ms:contentKeyID: 35249725
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Time Zone Related Types 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

There are several data or object types that are related to date/time or time zone. Also, X++ has several intrinsic functions that are related to date/time or time zone.

## Types

The following tables list data and object types that are related to date/time or time zone.

### ![Cc617101.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc617101.collapse_all(en-us,AX.60).gif")Class – Unrelated to Visual Controls

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Type name in X++</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DateTimeUtil</p></td>
<td><p>A class whose members are mostly static methods. Used for parsing and translating utcdatetime values.</p>
<p>For more information, see <a href="https://msdn.microsoft.com/en-us/library/gg837448(v=ax.60)">DateTimeUtil Class</a>.</p></td>
</tr>
</tbody>
</table>


### ![Cc617101.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc617101.collapse_all(en-us,AX.60).gif")Class – Visual Controls

For more information about where visual controls related to date/time are used, see [Time Zone and DateTime Display Controls](time-zone-and-datetime-display-controls.md).

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Type name in X++</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>FormDateTimeControl</p></td>
<td><p>Displays a date/time value, and enables editing of the value.</p>
<p>Translates UTC date/time values both to and from a preferred time zone.</p></td>
</tr>
<tr class="even">
<td><p>FormWebDateTime</p></td>
<td><p>Displays a date/time value, and enables editing of the value.</p>
<p>Translates UTC date/time values both to and from a preferred time zone.</p></td>
</tr>
<tr class="odd">
<td><p>ReportDateTimeControl</p></td>
<td><p>Displays a date/time value.</p>
<p>Translates a UTC date/time value to a preferred time zone.</p></td>
</tr>
</tbody>
</table>


### ![Cc617101.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc617101.collapse_all(en-us,AX.60).gif")Database Table Columns

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Type name</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>DateTime</strong></p></td>
<td><p>Stored date/time for a specific hour, minute, and second. Corresponds to utcdatetime in X++.</p>
<p>When you create a DateTime field on a table, the system always creates a hidden column with the same name except appended with the four letters TZId. The *TZId column is used to automatically store the time zone and DST information that was used to convert the local date/time to UTC.</p>
<p>System created DateTime fields on tables, like CreatedDateTime and ModifiedDateTime, do not have corresponding *TZId fields.</p></td>
</tr>
<tr class="even">
<td><p><strong>Date</strong></p></td>
<td><p>Stored date, corresponds to date in X++.</p>
<p>There is no *TZId column associated with this type. <strong>Date</strong> values are not associated with a time zone, and <strong>Date</strong> values are not converted to any time zone.</p>
<p>Birth date is a common example where the <strong>Date</strong> type is appropriate. No specific <strong>Time</strong> is associated with a birth date.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Time</strong></p></td>
<td><p>Stored time, corresponds to the timeOfDay extended data type.</p>
<p>There is no *TZId column associated with this type. <strong>Time</strong> values are not associated with a time zone, and <strong>Time</strong> values are not converted to any time zone.</p>
<p>The daily hours that a business is scheduled to be open is a common example of where the <strong>Time</strong> type could be used.</p></td>
</tr>
</tbody>
</table>


### ![Cc617101.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc617101.collapse_all(en-us,AX.60).gif")Enums

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Type name</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Timezone</p></td>
<td><p>Based on int.</p>
<p>An int value of 0 is used for the UTC time zone.</p></td>
</tr>
</tbody>
</table>


### ![Cc617101.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc617101.collapse_all(en-us,AX.60).gif")Extended Data Types

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Type name</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>timeOfDay</p></td>
<td><p>An integer count of the number of seconds since the start of a day.</p></td>
</tr>
</tbody>
</table>


### ![Cc617101.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc617101.collapse_all(en-us,AX.60).gif")X++ Intrinsic Types

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Type name in X++</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>date</p></td>
<td><p>Stores yyyy-mm-dd data, independent of any display format.</p>
<p>It is better to use utcdatetime whenever the time component is also needed.</p></td>
</tr>
<tr class="even">
<td><p>utcdatetime</p></td>
<td><p>Stores yyyy-mm-dd hh:mm:ss data. Storage is independent of any display format.</p></td>
</tr>
</tbody>
</table>


## X++ Functions

There are functions intrinsic to X++. A few of these functions are related to date/time.

### ![Cc617101.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc617101.collapse_all(en-us,AX.60).gif")Functions Directly Related to utcdatetime

The following functions can be used to convert between utcdatetime and string.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Function name</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>datetime2Str</p></td>
<td><p>Converts a utcdatetime into a text string.</p>
<p>For more information, see <a href="https://msdn.microsoft.com/en-us/library/cc637978(v=ax.60)">datetime2Str Function</a>.</p></td>
</tr>
<tr class="even">
<td><p>str2Datetime</p></td>
<td><p>Converts a text string into a utcdatetime.</p>
<p>For more information, see <a href="https://msdn.microsoft.com/en-us/library/cc569557(v=ax.60)">str2Datetime Function</a>.</p></td>
</tr>
</tbody>
</table>


## See also

[Time Zone Overview and Terminology](time-zone-overview-and-terminology.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

