---
title: Best Practices for Report Design
TOCTitle: Report Design
ms:assetid: c532cf5f-b34b-4a42-8db7-07a147fe03bb
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa865736(v=AX.60)
ms:contentKeyID: 35251109
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Best Practices for Report Design [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_


> [!NOTE]
> <P>SQL Server&nbsp;Reporting Services is now the primary reporting platform for Microsoft Dynamics AX. The X++ reporting framework is being deprecated in Microsoft Dynamics AX 2012. Use the Visual Studio tools for Microsoft Dynamics AX to define reports. For more information, see <A href="https://msdn.microsoft.com/en-us/library/cc653472(v=ax.60)">Development Tasks for Reporting</A>.</P>



An X++ report can have two kinds of design:

  - Auto (AutoDesignSpecs)

  - Generated (Design)

Use Auto design for all 'normal' reports.

Use a Generated design for reports that have special functional requirements that cannot be implemented by using Auto designs or where the design is determined externally. For example:

  - Reports that are forms with externally-determined layouts where the information is expected to be added in very specific positions.

  - Reports that are forms (invoices and so on) where the design should probably be adjusted to the customer's needs at the installation. Most controls should have their positions fixed (not set to Auto) to simplify moving the controls by using the Visual Report Designer.

## See also

[Best Practices for Report Properties](best-practices-for-report-properties.md)

[Reports Best Practices](reports-best-practices.md)

[Best Practices for Use of Reports](best-practices-for-use-of-reports.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

