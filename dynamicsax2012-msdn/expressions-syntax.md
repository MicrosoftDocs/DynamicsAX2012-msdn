---
title: Expressions Syntax
TOCTitle: Expressions Syntax
ms:assetid: c7eb32c3-80c8-434d-afd6-10c72267a24e
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa867076(v=AX.60)
ms:contentKeyID: 35251172
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Expressions Syntax [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

An expression in X++ is used in either a mathematical or logical way. Expressions are built on the data types of the language; that is, an expression returns a value of some type. This value can be used in calculations, assignments, conditional statements, and so on.

## EBNF Description of Expressions in X++

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Expression</p></td>
<td><p>=</p></td>
<td><p>Simple-expression [RelationalOperator Simple-expression ]</p></td>
</tr>
<tr class="even">
<td><p>RelationalOperator</p></td>
<td><p>=</p></td>
<td><p>= | != | &lt; | &gt; | &lt;= | &gt;= | like</p></td>
</tr>
<tr class="odd">
<td><p>Simple-expression</p></td>
<td><p>=</p></td>
<td><p>Simple-expression [ + | - | | ] Term | Term</p></td>
</tr>
<tr class="even">
<td><p>Term</p></td>
<td><p>=</p></td>
<td><p>Compfactor { Mult-operator CompFactor }</p></td>
</tr>
<tr class="odd">
<td><p>Mult-operator</p></td>
<td><p>=</p></td>
<td><p>* | / | div | mod | &lt;&lt; | &gt;&gt; | &amp; | ^ | |</p></td>
</tr>
<tr class="even">
<td><p>CompFactor</p></td>
<td><p>=</p></td>
<td><p>[ ! ] [ - | ~ ] Factor</p></td>
</tr>
<tr class="odd">
<td><p>Factor</p></td>
<td><p>=</p></td>
<td><p>Literal | Enum | Variable | FunctionCall | ( If-expression ) | Select-expression</p></td>
</tr>
<tr class="even">
<td><p>Enum</p></td>
<td><p>=</p></td>
<td><p>EnumName :: Literal</p></td>
</tr>
<tr class="odd">
<td><p>Variable</p></td>
<td><p>=</p></td>
<td><p>Identifier [ [ Expression ] ] [ . Expression ]</p></td>
</tr>
<tr class="even">
<td><p>FunctionCall</p></td>
<td><p>=</p></td>
<td><p>[ Expression (. | ::) | this . ] FunctionName ( argumentlist )</p></td>
</tr>
<tr class="odd">
<td><p>If-expression</p></td>
<td><p>=</p></td>
<td><p>Expression ? Expression : Expression</p></td>
</tr>
</tbody>
</table>


Semantic restrictions apply on the preceding syntax. You cannot call any method using the :: operator. Similarly, you cannot use the this keyword without an active object; that is, if you are not within a method and so on.

## Examples

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Example of expression</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1</p></td>
<td><p>An integer literal.</p></td>
</tr>
<tr class="even">
<td><p>NoYes::No</p></td>
<td><p>An enum-reference.</p></td>
</tr>
<tr class="odd">
<td><p>A</p></td>
<td><p>A variable-reference.</p></td>
</tr>
<tr class="even">
<td><p>Debtor::Find(&quot;1&quot;)</p></td>
<td><p>A static method-call (returns a customer variable).</p></td>
</tr>
<tr class="odd">
<td><p>(A &gt; 3 ? true : false)</p></td>
<td><p>An if-expression that returns true or false.</p></td>
</tr>
<tr class="even">
<td><p>(select CustTable where CustTable.Account == &quot;100&quot;).NameRef</p></td>
<td><p>A select-expression. Returns the nameref field in the customer table. This is a string.</p></td>
</tr>
<tr class="odd">
<td><p>A &gt;= B</p></td>
<td><p>A logical expression. Returns true or false.</p></td>
</tr>
<tr class="even">
<td><p>A + B</p></td>
<td><p>An arithmetic expression. Sums A and B.</p></td>
</tr>
<tr class="odd">
<td><p>A + B / C</p></td>
<td><p>Calculates B/C, and then adds this to A.</p></td>
</tr>
<tr class="even">
<td><p>~A + this.Value()</p></td>
<td><p>Sums binary not A and the result of the method-call Value on the object in scope (this).</p></td>
</tr>
<tr class="odd">
<td><p>Debtor::Find(&quot;1&quot;).NameRef</p></td>
<td><p>Returns the NameRef field of the found customer record.</p></td>
</tr>
<tr class="even">
<td><p>Debtor::Find(&quot;1&quot;).Balance()</p></td>
<td><p>A method call to Balance in the customer table (Debtor::Find returns a customer). Returns the balance of the customer with account number 1.</p></td>
</tr>
</tbody>
</table>


## See also

[X++ Syntax](x-syntax.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

