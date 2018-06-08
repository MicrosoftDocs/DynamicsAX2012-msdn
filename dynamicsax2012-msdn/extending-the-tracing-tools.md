---
title: Extending the Tracing Tools
TOCTitle: Extending the Tracing Tools
ms:assetid: f4e1917d-7221-44b1-911e-899bf4e4fe0a
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa889036(v=AX.60)
ms:contentKeyID: 35253530
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Extending the Tracing Tools 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The tracing system in Microsoft Dynamics AX is based on the kernel supplying information to application elements, which in turn handle dispatching and storing the information. Business partners can extend or change the behavior of the trace-engine. To investigate how to extend the default trace mechanism, check the method SysTrace on the Application class, which is called once for each trace event.

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

