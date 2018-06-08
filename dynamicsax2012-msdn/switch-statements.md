---
title: Switch Statements
TOCTitle: Switch Statements
ms:assetid: 5bfdc5d6-2a4c-4ba8-8602-74d727ae9c42
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa607181(v=AX.60)
ms:contentKeyID: 35244394
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Switch Statements 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The switch statement is a multi-branch language construct. You can create more than two branches by using the switch statement. This is in contrast to the if statement. You have to nest statements to create the same effect.

The general format of a switch statement is as follows.

switch ( Expression )

{

case  Constant :

 Statement ;

break;

...

default:

 Statement ;

break;

}

The switch expression is evaluated and checked against each of the case compile-time constants. If a constant matches the switch expression, the case statement is executed. If the case also contains a break statement, the program then jumps out of the switch. If there is no break statement, the program continues evaluating the other case statements.

If no matches are found, the default statement is executed. If there are no matches and no default, none of the statements inside the switch are executed.

Each of the previous Statement lines can be replaced with a block of statements by enclosing the block in {...} braces.

## Syntax

Switch statement = switch (  expression ) { {case } \[ default:  statement  \] }

case = case  expression  { ,  expression  } :  statement

## Examples

switch (Debtor.AccountNo)

{

case "1000" :

do\_something;

break;

case "2000" :

do\_something\_else;

break;

default :

default\_statement;

break;

}

It is possible to make the execution drop through case branches by omitting a break statement. For example:

switch (x)

{

case 10:

a = b;

case 11:

c = d;

break;

case 12:

e = f;

break;

}

Here, if x is 10, b is assigned to a, and d is assigned to c, the break statement is omitted after the case 10: statement. If x is 11, d is assigned to c. If x is 12, f is assigned to e.

## See also

[Comparison of if and switch Statements](comparison-of-if-and-switch-statements.md)

[if and if ... else Statements](if-and-if-else-statements.md)

[Ternary Operator (?)](ternary-operator.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

