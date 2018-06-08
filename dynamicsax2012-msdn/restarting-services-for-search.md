---
title: Restarting Services for Search
TOCTitle: Restarting Services for Search
ms:assetid: 59a2ec70-fd23-412b-92d9-1142a5fa8cfd
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh397316(v=AX.60)
ms:contentKeyID: 36929807
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Restarting Services for Search 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

If you create any new queries that will be used for search, or you make any changes to existing queries that are used for search, you must restart the services that are used for search.


> [!WARNING]
> <P>If you do not restart the services after you make changes to the search queries, the search crawler can encounter errors that prevent data from being accessed through search.</P>



## Restarting the AOS

In the **Services** control panel, restart the service named **Microsoft Dynamics AX Object Server 6.0**. To prevent data loss, make sure that no users are accessing Microsoft Dynamics AX before you restart the service.

## Restarting the SharePoint Search Service

In the **Services** control panel, restart the service named **SharePoint Server Search 14**.

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

