---
title: Developing Applications Using the AOS
TOCTitle: Developing Applications Using the AOS
ms:assetid: 120146ed-f61f-4cef-8137-0a25d89b8a6d
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa597388(v=AX.60)
ms:contentKeyID: 35240564
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Developing Applications Using the AOS 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

When you develop a Microsoft Dynamics AX application, you should consider running methods on the Application Object Server (AOS) if they do one of the following:

  - Have more than one select.

  - Select more than a few records.

  - Call methods on the server.

Since every database operation goes through the AOS, if your code does more than one operation on the database, it should run on the AOS. If your code has more than one call to the AOS, it should run on the AOS.

This section describes how to run your application objects on the AOS to increase application and server performance.

## In This Section

[Application Object RunOn Property Overview](application-object-runon-property-overview.md)

[Time Zone Overview and Terminology](time-zone-overview-and-terminology.md)

[How to: Run a Class on the AOS](how-to-run-a-class-on-the-aos.md)

[How to: Optimize an Application for the AOS](how-to-optimize-an-application-for-the-aos.md)

[How to: View Client to Server Calls](how-to-view-client-to-server-calls.md)

[Walkthrough: Extending RunBaseBatch Class to Create and Run a Batch](walkthrough-extending-runbasebatch-class-to-create-and-run-a-batch.md)

[Number Sequence Framework](number-sequence-framework.md)

[Search](search.md)

## See also

[Application Object Server (AOS)](application-object-server-aos.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

