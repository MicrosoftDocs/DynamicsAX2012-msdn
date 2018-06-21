---
title: Do...while Loops
TOCTitle: Do...while Loops
ms:assetid: 9313718f-bfed-469e-ad2f-0e82121c9bfb
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa842320(v=AX.60)
ms:contentKeyID: 35247523
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Do...while Loops [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The do...while loop is similar to the [while loop](while-loops.md), but differs in that the condition follows the statement. The statement is always performed at least once. The do...while loop is well suited for tasks that always must be done at least once, for example, to get parameters for a report.

## Syntax

do

{ statement }

while

( expression ) ;

statement can be a block of statements.

## Example

Following is an example of a do...while loop designed to find the smallest power of 10 that is larger than \_Value.

    int FindPower(real _Value)
    {
        int ex=-1;
        real curVal;
        ;
       
        do
       {
          ex += 1;
          curVal = power(10, ex);
       }
       
       while (_Value>curVal);
     
       return ex;
    } 

## See also

[Loops](loops.md)

[Conditional Statements](conditional-statements.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

