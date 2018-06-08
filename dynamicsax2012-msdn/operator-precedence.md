---
title: Operator Precedence
TOCTitle: Operator Precedence
ms:assetid: 40982da8-ba43-456c-8838-dbae44a57270
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa594120(v=AX.60)
ms:contentKeyID: 35242946
ms.date: 08/19/2015
mtps_version: v=AX.60
---

# Operator Precedence 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The order in which a compound expression is evaluated can be important. For example, (x + y / 100) gives a different result depending on whether the addition or the division is performed first.

You can use parentheses ( ) to explicitly tell the X++ compiler how you want an expression to be evaluated. For example, (x + y)/ 100.

If you do not explicitly tell the compiler the order that you want operations to be performed in, the order is based on the precedence assigned to the operators. For example, the division operator has a higher precedence than the addition operator. For x + y / 100, the compiler would evaluate y/100 first. So, x + y / 100 is equivalent to x + (y / 100).

To make your code easy to read and maintain, be explicit. Indicate with parentheses which operators should be evaluated first.

## Order of Operator Precedence

The operators in the following table are listed in precedence order—the higher in the table an operator appears, the higher its precedence. Operators with higher precedence are evaluated before operators with a lower precedence. Note that the operator precedence of X++ is not the same as other languages, for example C\# and Java.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Operators in precedence order</p></th>
<th><p>Syntax</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>unary operators</p></td>
<td><p>- ~ !</p></td>
</tr>
<tr class="even">
<td><p>multiplicative, shift, bitwise AND, bitwise exclusive OR</p></td>
<td><p>* / % DIV &lt;&lt; &gt;&gt; &amp; ^</p></td>
</tr>
<tr class="odd">
<td><p>additive, bitwise inclusive OR</p></td>
<td><p>+ – |</p></td>
</tr>
<tr class="even">
<td><p>relational, equality</p></td>
<td><p>&lt; &lt;= == != &gt; &gt;= like as is</p></td>
</tr>
<tr class="odd">
<td><p>logical operators (AND, OR)</p></td>
<td><p>&amp;&amp; ||</p></td>
</tr>
<tr class="even">
<td><p>conditional</p></td>
<td><p>? :</p></td>
</tr>
</tbody>
</table>


Operators on the same line have equal precedence. If there is more than one of these operators in an expression, the expression is evaluated from left to right unless assignment operators are used (these are evaluated from right to left).

For example, && (logical AND) and || (logical OR) have the same precedence and are evaluated from left to right. This means that:

0&&0||1 == 1, and 1||0&&0 == 0

## See also

[Assignment Operators](assignment-operators.md)

[Arithmetic Operators](arithmetic-operators.md)

[Relational Operators](relational-operators.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

