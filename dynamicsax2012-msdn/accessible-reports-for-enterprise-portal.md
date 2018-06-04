---
title: Accessible Reports for Enterprise Portal
TOCTitle: Accessible Reports for Enterprise Portal
ms:assetid: e01720d3-58ff-4b0e-a919-b4b1f76cbca1
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh330355(v=AX.60)
ms:contentKeyID: 36806168
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# Accessible Reports for Enterprise Portal 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Only a subset of the SSRS reports that are included with Microsoft Dynamics AX can be accessed from Enterprise Portal. Use the following guidelines to help you determine which reports can be used on Enterprise Portal pages.

  - A menu item is required to access SSRS reports. The **ObjectType** property for the menu item must be **SSRSReport** for the report that you want to use in Enterprise Portal.

  - Reports that are based on a controller class cannot be accessed from Enterprise Portal. The menu item for a report based on a controller class has the **ObjectType** property set to **Class**.

The [SSRS Report Web Part](ssrs-report-web-part.md) lists the reports that can be used in Enterprise Portal. Any reports that cannot be used are excluded from the list.

Even though a report may be listed in the Report web part, it may not have been designed specifically for use in Enterprise Portal. You may have to create a separate design for the report that is more suitable for use in Enterprise Portal. See [Designing Reports for Enterprise Portal](designing-reports-for-enterprise-portal.md) for more information.

