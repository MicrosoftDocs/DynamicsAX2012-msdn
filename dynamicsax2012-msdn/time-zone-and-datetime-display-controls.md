---
title: Time Zone and DateTime Display Controls
TOCTitle: Time Zone and DateTime Display Controls
ms:assetid: c7c16b66-5b9a-4f55-964d-9b464813e6af
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc619625(v=AX.60)
ms:contentKeyID: 35251155
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Time Zone and DateTime Display Controls [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Values for **DateTime** fields in tables are stored in Coordinated Universal Time (UTC). Forms and other objects offer visual controls designed for displaying and editing the **DateTime** fields in local time, including adjustments for Daylight Savings Time (DST).

## DateTime Controls and Their Time Zone Properties

The following table lists controls that display or edit **DateTime** values, along with the time zone related properties that can be set for the control.

In the table, each control is identified by its path in the Application Object Tree (AOT), and then by its name in X++ code.

Each property is listed by its member named used in X++ code, followed in parentheses by its label in the client Property window.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Control</p></th>
<th><p>Properties</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><ul>
<li><p>AOT – <strong>Forms</strong> &gt; FormName &gt; <strong>Designs</strong> &gt; <strong>Design</strong> &gt; <strong>New Control</strong> &gt; <strong>UtcDateTimeEdit</strong></p>
<ul>
<li><p>X++ – Form .UtcDateTimeEdit</p></li>
</ul></li>
</ul></td>
<td><ul>
<li><p>displayOption (<strong>DisplayOption</strong>)</p></li>
<li><p>timeZone (Not available the in AOT)</p></li>
<li><p>timeZoneIndicator (<strong>TimeZoneIndicator</strong>)</p></li>
<li><p>timezonePreference (<strong>TimezonePreference</strong>)</p></li>
</ul></td>
</tr>
<tr class="even">
<td><ul>
<li><p>AOT – <strong>Reports</strong> &gt; ReportName &gt; <strong>Designs</strong> &gt; DesignName &gt; <strong>AutoDesignSpecs</strong> &gt; <strong>Body:</strong> Name &gt; <strong>New Control</strong> &gt; <strong>UtcDateTime</strong></p>
<ul>
<li><p>X++ – Report .ReportDateTimeControl</p></li>
</ul></li>
</ul></td>
<td><ul>
<li><p>timezonePreference (<strong>TimezonePreference</strong>)</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><ul>
<li><p>AOT – <strong>Web</strong> &gt; <strong>Web Forms</strong> &gt; WebFormName &gt; <strong>Designs</strong> &gt; <strong>Design</strong> &gt; <strong>New Control</strong> &gt; <strong>WebDateTime</strong></p>
<ul>
<li><p>X++ – WebForm .FormWebDateTime</p></li>
</ul></li>
</ul></td>
<td><ul>
<li><p>displayOption (<strong>DisplayOption</strong>)</p></li>
<li><p>timezonePreference (<strong>TimezonePreference</strong>)</p></li>
</ul></td>
</tr>
<tr class="even">
<td><ul>
<li><p>AOT – <strong>Web</strong> &gt; <strong>Web Reports</strong> &gt; WebReportName &gt; <strong>Designs</strong> &gt; DesignName &gt; <strong>AutoDesignSpecs</strong> &gt; <strong>Body:</strong> Name &gt; <strong>New Control</strong> &gt; <strong>UtcDateTime</strong></p>
<ul>
<li><p>X++ – Report .ReportDateTimeControl</p></li>
</ul></li>
</ul></td>
<td><ul>
<li><p>timezonePreference (<strong>TimezonePreference</strong>)</p></li>
</ul></td>
</tr>
</tbody>
</table>


For information about these properties, see [Form Control Properties](form-control-properties.md).

## See also

[Time Zone Overview and Terminology](time-zone-overview-and-terminology.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

