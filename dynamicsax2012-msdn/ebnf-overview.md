---
title: EBNF Overview
TOCTitle: EBNF Overview
ms:assetid: 12088c37-8a41-4d27-8fc6-7c0757678000
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa597401(v=AX.60)
ms:contentKeyID: 35240570
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# EBNF Overview [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Extended Backus Naur Form (EBNF) is a metalanguage and is used in this guide to describe the language syntax. An EBNF definition consists of production rules, nonterminals, and terminals. The key terms are shown in the following table.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Key terms</p></th>
<th><p>Example</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Terminals</p></td>
<td><p>Work_Team</p></td>
<td><p>A terminal is one character or a string of characters that never change.</p></td>
</tr>
<tr class="even">
<td><p>Nonterminals</p></td>
<td><p>Employee</p></td>
<td><p>A nonterminal is a description of part of a valid sentence in the language that is defined either by a production rule or a textual description. A nonterminal symbol can always be expanded to one or more terminal symbols.</p></td>
</tr>
<tr class="odd">
<td><p>Production rules</p></td>
<td><p>Employee = Developer | Tester</p></td>
<td><p>A production rule is a description of a valid sentence. A production rule defines how a nonterminal symbol on the left side expands into a number of terminal and nonterminal symbols on the right side.</p>
<p>If you continue to expand all nonterminal symbols on the right side of the production rules in a particular grammar, you will eventually have a sequence of terminal symbols.</p></td>
</tr>
</tbody>
</table>


## Example

Work\_Team = Manager Employee {, Employee}   
 Employee = Developer | Tester

This example defines a Work\_Team as consisting of a Manager and one or more Employees. An Employee is defined as being a Developer, or a Tester. The symbols used in the example are described in the following table.

## Special Symbols in EBNF

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Symbol</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>(Expression)</p></td>
<td><p>Parentheses hold the symbols (terminals and nonterminals) together. They can be placed anywhere on the right side of a production rule.</p></td>
</tr>
<tr class="even">
<td><p>Expression1 | Expression2</p></td>
<td><p>Or: Specifies that all the items on one side of the | apply, or else all the items on the other side of the | apply.</p></td>
</tr>
<tr class="odd">
<td><p>[Expression]</p></td>
<td><p>Optional: The items between [ and ] are optional. All or none of the items in the brackets are included.</p></td>
</tr>
<tr class="even">
<td><p>{Expression}</p></td>
<td><p>Repeat: The items between { and } are optional, but can be repeated as many times as necessary.</p></td>
</tr>
</tbody>
</table>


For example, if the accessories you buy for your bicycle consist of a saddle, water-bottle holders, bells, and horns, and you could have either a bell or a horn, and zero, one, or more water bottle holders, and exactly one saddle, this could be expressed as:

Bicycle\_Accessories = saddle \[bell | horn\] {water\_bottle\_holders}

This grammar defines the following possibilities:

saddle   
 saddle bell   
 saddle horn   
 saddle water\_bottle\_holder   
 saddle bell water\_bottle\_holder   
 saddle bell water\_bottle\_holder water\_bottle\_holder

And so on.

## See also

[X++ Syntax](x-syntax.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

