---
title: 'X++, C# Comparison: String Case and Delimiters'
TOCTitle: 'X++, C# Comparison: String Case and Delimiters'
ms:assetid: c60278c3-b82d-464d-b870-ec66faa5bcc0
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc967424(v=AX.60)
ms:contentKeyID: 35251116
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# X++, C\# Comparison: String Case and Delimiters [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

This topic compares the treatment of strings with mixed casing in X++ and C\#. It also explains the string delimiters that are available in X++.

## X++ to C\# Comparisons

There are similarities and differences in how strings are delimited in X++ and C\#.

### ![Cc967424.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc967424.collapse_all(en-us,AX.60).gif")Similarities

The following X++ features are the same as in C\#:

  - The backslash (\\) is the escape operator for string delimiters.

  - The at sign (@) nullifies the escape effect of the backslash when the at sign is written immediately before the open quotation mark of a string.

  - The plus sign (+) is the string concatenation operator.

### ![Cc967424.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc967424.collapse_all(en-us,AX.60).gif")Differences

X++ features that are different in C\# are listed in the following table.

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Feature</p></th>
<th><p>X++</p></th>
<th><p>C#</p></th>
<th><p>Comments</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>== comparison operator</p></td>
<td><p>Insensitive: the == <a href="relational-operators.md">operator</a> is insensitive to differences in string casing.</p></td>
<td><p>In C#, the == operator is sensitive to differences in string casing.</p></td>
<td><p>In X++ you can use the <a href="https://msdn.microsoft.com/en-us/library/aa672979(v=ax.60)">strCmp Function</a> for case sensitive comparisons between strings.</p></td>
</tr>
<tr class="even">
<td><p>String delimiters</p></td>
<td><p>In X++ you can use either the single (') or double (&quot;) quotation mark as the string delimiter.</p>
<div class="mtps-table">
<div class="mtps-row">
<img src="images/Aa589339.alert_note(en-us,AX.60).gif" title="Note" alt="Note" class="note" /><strong>Note</strong>
</div>
<div class="mtps-row">
Usually the best practice is to use double quotation marks for strings that might be displayed to the user. However, it is convenient to delimit a string with single quotation marks when a double quotation mark is one of the characters in the string.
</div>
</div></td>
<td><p>In C# you must use the double quotation mark as the string delimiter. This refers to the type System.String.</p></td>
<td><p>In X++ and C# you have the option of embedding a delimiter in a literal string and escaping it with \.</p>
<p>In X++ you also have the alternative of embedding single quotation marks in a string that is delimited by double quotation marks (or the reverse), without having to use the escape.</p></td>
</tr>
<tr class="odd">
<td><p>Character delimiters</p></td>
<td><p>X++ has a string data type (str), but no character type.</p></td>
<td><p>In C# you must use the single quotation mark as the character delimiter. This refers to the type System.Char.</p></td>
<td><p>In the .NET Framework, a System.String of length one is a different data type than a System.Char character.</p></td>
</tr>
</tbody>
</table>


## Example 1: Case Sensitivity of the == Operator

The == and \!= operators are case insensitive in X++, but are case sensitive in C\#, as is illustrated by the following example.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>X++</p></th>
<th><p>C#</p></th>
<th><p>Comments</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>&quot;HELLO&quot; == &quot;hello&quot;</p>
<p>True in X++.</p></td>
<td><p>&quot;HELLO&quot; == &quot;hello&quot;</p>
<p>False in C#.</p></td>
<td><p>Different case comparisons between X++ and C#.</p></td>
</tr>
</tbody>
</table>


## Example 2: The + String Concatenation Operator

The + and += operators are used to concatenate strings in both X++ and C\#, as is shown by the examples in the following table.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>X++</p></th>
<th><p>C#</p></th>
<th><p>Comments</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>myString1 = &quot;Hello&quot; + &quot; world&quot;;</p>
<p>Result is equality:</p>
<p>myString1 == &quot;Hello world&quot;</p></td>
<td><p>(Same as for X++.)</p></td>
<td><p>In both X++ and C#, the behavior of the + operator depends on the data type of its operands. The operator concatenates strings, or adds numbers.</p></td>
</tr>
<tr class="even">
<td><p>mystring2 = &quot;Hello&quot;;</p>
<p>myString2 += &quot; world&quot;;</p>
<p>Result is equality:</p>
<p>myString2 == &quot;Hello world&quot;</p></td>
<td><p>(Same as for X++.)</p></td>
<td><p>In both X++ and C#, the following statements are equivalent:</p>
<p>a = a + b;</p>
<p>a += b;</p></td>
</tr>
</tbody>
</table>


## Example 3: Embedding and Escaping String Delimiters

Either single or double quotation marks can be used to delimit strings in X++. The escape character (\\) can be used to embed delimiters in a string. These are illustrated in the following table.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>X++</p></th>
<th><p>C#</p></th>
<th><p>Comments</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>myString1 = &quot;He said \&quot;yes\&quot;.&quot;;</p>
<p>Result:</p>
<p>He said &quot;yes&quot;.</p></td>
<td><p>(Same as for X++.)</p></td>
<td><p>The escape character enables you to embed string delimiters inside strings.</p></td>
</tr>
<tr class="even">
<td><p>myString2 = 'He said &quot;yes&quot;.';</p>
<p>Result:</p>
<p>He said &quot;yes&quot;.</p></td>
<td><p>C# syntax does not allow for single quotation marks to delimit strings.</p></td>
<td><p>For strings that may be seen by the user, it is considered a best practice to use the escape character instead of the single quotation marks as shown in the example.</p></td>
</tr>
<tr class="odd">
<td><p>myString3 = &quot;He said 'yes'.&quot;;</p>
<p>Result:</p>
<p>He said 'yes'.</p></td>
<td><p>(Same as for X++.)</p></td>
<td><p>In X++, the single quotation marks are not treated as delimiters unless the string starts with a single quotation mark delimiter.</p>
<p>In C# the single quotation mark has no special meaning for strings, and it cannot be used to delimit strings.</p>
<p>In C# the single quotation mark is the required delimiter for literals of type System.Char. X++ has no character data type.</p></td>
</tr>
<tr class="even">
<td><p>str myString4 = 'C';</p>
<p>Here the single quotation is a string delimiter.</p></td>
<td><p>char myChar4 = 'C';</p>
<p>Here the single quotation mark is a System.Char delimiter, not a System.String delimiter.</p></td>
<td><p>X++ has no data type that corresponds to System.Char in the .NET Framework. An X++ string that is limited to a length of one is still a string, not a character data type.</p></td>
</tr>
</tbody>
</table>


## Example 4: Single Escape Character

Examples that illustrate the single escape character in either the input or the output are shown in the following table.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>X++</p></th>
<th><p>C#</p></th>
<th><p>Comments</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>myString1 = &quot;Red\ shoe&quot;;</p>
<p>Result:</p>
<p>Red shoe</p></td>
<td><p>A literal string in C# cannot contain the two character sequence of escape followed by a space, such as &quot;\ &quot;. A compiler error occurs.</p></td>
<td><p>When the X++ compiler encounters the two character sequence of &quot;\ &quot;, it discards the single escape character.</p></td>
</tr>
<tr class="even">
<td><p>myString2 = &quot;Red\\ shoe&quot;;</p>
<p>Result:</p>
<p>Red\ shoe</p></td>
<td><p>(Same as for X++.)</p></td>
<td><p>In a pair of escape characters, the first negates the special meaning of the second.</p></td>
</tr>
</tbody>
</table>


## See also

[X++, C\# Comparisons](x-csharp-comparisons.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

