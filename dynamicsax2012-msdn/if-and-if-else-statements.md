---
title: if and if ... else Statements
TOCTitle: if and if ... else Statements
ms:assetid: 00a812d1-9800-4032-9195-4e83e75ca2d6
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa497992(v=AX.60)
ms:contentKeyID: 35240036
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# if and if ... else Statements 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The if statement evaluates a question (a condition) and executes a statement or set of statements if the condition is true. You can provide an alternative statement or set of statements that are executed if the condition is false (the else statement).

if and if...else statements are the most simple conditional statements in X++. You can also use [switch statements](switch-statements.md) and [ternary operators](ternary-operator.md).

You can nest if statements, but if the nesting of if statements becomes too deep, consider using a switch statement.

## Syntax

if ( expression ) statement \[ else statement \]

Both statements can be compound statements. The expression in the parentheses (the condition) can be any valid expression that is evaluated to true or false. (All numbers different from zero are true; all non-empty strings are also true).

## Examples

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Without else</p></th>
<th><p>With else</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>if (a&gt;4)</p>
<p>{</p>
<p>print a;</p>
<p>}</p></td>
<td><p>if (a&gt;4)</p>
<p>{</p>
<p>print a;</p>
<p>}</p>
<p>else</p>
<p>{</p>
<p>print &quot;a is less than or equal to 4&quot;;</p>
<p>}</p></td>
</tr>
</tbody>
</table>


## See also

[Comparison of if and switch Statements](comparison-of-if-and-switch-statements.md)

[Switch Statements](switch-statements.md)

[Ternary Operator (?)](ternary-operator.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

