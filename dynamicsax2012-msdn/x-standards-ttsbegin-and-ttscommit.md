---
title: 'X++ Standards: ttsBegin and ttsCommit'
TOCTitle: 'X++ Standards: ttsBegin and ttsCommit'
ms:assetid: 6a0a0197-70bc-44fa-8187-de86b91138e5
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa609617(v=AX.60)
ms:contentKeyID: 35244785
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# X++ Standards: ttsBegin and ttsCommit 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

ttsBegin and ttsCommit must always be used in a clear and well-balanced manner. Balanced ttsBegin and ttsCommit statements are the following:

  - Always in the same method.

  - Always on the same level in the code.

Avoid making only one of them conditional.

Use throw, if a transaction cannot be completed.

Do not use ttsAbort; use [throw](x-standards-throw-statements.md) instead.

Do not use anything that requires a user interaction within a transaction (such as an action on a dialog box).

## See also

[Transaction Integrity](transaction-integrity.md)

[Exception Handling with try and catch Keywords](exception-handling-with-try-and-catch-keywords.md)

[X++ Coding Standards](x-coding-standards.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

