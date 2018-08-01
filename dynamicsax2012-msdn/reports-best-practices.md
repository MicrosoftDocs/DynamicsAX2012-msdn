---
title: Reports Best Practices
TOCTitle: Reports
ms:assetid: 24fac17e-3b1a-4f15-a82c-99c69721c06b
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa635013(v=AX.60)
ms:contentKeyID: 35241643
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Reports Best Practices [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_


> [!NOTE]
> <P>SQL Server is now the primary reporting platform for Microsoft Dynamics AX. The X++ reporting framework is being deprecated in Microsoft Dynamics AX 2012. Use the Visual Studio tools for Microsoft Dynamics AX to define reports. For more information, see <A href="https://msdn.microsoft.com/en-us/library/cc653472(v=ax.60)">Development Tasks for Reporting</A>.</P>



X++ reports are one of the central places where IntelliMorph is active. Best practices for X++ reports concern keeping the default settings for properties.

When you design a report, you often do not know much about the environment in which the report will be executed, such as:

  - The size of the paper in the printer.

  - The length or the contents of the labels that are used in the user's installation or language.

  - Which fields are disabled due to security keys and configuration keys.

  - The length of the fields (extended data types) in the user's installation.

  - The sort order of the data sent to the report.

  - Whether the user only wants to print the (sub) totals.

  - What font and size the user has set up as report defaults.

  - How many records there are in the tables from which the report gets its data.


> [!NOTE]
> <P>You must use labels for the report's Caption and Description properties <IMG title="Error icon" alt="Error icon" src="images/Aa872655.ErrorIcon(AX.60).gif">, unless the report is country/region-specific. This enables the report to be translated more easily.</P>



For specific rules about reports, see:

  - [Best Practices for Report Design](best-practices-for-report-design.md)

  - [Best Practices for Report Properties](best-practices-for-report-properties.md)

  - [Best Practices for Use of Reports](best-practices-for-use-of-reports.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

