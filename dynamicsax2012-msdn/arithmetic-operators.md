---
title: Arithmetic Operators
TOCTitle: Arithmetic Operators
ms:assetid: cffbc613-3875-4520-9dea-046dc99aab99
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa870833(v=AX.60)
ms:contentKeyID: 35251770
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Arithmetic Operators 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Use arithmetic operators to perform calculations in X++. Except for ~, which is unary, all arithmetic operators are dyadic; that is, they work on two operands. The syntax of arithmetic expressions is: expression1 ArithmeticOperator expression2.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Operator</p></th>
<th><p>Term</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>&lt;&lt;</p></td>
<td><p>Left shift</p></td>
<td><p>Performs expression2 left shift (a multiplication by 2) on expression1.</p></td>
</tr>
<tr class="even">
<td><p>&gt;&gt;</p></td>
<td><p>Right shift</p></td>
<td><p>Performs expression2 right shift (a division by 2) on expression1.</p></td>
</tr>
<tr class="odd">
<td><p>*</p></td>
<td><p>Multiply</p></td>
<td><p>Multiplies expression1 by expression2.</p></td>
</tr>
<tr class="even">
<td><p>/</p></td>
<td><p>Divide</p></td>
<td><p>Divides expression1 by expression2.</p></td>
</tr>
<tr class="odd">
<td><p>DIV</p></td>
<td><p>Integer division</p></td>
<td><p>Performs an integer division of expression1 by expression2.</p></td>
</tr>
<tr class="even">
<td><p>MOD</p></td>
<td><p>Integer remainder</p></td>
<td><p>Returns the remainder of an integer division of expression1 by expression2.</p></td>
</tr>
<tr class="odd">
<td><p>~</p></td>
<td><p>Not</p></td>
<td><p>Unary operator. Performs a binary not-operation.</p></td>
</tr>
<tr class="even">
<td><p>&amp;</p></td>
<td><p>Binary AND</p></td>
<td><p>Performs a binary and-operation on expression1 and expression2.</p></td>
</tr>
<tr class="odd">
<td><p>^</p></td>
<td><p>Binary XOR</p></td>
<td><p>Performs a binary XOR-operation on expression1 and expression2.</p></td>
</tr>
<tr class="even">
<td><p>|</p></td>
<td><p>Binary OR</p></td>
<td><p>Performs a binary or-operation on expression1 and expression2.</p></td>
</tr>
<tr class="odd">
<td><p>+</p></td>
<td><p>Plus</p></td>
<td><p>Adds expression1 to expression2.</p></td>
</tr>
<tr class="even">
<td><p>-</p></td>
<td><p>Minus</p></td>
<td><p>Subtracts expression2 from expression1.</p></td>
</tr>
<tr class="odd">
<td><p>?</p></td>
<td><p>Ternary operator</p></td>
<td><p>Takes three expressions: expression1 ? expression2 : expression3. If expression1 is true, expression2 is returned; otherwise, expression3 is returned.</p></td>
</tr>
</tbody>
</table>


## Examples

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Operator</p></th>
<th><p>Example</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>&lt;&lt;</p></td>
<td><p>i = 1 &lt;&lt; 4;</p></td>
<td><p>Performs 4 left shifts on 1 (1*2*2*2*2). This gives: i=16.</p></td>
</tr>
<tr class="even">
<td><p>&gt;&gt;</p></td>
<td><p>i = 16 &gt;&gt; 4;</p></td>
<td><p>Performs 4 right shifts on 16 (16/2/2/2/2). This gives i=1.</p></td>
</tr>
<tr class="odd">
<td><p>*</p></td>
<td><p>i = 4*5;</p></td>
<td><p>Multiplies 4 by 5. i=20.</p></td>
</tr>
<tr class="even">
<td><p>/</p></td>
<td><p>i = 20/5;</p></td>
<td><p>Divides 20 by 5. i=4.</p></td>
</tr>
<tr class="odd">
<td><p>div</p></td>
<td><p>i = 100 div 21;</p></td>
<td><p>Returns the integer division of 100 by 21. i=4 (4*21 = 84, remainder 16).</p></td>
</tr>
<tr class="even">
<td><p>mod</p></td>
<td><p>i = 100 mod 21;</p></td>
<td><p>Returns the remainder of the integer division of 100 by 21. i=16.</p></td>
</tr>
<tr class="odd">
<td><p>~</p></td>
<td><p>i = ~1;</p></td>
<td><p>Binary negates 1. This gives i=-2 (all bits are reversed).</p></td>
</tr>
<tr class="even">
<td><p>&amp;</p></td>
<td><p>i = 1 &amp; 3;</p></td>
<td><p>Binary AND. Return the bits in common in the two integers. i=1.</p></td>
</tr>
<tr class="odd">
<td><p>|</p></td>
<td><p>i = 1 | 3;</p></td>
<td><p>Binary OR. Return the bits set in either 1 or 3. i=3.</p></td>
</tr>
<tr class="even">
<td><p>^</p></td>
<td><p>i = 1 ^ 3;</p></td>
<td><p>Binary XOR. Returns the bits set in 1 and NOT in 3 and vice versa. i=2.</p></td>
</tr>
<tr class="odd">
<td><p>+</p></td>
<td><p>i = 1 + 3;</p></td>
<td><p>Adds 1 and 3. i=4.</p></td>
</tr>
<tr class="even">
<td><p>-</p></td>
<td><p>i = 3 - 1;</p></td>
<td><p>Subtracts 1 from 3. i=2.</p></td>
</tr>
<tr class="odd">
<td><p>?</p></td>
<td><p>i = (400&gt;4) ? 1 : 5;</p></td>
<td><p>If (400&gt;4) 1 is returned, else 5 is returned. As 400&gt;4, 1 is returned. i=1.</p></td>
</tr>
</tbody>
</table>


## See also

[Assignment Operators](assignment-operators.md)

[Expressions Syntax](expressions-syntax.md)

[Operator Precedence](operator-precedence.md)

[Relational Operators](relational-operators.md)

[Ternary Operator (?)](ternary-operator.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

