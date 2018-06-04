---
title: Cross-Company Queries for Views
TOCTitle: Cross-Company Queries for Views
ms:assetid: d999ecd2-8ce1-487d-b11b-c8a43e64acd5
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc621079(v=AX.60)
ms:contentKeyID: 35252070
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Cross-Company Queries for Views 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

In the Application Object Tree (AOT), you can build a view by dragging a query node onto the **Data Sources** node of your view. The query could have the **AllowCrossCompany** property set to **Yes**. However, this will not return cross-company results from the view.

To return cross-company results from a view, you need to use the crossCompany keyword on the select statement that reads from the view. The **AllowCrossCompany** setting on the view's data source query is ignored in X++ select statements that read from a view.

## See also

[Cross-Company X++ Code Basics](cross-company-x-code-basics.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

