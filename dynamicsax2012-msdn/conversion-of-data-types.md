---
title: Conversion of Data Types
TOCTitle: Conversion of Data Types
ms:assetid: 8f708d0e-fafa-4e16-9f22-5932dd66e90d
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa679079(v=AX.60)
ms:contentKeyID: 35247387
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Conversion of Data Types [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The automatic and explicit conversions that can be carried out between different data types are listed in the help topics for several of the [primitive](primitive-data-types.md) and [composite](composite-data-types.md) data types. This topic describes the rules and algorithms that MorphX uses to perform automatic (or implicit) type conversion on primitive data types.

The default values and the internal representation for variables of primitive data types in X++ are shown in the following table.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Data type</p></th>
<th><p>Default</p></th>
<th><p>Internal representation</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Boolean</p></td>
<td><p>false</p></td>
<td><p>Short number</p></td>
</tr>
<tr class="even">
<td><p>Integer</p></td>
<td><p>0</p></td>
<td><p>Long number</p></td>
</tr>
<tr class="odd">
<td><p>Real</p></td>
<td><p>0.0</p></td>
<td><p>BCD (binary-coded digital) number</p></td>
</tr>
<tr class="even">
<td><p>Date</p></td>
<td><p>Null</p></td>
<td><p>Date</p></td>
</tr>
<tr class="odd">
<td><p>String</p></td>
<td><p>empty</p></td>
<td><p>List of characters</p></td>
</tr>
<tr class="even">
<td><p>Enums</p></td>
<td><p>0 (first entry)</p></td>
<td><p>Short number</p></td>
</tr>
</tbody>
</table>


The internal implementation is shown to explain the automatic type conversions that X++ can perform. The principle is simple: every number can automatically be converted to another number in an expression. Usually, the conversion is upward; that is, from short to long to BCD. The conversion follows the operators in the expression. The following table shows the rules.

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
<td><p>+ - *</p></td>
<td><p>If one of the operands is a real, the other will be converted into real and the result is a real.</p>
<p>If both are integers, Booleans, or enums, no conversion will take place, and the result will be integer, Boolean, or enum, respectively.</p>
<p>Otherwise, a Boolean is promoted to enum and enum is promoted to integer</p></td>
</tr>
<tr class="even">
<td><p>/</p></td>
<td><p>Because / is division, the result can be decimal. X++ converts numbers to real before performing the division. The result is real.</p></td>
</tr>
</tbody>
</table>


## Conversion Examples

In the examples shown in the following table, which illustrate these principles, the first letter of the data type is used as a variable identifier (b is a Boolean, d is a date, I is an integer, r is a real, and s is a string).

<table style="width:100%;">
<colgroup>
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
<col style="width: 16%" />
</colgroup>
<thead>
<tr class="header">
<th><p>ID</p></th>
<th><p>Expression</p></th>
<th><p>Left data type</p></th>
<th><p>Operands converted</p></th>
<th><p>With numbers</p></th>
<th><p>Result</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1</p></td>
<td><p>i = b + b</p></td>
<td><p>integer</p></td>
<td><p>Boolean, Boolean</p></td>
<td><p>i = false + false</p></td>
<td><p>0</p></td>
</tr>
<tr class="even">
<td><p>2</p></td>
<td><p>i = r + b</p></td>
<td><p>integer</p></td>
<td><p>real, real</p></td>
<td><p>i = 33.3 + true</p></td>
<td><p>34</p></td>
</tr>
<tr class="odd">
<td><p>3</p></td>
<td><p>b = i + r</p></td>
<td><p>Boolean</p></td>
<td><p>real, real</p></td>
<td><p>b = 10 + 33.3</p></td>
<td><p>undefined</p></td>
</tr>
<tr class="even">
<td><p>4</p></td>
<td><p>b = i + r</p></td>
<td><p>Boolean</p></td>
<td><p>real, real</p></td>
<td><p>b = 0 + 1</p></td>
<td><p>true</p></td>
</tr>
<tr class="odd">
<td><p>5</p></td>
<td><p>r = i + b</p></td>
<td><p>real</p></td>
<td><p>integer, integer</p></td>
<td><p>r = 100 + false</p></td>
<td><p>100.0</p></td>
</tr>
<tr class="even">
<td><p>6</p></td>
<td><p>r = i + b</p></td>
<td><p>real</p></td>
<td><p>integer, integer</p></td>
<td><p>r = 100 + true</p></td>
<td><p>101.0</p></td>
</tr>
<tr class="odd">
<td><p>7</p></td>
<td><p>i = r MOD b</p></td>
<td><p>integer</p></td>
<td><p>integer, integer</p></td>
<td><p>i = 33.3 MOD true</p></td>
<td><p>0</p></td>
</tr>
<tr class="even">
<td><p>8</p></td>
<td><p>r = i DIV i</p></td>
<td><p>real</p></td>
<td><p>no conversion</p></td>
<td><p>r = 100 DIV 5</p></td>
<td><p>20</p></td>
</tr>
<tr class="odd">
<td><p>9</p></td>
<td><p>d = d + i</p></td>
<td><p>date</p></td>
<td><p>date, date</p></td>
<td><p>d = 1\1\1998 + 30</p></td>
<td><p>31\1\1998</p></td>
</tr>
<tr class="even">
<td><p>10</p></td>
<td><p>i = d + i</p></td>
<td><p>integer</p></td>
<td><p>date, date</p></td>
<td><p>i = 1\1\1998 + 1</p></td>
<td><p>compile error</p></td>
</tr>
<tr class="odd">
<td><p>11</p></td>
<td><p>d = d + d</p></td>
<td><p>date</p></td>
<td><p>date, date</p></td>
<td><p>d = 1\1\1998+1\1\1998</p></td>
<td><p>compile error</p></td>
</tr>
<tr class="even">
<td><p>12</p></td>
<td><p>s = s + s</p></td>
<td><p>string</p></td>
<td><p>string, string</p></td>
<td><p>s = &quot;a&quot; + &quot;b&quot;</p></td>
<td><p>&quot;ab&quot;</p></td>
</tr>
<tr class="odd">
<td><p>13</p></td>
<td><p>i = s + i</p></td>
<td><p>integer</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>


### ![Aa679079.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa679079.collapse_all(en-us,AX.60).gif")Notes for the Preceding Examples

The following table discusses details about some of the rows in the preceding table. The ID values match.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>ID</p></th>
<th><p>Discussion</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>2</p></td>
<td><p>The assignment i = r + b, with r = 33.3 and b = true is calculated as follows:</p>

```X++
i = 33.3 + true; // Which is evaluated as...
i = 33.3 + 1.0; // Which is evaluated as...
i = 34.3; // Which is evaluated as...
i = 34; // ...as i is an integer.
```

</td>
</tr>
<tr class="even">
<td><p>3</p></td>
<td><p>The result is undefined because a Boolean has only two legal values: false (0) and true (1). The result of the expression 10 + 33.3 is 43, which is assigned to the Boolean.</p>

> [!note]  
> <P>Because the internal representation is integer, you can use the Boolean in an expression and it will represent the value 43. The Boolean will be considered true.</P>

</td>
</tr>
<tr class="odd">
<td><p>9</p></td>
<td><p>Shows that an integer can be added to a date. The system treats the integer as a quantity of days.</p>

> [!note]  
> <P>The utcdatetime data type does not support arithmetic operations and implicit conversions. Instead, methods on the DateTimeUtil class can be used.</P>

</td>
</tr>
<tr class="even">
<td><p>10</p></td>
<td><p>Results in a compiler error, because a date cannot be automatically converted into an integer.</p></td>
</tr>
<tr class="odd">
<td><p>11</p></td>
<td><p>Shows that you cannot add dates together.</p></td>
</tr>
<tr class="even">
<td><p>12</p></td>
<td><p>Shows that the + operator strings concatenates two strings to create a new string.</p></td>
</tr>
<tr class="odd">
<td><p>13</p></td>
<td><p>Shows that there is no automatic conversion between strings and integers (or other numbers). However, you can make explicit conversions by using built-in conversion functions, such as the str2int function.</p></td>
</tr>
</tbody>
</table>


## See also

[Data Types in X++](data-types-in-x.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

