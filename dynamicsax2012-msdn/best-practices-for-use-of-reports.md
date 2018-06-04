---
title: Best Practices for Use of Reports
TOCTitle: Use of Reports
ms:assetid: fe753881-b2da-44f5-ab92-400c8d902f41
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa893471(v=AX.60)
ms:contentKeyID: 35254214
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Best Practices for Use of Reports 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_


> [!NOTE]
> <P>SQL Server&nbsp;Reporting Services is now the primary reporting platform for Microsoft Dynamics AX. The X++ reporting framework is being deprecated in Microsoft Dynamics AX 2012. Use the Visual Studio tools for Microsoft Dynamics AX to define reports. For more information, see <A href="https://msdn.microsoft.com/en-us/library/cc653472(v=ax.60)">Development Tasks for Reporting</A>.</P>



## RunBaseReport

Reports should use the [RunbaseReportStd Class](https://msdn.microsoft.com/en-us/library/gg838161\(v=ax.60\)) framework to make it possible to run the report in batch and to give it a consistent user interface. An example can be seen in the tutorial\_RunbaseReportStd report.

The menu item that is used to start the report is used to control on which tier (client, server, called from) the report should run.

## Menu Item

A Menu Item for a report should be an Output Menu Item. Name the Output Menu Item after the report, or name it logically.

Consider where the report should run (Client, Server, Called), and set the property on the menu item (or the class) starting the report.

Apply the same label for the Output Menu Item, the caption of the report, and its dialog.

## See also

[Best Practices for Report Properties](best-practices-for-report-properties.md)

[Reports Best Practices](reports-best-practices.md)

[Best Practices for Report Design](best-practices-for-report-design.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

