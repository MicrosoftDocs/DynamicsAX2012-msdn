---
title: 'How to: Convert Between utcdatetime and System.DateTime'
TOCTitle: 'How to: Convert Between utcdatetime and System.DateTime'
ms:assetid: 518fc5b0-4047-4795-bc3d-00af36bedad3
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc553823(v=AX.60)
ms:contentKeyID: 35244245
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Convert Between utcdatetime and System.DateTime 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

In Microsoft Dynamics AX, the X++ Global class provides methods for converting between the X++ utcdatetime and the .NET Framework System.DateTime type. The X++ language does not provide the same automatic marshaling between these two date/time types that it does for pairs of other primitive types (such as for int and System.Int32).


> [!NOTE]
> <P>For more information about automatic or implicit marshaling, see <A href="how-to-marshal-between-x-and-clr-primitive-types.md">How to: Marshal Between X++ and CLR Primitive Types</A>.</P>



## X++ Code Sample That Converts Date/Time Types

The following code sample demonstrates the static methods available on the Global class for converting between utcdatetime and System.DateTime in either direction.

In the code sample, the two important X++ methods are:

  - Global::utcDateTime2SystemDateTime

  - Global::CLRSystemDateTime2UtcDateTime

<!-- end list -->

    static void JobDateTimeGlobalMarshal(Args _args)
    {
        System.DateTime netDttm;
        utcdatetime xppDttm;
        str xppString;
        ;
        xppDttm = 2007-06-05T23:22:21; // ISO standard format.
        
        // Convert X++ to .NET.
        netDttm = Global::utcDateTime2SystemDateTime(xppDttm);
        
        // Convert .NET to X++.
        xppDttm = Global::CLRSystemDateTime2UtcDateTime(netDttm);
        
        xppString = DateTimeUtil::toStr(xppDttm);
        info("xppDttm: " + xppString);
    }

## Compatible String Formats

The methods that you can use to pass string representations of date/time values between X++ and .NET are as follows:

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Direction</p></th>
<th><p>X++</p></th>
<th><p>.NET Framework</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Date/time to string</p></td>
<td><p>DateTimeUtil ::toStr</p></td>
<td><p>System.DateTime.GetDateTimeFormats (Input a System.Char of s.)</p></td>
</tr>
<tr class="even">
<td><p>String to date/time</p></td>
<td><p>DateTimeUtil ::parse</p></td>
<td><p>System.DateTime::Parse</p></td>
</tr>
</tbody>
</table>


Neither System.Convert::ToString nor System.DateTime.ToString output a format that can be input by DateTimeUtil::Parse.

### ![Cc553823.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc553823.collapse_all(en-us,AX.60).gif")ISO String Format for Date/Time

The output format of DateTimeUtil::toStr and System.DateTime.GetDateTimeFormats is yyyy-mm-ddThh:mm:ss in 24 hour format (no trailing AM or PM), with leading zeros. For example, July 20 of 2007 at 1:45PM would be output as **2007-07-20T13:45:00**. This string format is an International Standards Organization (ISO) standard.

This ISO string format is input into DateTimeUtil::parse and System.DateTime::Parse. to convert the string to a date/time type.

### ![Cc553823.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc553823.collapse_all(en-us,AX.60).gif")Sample of Converting Between Date/Time and String

The following X++ code sample shows how compatible strings can be passed between .NET and X++ and converted into date/time variables.

    static void JobDtimeTimeStringsNetXpp(Args _args) // X++
    {
        System.DateTime netDttm;
        utcdatetime xppDttm, xppIsoDttm;
        str xppStr;
        ;
        // Use the ISO format to initialize X++ and .NET.
        xppIsoDttm = 2007-05-28T23:59:04; // ISO literal.
        xppDttm = DateTimeUtil::parse("2007-05-28T23:59:04");
        if (xppDttm != xppIsoDttm)
        {
            info("Error 1");
        }
        // Pass date/time strings between X++ and .NET.
        xppStr = DateTimeUtil::toStr(xppDttm);
        netDttm = System.DateTime::Parse(xppStr);
        xppStr = netDttm.ToString("s");
        info(xppStr);
    /********* Actual Infolog output
    Message (03:56:01 pm)
    2007-05-28T23:59:04
    **********/
    }

## See also

[.NET Interop from X++](net-interop-from-x.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

