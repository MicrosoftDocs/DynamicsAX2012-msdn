---
title: Assignment Operators
TOCTitle: Assignment Operators
ms:assetid: d4e86b9c-be82-4f19-ad86-7722344a05f3
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa873102(v=AX.60)
ms:contentKeyID: 35252009
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Assignment Operators 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

An assignment changes the contents of a variable or field.

The X++ assignment operators are shown in the following table.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Operator</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>=</p></td>
<td><p>Assigns the expression on the right of the equal sign to the variable on the left.</p></td>
</tr>
<tr class="even">
<td><p>+=</p></td>
<td><p>Assigns the variable on the left the current variable value plus the expression on the right.</p></td>
</tr>
<tr class="odd">
<td><p>++</p></td>
<td><p>Increments the variable by one.</p></td>
</tr>
<tr class="even">
<td><p>-=</p></td>
<td><p>Assigns the variable on the left the current variable value minus the expression on the right.</p></td>
</tr>
<tr class="odd">
<td><p>--</p></td>
<td><p>Decrements the variable by one.</p></td>
</tr>
</tbody>
</table>



> [!NOTE]
> <P>There is no difference between prefixed and postfixed operators.</P>



## Examples

The examples in the following table assume that the initial value of i is 1.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Assignment</p></th>
<th><p>Example</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>=</p></td>
<td><p>i = i + 1;</p></td>
<td><p>i is assigned the value of i, plus 1. i = 2.</p></td>
</tr>
<tr class="even">
<td><p>+=</p></td>
<td><p>i += 1;</p></td>
<td><p>i is assigned the value of i, plus 1. i = 2 (i = i + 1).</p></td>
</tr>
<tr class="odd">
<td><p>++</p></td>
<td><p>i++;</p>
<p>++i;</p></td>
<td><p>i is incremented by 1, and then by 1 again in the second statement. The final value of i is 3.</p></td>
</tr>
<tr class="even">
<td><p>-=</p></td>
<td><p>i -= 1;</p></td>
<td><p>i is assigned the value of i minus 1. i = 0 (i = i - 1).</p></td>
</tr>
<tr class="odd">
<td><p>--</p></td>
<td><p>--i;</p>
<p>i--;</p></td>
<td><p>i is decremented by 1, and then by 1 again in the second statement. The final value of i is -1.</p></td>
</tr>
</tbody>
</table>


## See also

[Arithmetic Operators](arithmetic-operators.md)

[Declaration of Variables](declaration-of-variables.md)

[Expressions Syntax](expressions-syntax.md)

[Relational Operators](relational-operators.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

