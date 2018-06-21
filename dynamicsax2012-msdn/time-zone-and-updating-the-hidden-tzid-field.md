---
title: Time Zone and Updating the Hidden *TZId Field
TOCTitle: Time Zone and Updating the Hidden *TZId Field
ms:assetid: e38586f8-4ebf-4eab-afc0-867b42765fdf
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc622312(v=AX.60)
ms:contentKeyID: 35253149
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Time Zone and Updating the Hidden \*TZId Field [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The administrator occasionally needs to run a service pack or a minor upgrade issued by Microsoft to make government mandated adjustments to stored Coordinated Universal Time (UTC) values in the **DateTime** fields of tables. There is no need to upgrade any runnable code when updating only the UTC data values.

## Coordinated Pair of Fields

When you use the Application Object Tree (AOT) to add a **DateTime** field named MyDateTime to a table, the following two fields are added to the database table:

  - **MyDateTime**

  - MyDateTimeTZId

The **MyDateTime** field is visible in the AOT. **MyDateTime** is also available as a member on the MyTable myTab; a buffer variable that inherits from the [xRecord Class](https://msdn.microsoft.com/en-us/library/gg950368\(v=ax.60\)).

The MyDateTimeTZId field is not visible in the AOT, nor is it available on the table buffer variable. Also, any reference to this field name in an X++ SQL command causes a compile error.

### ![Cc622312.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc622312.collapse_all(en-us,AX.60).gif")\*TZId Field Information

The \*TZId field holds information about the time zone that the stored UTC value was derived from. The \*TZId field also holds the Daylight Savings Time (DST) rules established for the time zone, at the time the value was stored. The DST rules cover an entire year, not just the day that the value was stored.

## Governments Can Redefine Time Zone and DST Rules

Governments can redefine the time zones. For example, a government could combine two adjacent time zones, so that both territories would have the same clock time. Or a government could modify a time zone so that it's offset from UTC would be 6.5 hours instead of 6.0 hours.

Governments can also redefine the DST rules for a certain time zone. For example, DST could be in effect for 30 weeks instead of 26 weeks.

### ![Cc622312.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc622312.collapse_all(en-us,AX.60).gif")Rule Redefinitions Can Invalidate Stored UTC Values

The database can store in UTC the date/time of a meeting planned to occur months or years in the future. After the meeting's planned start date/time is stored, government changes to DST or other time zone rules can alter the interpretation of the meeting's stored start time.

In the following example, notice in the local time column that the new meeting start date/time is one hour later than in the original meeting start date/time. In the database, the UTC for the new meeting start must be updated from 18:00 to 17:00, because this shifts the local time from 14:00 back to 13:00.

Upgrades provided by Microsoft automatically make these corrections when they update time zone and DST rules.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Description</p></th>
<th><p>UTC</p></th>
<th><p>Local time</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Original DST start</p></td>
<td><p>2038/04/25 07:00</p></td>
<td><p>2038/04/25 02:00</p></td>
</tr>
<tr class="even">
<td><p>Original meeting start</p></td>
<td><p>2038/04/19 18:00</p></td>
<td><p>2038/04/19 13:00</p></td>
</tr>
<tr class="odd">
<td><p>New DST start</p></td>
<td><p>2038/03/16 07:00</p></td>
<td><p>2038/03/16 02:00</p></td>
</tr>
<tr class="even">
<td><p>New meeting start (if left uncorrected)</p></td>
<td><p>2038/04/19 18:00</p></td>
<td><p>2038/04/19 14:00</p></td>
</tr>
</tbody>
</table>


## Minor Upgrades

Microsoft can issue time zone upgrades that the administrator can run to update all of the application **DateTime** and \*TZId fields in the database. Each upgrade must involve a redefinition for at least one time zone.

At a minimum, each upgrade updates a system table where time zones and their DST rules are stored. For application data, the upgrade searches the database for all \*TZId fields that contain the particular time zone that has been redefined. If the system has no data for that time zone, then the upgrade finishes without changing any application data.

\*TZId fields that store the redefined time zone are updated by the upgrade. The UTC value in the associated **DateTime** field gets updated only if appropriate. Date/time values in the past are never updated. A date/time value in the future likely remains unchanged if it is in DST for both the old and the new rules.

## utcdatetime Includes \*TZId Information

The X++ intrinsic type utcdatetime holds a date/time value. It also holds hidden time zone information, which is inaccessible to your X++ code. This is shown in the following X++ code example.

In this example, the Timezone values applied as offsets are different for the two rows that are inserted. This difference causes the two rows to have different \*TZId values. The utcdatetime variables transfer time zone information into the database for the \*TZId columns.

    static void JobApplyTimeZone(Args _args)
    {
        MeetingTable meetingXRec2;
        utcdatetime utc4, utc5;
        ;
        utc4 = DateTimeUtil ::utcNow();
        //--------------
        utc5 = DateTimeUtil ::applyTimeZoneOffset
            ( utc4,
            Timezone ::GMTPLUS0545KATHMANDU
            );
        meetingXRec2 .MeetingDateTime = utc5;
        meetingXRec2 .insert();
        //--------------
        utc5 = DateTimeUtil ::applyTimeZoneOffset
            ( utc4,
            Timezone ::GMTMINUS0330NEWFOUNDLAND
            );
        meetingXRec2 = null;
        meetingXRec2 .MeetingDateTime = utc5;
        meetingXRec2 .insert();
    }

## See also

[Time Zone Overview and Terminology](time-zone-overview-and-terminology.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

