---
title: 'X++ Standards: Dates'
TOCTitle: 'X++ Standards: Dates'
ms:assetid: 4bbf76cc-4307-40e5-ad72-0edd0d50977f
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa605545(v=AX.60)
ms:contentKeyID: 35243327
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# X++ Standards: Dates 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

When you are programming with dates, Best Practices are:

  - Use only strongly typed (date) fields, variables, and controls (do not use str or int).

  - Use Auto settings in date formatting properties.

  - Use DateTimeUtil::getSystemDateTime instead of systemDateGet or today. The today function uses the date of the machine. The systemDateGet method uses the system date in Microsoft Dynamics AX. Only DateTimeUtil::getSystemDateTime compensates for the time zone of the user.

  - Avoid using date2str for performing date conversions.

## Use Strong Typing (date)

Never permanently store a date in anything other than a date field.

Always present a date in a date control.

Fields, variables, and controls should be defined by extended data types. These should have their formatting properties set to **Auto** so that you do not take control away from the users' specific date formatting setup.

## Current Business Date

Most application logic should use the system function systemDateGet ![Warning icon](images/Aa658028.WarningIcon(en-us,AX.60).gif "Warning icon"), which holds the logic business date of the system (this can be set from the status bar).

The system function today() should be used only where the actual machine date is needed. This is seldom the case.


> [!NOTE]
> <P>The date and time can be different on the client and the server.</P>



## Avoid String / Date Conversions

You will not typically need to format a date to a string. Use date fields, variables, and date controls on forms and reports instead.

If you need to format a date to a string:

  - For user interface situations, use strFmt or date2Str with -1 in all the formatting parameters. This ensures that the date is formatted in the way that the user has specified in **Regional Settings**.

  - For other specific system-related situations, such as communication with external systems, use date2Str.

When you let **Regional Settings** dictate the format, be aware that it can change from user to user and might not be a suitable format for external communication.

Using str2Date indicates that dates are being used that have had a string format.

## See also

[date2Str Function](https://msdn.microsoft.com/en-us/library/aa857241\(v=ax.60\))

[str2Date Function](https://msdn.microsoft.com/en-us/library/aa554244\(v=ax.60\))

[DateTimeUtil::getSystemDateTime Method](https://msdn.microsoft.com/en-us/library/gg837438\(v=ax.60\))

[systemDateGet Function](https://msdn.microsoft.com/en-us/library/aa672952\(v=ax.60\))

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

