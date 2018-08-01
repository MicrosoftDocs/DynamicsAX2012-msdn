---
title: 'X++, C# Comparison: Operators'
TOCTitle: 'X++, C# Comparison: Operators'
ms:assetid: bda4bc5d-93cc-48b6-bbd6-5d0e8029ebf3
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc967420(v=AX.60)
ms:contentKeyID: 35250038
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# X++, C\# Comparison: Operators [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

This topic compares the operators between Microsoft Dynamics AX X++ and C\#.

## Assignment Operators

The following table displays the differences between the assignment operators in X++ and C\#.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>X++ and C#</p></th>
<th><p>Differences</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>=</p></td>
<td><p>In X++ this operator causes an implicit conversion whenever a loss of precision might occur, such for an assignment from an int64 to an int. But in C# the assignment causes a compile error.</p></td>
</tr>
<tr class="even">
<td><p>+=</p>
<p>and</p>
<p>-=</p></td>
<td><p>The only difference is that in C# these operators are also used in delegate manipulation.</p></td>
</tr>
<tr class="odd">
<td><p>++</p>
<p>and</p>
<p>--</p></td>
<td><p>These are the increment and decrement operators in both languages. The following line is identical in both languages:</p>
<ul>
<li><p>++myInteger;</p></li>
</ul>
<p>But in X++ these two operators are for statements, not for expressions. Therefore the following lines generate compile errors in X++:</p>
<ul>
<li><p>myStr = int2str(++myInteger);</p></li>
<li><p>myIntA = myIntBB++;</p></li>
</ul></td>
</tr>
</tbody>
</table>


## Arithmetic Operators

The following table lists the arithmetic operators.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>X++ and C#</p></th>
<th><p>Differences</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>*</p></td>
<td><p>As the multiplication operator, there are no differences.</p>

> [!note]  
> <P>The asterisk is also used in the SQL statements that are part of the X++ language. In these SQL statements the asterisk can also be one of the following:
> <ul>
> <li><p>A wildcard indicating that all the columns should be returned.</p></li>
> <li><p>A wildcard for characters in a string that is used on a like clause.</p></li>
> </ul>
> For more information, see <a href="relational-operators.md">Relational Operators</a>.</P>

</td>
</tr>
<tr class="even">
<td><p>/</p></td>
<td><p>The division operator is the same in X++ and C#.</p></td>
</tr>
<tr class="odd">
<td><p>MOD</p></td>
<td><p>For modulo operations, the only difference is that the % symbol is used in C#.</p></td>
</tr>
<tr class="even">
<td><p>+</p></td>
<td><p>The addition operator is the same in X++ and C#. The plus sign is also used for string concatenation.</p>
<p>This operator adds numbers and concatenates strings in both languages.</p></td>
</tr>
<tr class="odd">
<td><p>-</p></td>
<td><p>The subtraction operator is the same in X++ and C#.</p></td>
</tr>
</tbody>
</table>


## Bitwise Operators

The following table compares the bitwise operators between X++ and C\#.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>X++ and C#</p></th>
<th><p>Differences</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>&lt;&lt;</p></td>
<td><p>The left shift operator is the same in X++ and C#.</p></td>
</tr>
<tr class="even">
<td><p>&gt;&gt;</p></td>
<td><p>The right shift operator is the same in X++ and C#.</p></td>
</tr>
<tr class="odd">
<td><p>~</p></td>
<td><p>The bitwise NOT operator is the same in X++ and C#.</p></td>
</tr>
<tr class="even">
<td><p>&amp;</p></td>
<td><p>The binary AND operator is the same in X++ and C#.</p></td>
</tr>
<tr class="odd">
<td><p>^</p></td>
<td><p>The binary XOR operator is the same in X++ and C#.</p></td>
</tr>
<tr class="even">
<td><p>|</p></td>
<td><p>The binary OR operator is the same in X++ and C#.</p></td>
</tr>
</tbody>
</table>


## Relational Operators

The following relational operators are the same in X++ and C\#:

  - \==

  - \>=

  - \<=

  - \>

  - \<

  - \!=

  - &&

  - ||

  - \!

  - ? :

## See also

[X++, C\# Comparisons](x-csharp-comparisons.md)

[Operators](operators.md)

[Expression Operators: Is and As for Inheritance](expression-operators-is-and-as-for-inheritance.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

