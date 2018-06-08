---
title: Relational Operators
TOCTitle: Relational Operators
ms:assetid: 702af366-4d46-445e-bd4b-722c9845199f
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa673519(v=AX.60)
ms:contentKeyID: 35244892
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Relational Operators 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The following table lists the relational operators that can be used in X++. All relational operators (except \!) are placed between two expressions: expression1 relationalOperator expression2. For example, while (a \> 10).

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Operator</p></th>
<th><p>Meaning</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>like</p></td>
<td><p>like</p></td>
<td><p>Returns true if expression1 is like expression2.</p>
<p>like can use * as a wildcard for zero or more characters and ? as a wildcard for one character.</p>
<p>Expression2 cannot be longer than 1000 characters.</p>
<p>If the expressions that you are comparing contain a file path, you need to include four backslashes between each element. For example:</p>
<p>select * from xRefpaths</p>
<p>    where xRefPaths.Path like “\\\\Classes\\\\AddressSelectForm”</p>
<div class="mtps-table">
<div class="mtps-row">
<img src="images/Aa589339.alert_note(en-us,AX.60).gif" title="Note" alt="Note" class="note" /><strong>Note</strong>
</div>
<div class="mtps-row">
like is evaluated by the underlying SQL, so the result may differ on different installations.
</div>
</div></td>
</tr>
<tr class="even">
<td><p>==</p></td>
<td><p>equal</p></td>
<td><p>Returns true if both expressions are equal.</p>
<div class="mtps-table">
<div class="mtps-row">
<img src="images/Aa589339.alert_note(en-us,AX.60).gif" title="Note" alt="Note" class="note" /><strong>Note</strong>
</div>
<div class="mtps-row">
When you use == to compare objects, the object references rather than the objects themselves are compared. This may be a problem if you compare two objects that are located on the server and on the client, respectively. In such cases, you should use the equal method in the Object class, which you can override to specify what it means that two objects are equal. If equal is not overridden, the comparison is identical to the one performed by ==.
</div>
</div></td>
</tr>
<tr class="odd">
<td><p>&gt;=</p></td>
<td><p>greater than or equal to</p></td>
<td><p>Returns true if expression1 is greater than or equal to expression2.</p></td>
</tr>
<tr class="even">
<td><p>&lt;=</p></td>
<td><p>less than or equal to</p></td>
<td><p>Returns true if expression1 is less than or equal to expression2.</p></td>
</tr>
<tr class="odd">
<td><p>&gt;</p></td>
<td><p>greater than</p></td>
<td><p>Returns true if expression1 is greater than expression2.</p></td>
</tr>
<tr class="even">
<td><p>&lt;</p></td>
<td><p>less than</p></td>
<td><p>Returns true if expression1 is less than expression2.</p></td>
</tr>
<tr class="odd">
<td><p>!=</p></td>
<td><p>not equal</p></td>
<td><p>Returns true if expression1 is different from (that is, not equal to) expression2.</p></td>
</tr>
<tr class="even">
<td><p>&amp;&amp;</p></td>
<td><p>and</p></td>
<td><p>Returns true if both expression1 and expression2 are true.</p></td>
</tr>
<tr class="odd">
<td><p>||</p></td>
<td><p>or</p></td>
<td><p>Returns true if expression1 or expression2 or both are true.</p></td>
</tr>
<tr class="even">
<td><p>!</p></td>
<td><p>not</p></td>
<td><p>A unary operator. Negates the expression. Returns true if the expression is false; false if the expression is true.</p></td>
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
<th><p>Returns</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>like</p></td>
<td><p>&quot;Jones&quot; like &quot;Jo?es&quot;</p></td>
<td><p>true; the ? is equal to any single character.</p></td>
</tr>
<tr class="even">
<td><p>like</p></td>
<td><p>&quot;Fabrikam, Inc.&quot; like &quot;Fa*&quot;</p></td>
<td><p>true; the * is equal to zero or more characters.</p></td>
</tr>
<tr class="odd">
<td><p>==</p></td>
<td><p>(( 42 * 2) == 84)</p></td>
<td><p>true; 42*2 is equal to 84.</p></td>
</tr>
<tr class="even">
<td><p>&gt;=</p></td>
<td><p>today() &gt;= 1\1\1980</p></td>
<td><p>true; today is later than January 1, 1980.</p></td>
</tr>
<tr class="odd">
<td><p>&gt;=</p></td>
<td><p>((11 div 10) &gt;= 1)</p></td>
<td><p>true; 11 div 10 is 1 (therefore, &gt;= 1 is true).</p></td>
</tr>
<tr class="even">
<td><p>&lt;=</p></td>
<td><p>(11&lt;= 12)</p></td>
<td><p>true; 11 is less than 12.</p></td>
</tr>
<tr class="odd">
<td><p>&gt;</p></td>
<td><p>((11 div 10) &gt; 1)</p></td>
<td><p>false; 11 div 10 is 1.</p></td>
</tr>
<tr class="even">
<td><p>&lt;</p></td>
<td><p>(11 div 10) &lt; 1)</p></td>
<td><p>false; 11 div 10 is 1.</p></td>
</tr>
<tr class="odd">
<td><p>!=</p></td>
<td><p>(11 != 12)</p></td>
<td><p>true; 11 is not equal to 12.</p></td>
</tr>
<tr class="even">
<td><p>&amp;&amp;</p></td>
<td><p>(1 == 1) &amp;&amp; (3 &gt; 1)</p></td>
<td><p>true; both expressions are true.</p></td>
</tr>
</tbody>
</table>


## See also

[Arithmetic Operators](arithmetic-operators.md)

[Assignment Operators](assignment-operators.md)

[Expressions Syntax](expressions-syntax.md)

[Operator Precedence](operator-precedence.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

