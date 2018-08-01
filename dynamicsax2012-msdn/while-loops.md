---
title: While Loops
TOCTitle: While Loops
ms:assetid: b8c714e6-422f-4fb3-840b-6853434f57f6
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa860014(v=AX.60)
ms:contentKeyID: 35249856
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# While Loops [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

A while loop enables you to repeatedly execute one or more statements, as long as a condition is true. The statement is executed from zero (not at all) to many times, depending on how many times the condition is met. This contrasts with a [do...while](do-while-loops.md) loop. Here, the statement is always executed at least once before the condition is evaluated.

## Syntax

while ( expression ) statement

statement can be replaced by a block of statements.

## Example

   ```X++
   int no = 1;
    ;
    while (no <= conlen(cont))
    {
        print conpeek(cont,no);
        no = no + 1;
    } 
   ```

This traverses a container, cont, and prints out the contents of the container.

## See also

[Loops](loops.md)

[Conditional Statements](conditional-statements.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

