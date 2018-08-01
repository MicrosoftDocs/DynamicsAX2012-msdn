---
title: 'How to: Optimize an Application for the AOS'
TOCTitle: 'How to: Optimize an Application for the AOS'
ms:assetid: 14877ac8-7512-4b37-9e3e-aa0ead1201eb
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa598289(v=AX.60)
ms:contentKeyID: 35240603
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Optimize an Application for the AOS [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

In Microsoft Dynamics AX, you can optimize your application performance by ensuring that application objects execute on the tier most appropriate for that object. For example, user interface elements should run on the client tier instead of the Application Object Server (AOS). This will reduce calls from the client to the server and increase client performance. This topic lists the steps to optimize your application for performance using the AOS.

## Procedure

### To optimize application object performance on the AOS

1.  Select an area of the application that you want to optimize for the AOS.

2.  Create a project and a node for each area in the Application Object Tree (AOT), such as classes, forms, and tables.

3.  For each area in the project:
    
      - Right-click the object that you want to check, point to **Add-Ins**, and then click **Check Best Practices**.
    
      - Review the results that are shown in the **Compiler output** window on the **Best Practices** tab.
    
      - Implement the applicable best practices recommendations.

4.  Repeat step 3 for tables.

5.  Repeat step 3 for classes.
    
      - Complete the best practices check for the whole class before you start a new class.
    
      - Evaluate the object to determine which tier the class should run on. You should consider the inheritance of the RunOn property. For more information, see [Application Object RunOn Property Overview](application-object-runon-property-overview.md).

6.  Repeat steps 3 - 5. Implementations can create new best practices recommendations.

7.  Repeat step 6 until no new best practices implementations are required.

8.  Evaluate client to server, and server to client calls by using development tracing tools. For more information, see [How to: View Client to Server Calls](how-to-view-client-to-server-calls.md).

9.  Validate the performance of the application objects by running the application in the actual network environment.

## See also

[Application Object RunOn Property Overview](application-object-runon-property-overview.md)

[How to: View Client to Server Calls](how-to-view-client-to-server-calls.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

