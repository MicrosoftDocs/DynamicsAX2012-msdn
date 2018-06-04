---
title: Break Statements
TOCTitle: Break Statements
ms:assetid: b480b0bb-67b3-40cc-b9ce-2b8eddf4c14b
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa858014(v=AX.60)
ms:contentKeyID: 35249785
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Break Statements 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

X++ provides a break statement for the following:

  - Terminating loops

  - Separation of case statements in a switch statement

## Syntax

break;

## Loops

When used within a [while](while-loops.md), [do...while](do-while-loops.md), or [for](for-loops.md) loop, the loop is terminated and execution continues from the statement following the loop as shown in the following example.

    mainMenu = SysDictMenu::newMainMenu();
    enum = mainMenu.getEnumerator();
    found = false;
     
    while (enum.moveNext())
    {
        menuItem = enum.current();
        if (menuItem.label() == parentDictsecuritykey.label())
        {
            found = true;
            break;
        }
    }
    if (found) //Belongs in Navigation Pane.
    {
        ...
    }

## Switch

When break is used within a [switch](switch-statements.md) statement, the execution of the case branch terminates, and the statement following the switch is executed as shown in the following example.

switch (Debtor.AccountNo)

{

case "1000": 

do\_something;

break;

case "2000":

do\_something\_else;

break;

default:

default\_statement; 

break;

}

If the Debtor account number is 1000, the program executes do\_something, and then continues execution after the switch statement.

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

