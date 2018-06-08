---
title: Continue Statements
TOCTitle: Continue Statements
ms:assetid: 4dfe0a78-c733-4aa5-b550-34ff36203b94
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa638117(v=AX.60)
ms:contentKeyID: 35243453
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Continue Statements 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The continue statement causes the system to move straight to the next iteration of a for, while, or do...while loop. For do or while, the test is executed immediately. In a for statement, the increment step is executed.

If you use continue with an if statement, you can avoid deeply nested if...else statements.

## Syntax

continue ;

## Example

    int i;
    int Iarray[100];
    ;
     
    for (i=1; i<100; i++)
    {
        if (Iarray[i] <= 0)
        continue;
     
        // Some statements.
    }

If Iarray\[i\] \<= 0, the remaining statements in the loop are not executed, and i is incremented before the if statement is tried again.

## See also

[Break Statements](break-statements.md)

[Do...while Loops](do-while-loops.md)

[For Loops](for-loops.md)

[if and if ... else Statements](if-and-if-else-statements.md)

[While Loops](while-loops.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

