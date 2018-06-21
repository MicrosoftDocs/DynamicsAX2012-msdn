---
title: 'X++ Standards: try/catch Statements'
TOCTitle: 'X++ Standards: try/catch Statements'
ms:assetid: a34bb97c-3044-47ae-8d55-68c26a0cf873
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa849924(v=AX.60)
ms:contentKeyID: 35248375
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# X++ Standards: try/catch Statements [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Always create a try/catch deadlock/retry loop around database transactions that might lead to deadlocks.

Whenever you have a retry, all the transient variables must be set back to the value they had just before the try. The persistent variables (that is, the database and the **Infolog**) are set back automatically by the throw that leads to the catch/retry.

## Example

    try
    {
        this.createJournal();
        this.printPosted();
    }
    catch (Exception::Deadlock)
    {
        this.removeJournalFromList();
        retry;
    }

## See also

[Exception Handling with try and catch Keywords](exception-handling-with-try-and-catch-keywords.md)

[X++ Coding Standards](x-coding-standards.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

