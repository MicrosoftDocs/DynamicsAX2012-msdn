---
title: Convert from Time Zone Before Persisting in X++
TOCTitle: Convert from Time Zone Before Persisting in X++
ms:assetid: 240cafff-3f24-4223-aa55-49a80747e741
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc584924(v=AX.60)
ms:contentKeyID: 35241614
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Convert from Time Zone Before Persisting in X++ 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

In X++ code, SQL statements that read and write **DateTime** fields from tables do not implicitly perform time zone conversions. Explicit calls to methods on the DateTimeUtil class can be added to convert a database **DateTime** column or an X++ utcdatetime value to a particular time zone.


> [!NOTE]
> <P>In contrast, the <STRONG>DateTimeEdit</STRONG> control on a <STRONG>Form</STRONG> automatically converts between the user's preferred time zone that displays and the Coordinated Universal Time (UTC) value it reads or writes to the database table. You can change this default behavior of the control.</P>



## DateTime Values Must be Stored as UTC

Any X++ code that you write needs to store **DateTime** values in UTC. Your code should convert any non-UTC date/time values into UTC before storage.


> [!WARNING]
> <P>If you do not store <STRONG>DateTime</STRONG> values in UTC, they can be converted incorrectly by the <STRONG>DateTimeEdit</STRONG> control on a <STRONG>Form</STRONG> (when the values are read from the database).</P>



### ![Cc584924.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc584924.collapse_all(en-us,AX.60).gif")Reading DateTime Values in UTC

Each time you write an X++ method that reads date/time values from the database, you need to understand whether the date/times should be converted from UTC, and if so into which time zone.

## X++ Example of Inserting DateTime

This section contains:

  - Background information for the X++ example.

  - The X++ code example.

### ![Cc584924.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc584924.collapse_all(en-us,AX.60).gif")Background for the X++ Example

The following X++ code example demonstrates the use of certain date/time related types and methods.

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>DateTimeUtil class</p>
<ul>
<li><p>::newDateTime method</p></li>
<li><p>::getUserPreferredTimeZone method</p></li>
<li><p>::applyTimeZoneOffset method</p></li>
<li><p>::toStr method</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Timezone enum</p>
<ul>
<li><p>::GMTMINUS0500EASTERNTIME element</p></li>
</ul></td>
</tr>
</tbody>
</table>


The X++ example assumes that a table named MeetingTable already exists with the following fields:

  - MeetingId – **Integer**

  - MeetingDate – **Date**

  - MeetingTime – **Time**

  - MeetingDateTime – **DateTime**

In the code example, some rows are inserted into MeetingTable. For each row, the MeetingDateTime UTC value is obtained in a different way:

  - DateTimeUtil ::newDateTime, with a literal date and timeOfDay

  - DateTimeUtil ::newDateTime, with a hard-coded Timezone enum

  - DateTimeUtil ::applyTimeZoneOffset, with a hard-coded Timezone enum

  - DateTimeUtil ::newDateTime, with implicit use of the user's preferred time zone

### ![Cc584924.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc584924.collapse_all(en-us,AX.60).gif")Code Example

    static void DateTimeInsertJob( Args _args )
    {
        MeetingTable meetingXRec; // Inherits from xRecord class.
        date date2;
        timeOfDay time3;
        utcdatetime utcDt5 ,utcDt6;
        str sMeetingDate
            , sMeetingTime
            , sMeetingDateTimeUtc
            , sMeetingDateTimeLocalTz
            , sMeetingId;
        ;
        // Empty the MeetingTable table of all rows.
        delete_from meetingXRec;
        // Prepare a date and a timeOfDay, to use
        //  in building a utcdatetime.
        date2 = 27\11\2006;
        time3 = str2time( "06:44:55" );
        //---------------------------------
        // Combine a literal date and timeOfDay, into a
        //  utcdatetime variable, without conversion from UTC.
        utcDt5 = DateTimeUtil ::newDateTime
            ( date2
            , time3
            // Omitting the optional Timezone parameter,
            //  letting it default to UTC.
            );
        // Insert a row.
        meetingXRec = null;
        meetingXRec .MeetingId = 1;
        meetingXRec .MeetingDate = date2;
        meetingXRec .MeetingTime = time3;
        meetingXRec .MeetingDateTime = utcDt5;
        meetingXRec .insert();
        print( "[11], MeetingId == 1,  UTC,  utcDt5 == "
             + DateTimeUtil ::toStr( utcDt5 ) );
        //---------------------------------
        // Use a hard-coded Timezone enum value to convert
        //  a utcdatetime value for a particular time zone.
        utcDt5 = DateTimeUtil ::newDateTime
            ( date2
            , time3
            // A hard-coded Timezone value.
            , Timezone ::GMTMINUS0500EASTERNTIME
            );
        // Insert a row.
        meetingXRec = null;
        meetingXRec .MeetingId = 2;
        meetingXRec .MeetingDate = date2;
        meetingXRec .MeetingTime = time3;
        meetingXRec .MeetingDateTime = utcDt5;
        meetingXRec .insert();
        print( "[21], MeetingId == 2,  UTC-0500,  utcDt5 == "
             + DateTimeUtil ::toStr( utcDt5 ) );
        //---------------------------------
        // Convert to a hard-coded time zone by using
        //  ::applyTimeZoneOffset, instead of a time zone
        //  parameter in ::newDateTime. Same outcome.
        utcDt5 = DateTimeUtil ::newDateTime
            ( date2
            , time3
            // Omitting the optional Timezone parameter,
            //  letting it default to UTC.
            );
        utcDt5 = DateTimeUtil ::applyTimeZoneOffset
            ( utcDt5
            // A hard-coded Timezone value.
            , Timezone ::GMTMINUS0500EASTERNTIME
            );
        // Insert a row.
        meetingXRec = null;
        meetingXRec .MeetingId = 3;
        meetingXRec .MeetingDate = date2;
        meetingXRec .MeetingTime = time3;
        meetingXRec .MeetingDateTime = utcDt5;
        meetingXRec .insert();
        print( "[31], MeetingId == 3,  UTC-0500,  utcDt5 == "
             + DateTimeUtil ::toStr( utcDt5 ) );
        //---------------------------------
        // Use the user's preferred time zone to convert
        //  a utcdatetime value.
        utcDt5 = DateTimeUtil ::newDateTime
            ( date2
            , time3
            // User's preferred time zone.
            , DateTimeUtil ::getUserPreferredTimeZone()
            );
        // Insert a row.
        meetingXRec = null;
        meetingXRec .MeetingId = 4;
        meetingXRec .MeetingDate = date2;
        meetingXRec .MeetingTime = time3;
        meetingXRec .MeetingDateTime = utcDt5;
        meetingXRec .insert();
        print( "[41], MeetingId == 4,  User TZ,  utcDt5 == "
             + DateTimeUtil ::toStr( utcDt5 ) );
        pause;
        /**********************
        This code produces the following output.
        MeetingId == 4 shows the test run occurred when the user's
        preferred time zone was UTC-0500 (Eastern Time).
    
        [11], MeetingId == 1, UTC,     utcDt5 == 2006-11-27T06:44:55
        [21], MeetingId == 2, UTC-0500, utcDt5 == 2006-11-27T11:44:55
        [31], MeetingId == 3, UTC-0500, utcDt5 == 2006-11-27T11:44:55
        [41], MeetingId == 4, User TZ, utcDt5 == 2006-11-27T11:44:55
        **********************/
    }

## See also

[Time Zone Overview and Terminology](time-zone-overview-and-terminology.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

