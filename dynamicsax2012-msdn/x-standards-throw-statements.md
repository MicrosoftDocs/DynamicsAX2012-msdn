---
title: 'X++ Standards: throw Statements'
TOCTitle: 'X++ Standards: throw Statements'
ms:assetid: eeabafcf-6378-4da3-a350-019f7eb82695
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa885149(v=AX.60)
ms:contentKeyID: 35253268
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# X++ Standards: throw Statements 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The throw statement automatically initiates a ttsAbort, which is a database transaction rollback.

The throw statement should be used only if a piece of code cannot do what it is expected to do. The throw statement should not be used for more ordinary program flow control.

Always place an explanation of the throw in the **Infolog** before the actual throw.


> [!NOTE]
> <P>Do not use ttsAbort directly; use throw instead.</P>



## See also

[Exception Handling with try and catch Keywords](exception-handling-with-try-and-catch-keywords.md)

[X++ Coding Standards](x-coding-standards.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

