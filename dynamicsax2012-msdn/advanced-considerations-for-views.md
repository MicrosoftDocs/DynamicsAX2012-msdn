---
title: Advanced Considerations for Views
TOCTitle: Advanced Considerations for Views
ms:assetid: 8199a884-da59-4089-8332-2877323ce075
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg862505(v=AX.60)
ms:contentKeyID: 35246141
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Advanced Considerations for Views 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

This topic describes advanced considerations about view objects in Microsoft Dynamics AX.

## Global Table Join to Company-specific Table Treats Both as Global

A company-specific table has its **SavePerCompany** property set to **Yes**. And it has a DataAreaId column which stores the company code. A global table has no DataAreaId column.

The first data source on a view can be a global table. The global table can be joined with a company-specific table as the second data source. In this case, the company-specific table is also treated as a global table. This treatment as global means that the view will have no DataAreaId column that is automatically added to the view by the system.


> [!NOTE]
> <P>In versions prior to Microsoft Dynamics AX 2012, it was not possible to have this configuration of a global table joined by a company-specific table.</P>



## No Automatic Support of Table Inheritance for a Data Source

Views that have a derived table as their only data source do not have access to the fields that the derived table inherits from its base table. The base table can be joined as another data source to gain access to the fields of the base table.

## See also

[Walkthrough: Add a Computed Column to a View](walkthrough-add-a-computed-column-to-a-view.md)

[View Overview](view-overview.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

