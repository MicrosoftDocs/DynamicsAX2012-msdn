---
title: Inheritance Terminology
TOCTitle: Inheritance Terminology
ms:assetid: 487a4ba6-67cf-4ad2-8399-702e1e701a7a
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg845237(v=AX.60)
ms:contentKeyID: 35243127
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Inheritance Terminology 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

This topic describes the terminology that is used to discuss the inheritance relationships between sets of classes or set of tables in Microsoft Dynamics AX.

## Inheritance Terminology

In X++, suppose that class AA extends from the Object class, and class BB extends AA, and class CC extends BB. This inheritance hierarchy can be represented by the following notation:

Object \> AA \> BB \> CC

### ![Gg845237.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg845237.collapse_all(en-us,AX.60).gif")Table of Terms

The following table describes the terms that are used to discuss the inheritance example in the previous notation.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Term</p></th>
<th><p>Use</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ascendant</p></td>
<td><p>Class AA is an ascendant of CC.</p></td>
</tr>
<tr class="even">
<td><p>base</p></td>
<td><p>Class AA is the base of BB.</p></td>
</tr>
<tr class="odd">
<td><p>child</p></td>
<td><p>Do not use child when discussing inheritance.</p>
<p>This term is often used when discussing foreign key relationships between tables.</p></td>
</tr>
<tr class="even">
<td><p>descendant</p></td>
<td><p>Class CC is a descendant of AA.</p></td>
</tr>
<tr class="odd">
<td><p>derived</p></td>
<td><p>Class BB is derived from AA.</p></td>
</tr>
<tr class="even">
<td><p>downcast</p></td>
<td><p>The X++ assignment statement myCC = myAA as CC; is a downcast assignment. The as keyword is needed at compile time for downcasting. The downcast might or might not be valid at run time. For more information, see <a href="expression-operators-is-and-as-for-inheritance.md">Expression Operators: Is and As for Inheritance</a>.</p>
<p>The Object class is said to be at the top of the inheritance hierarchy. The CC class is at the bottom of the hierarchy. Casting from class AA to CC goes down the hierarchy.</p>
<p>The following code example illustrates an invalid downcast.</p>
<pre><code>BB myBB = new BB();
CC myCC;
myCC = myBB as CC;</code></pre></td>
</tr>
<tr class="odd">
<td><p>extends</p></td>
<td><p>In X++, the extends keyword is used in the <strong>classDeclaration</strong> node of a class in the Application Object Tree (AOT). The extends keyword means that the present class derives from the class that is named on the extends clause.</p></td>
</tr>
<tr class="even">
<td><p><strong>Extends</strong></p></td>
<td><p>At <strong>AOT</strong> &gt; <strong>Data Dictionary</strong> &gt; <strong>Tables</strong> &gt; MyTable &gt; <strong>Properties</strong>, the <strong>Extends</strong> property is used to derive MyTable from another table.</p></td>
</tr>
<tr class="odd">
<td><p>inherits</p></td>
<td><p>Class BB inherits from the AA class and the Object class.</p></td>
</tr>
<tr class="even">
<td><p>parent</p></td>
<td><p>Do not use parent when discussing inheritance.</p>
<p>This term is often used when discussing foreign key relationships between tables.</p></td>
</tr>
<tr class="odd">
<td><p>subtype</p></td>
<td><p>Class BB and class CC are both subtypes of class AA.</p>
<p></p></td>
</tr>
<tr class="even">
<td><p>supertype</p></td>
<td><p>Class BB and class AA are both supertypes of class CC.</p>
<p></p></td>
</tr>
<tr class="odd">
<td><p>upcast</p></td>
<td><p>The X++ assignment statement myAA = myCC; is an upcast assignment. Upcasting is valid at compile time, and is valid during run time. The as keyword is not needed.</p>
<p>The Object class is said to be at the top of the inheritance hierarchy. The CC class is at the bottom of the hierarchy. Casting from class CC to AA goes up the hierarchy.</p>
<p>The following code example is an upcast.</p>
<pre><code>BB myBB = new BB();
AA myAA;
myAA = myBB;</code></pre></td>
</tr>
</tbody>
</table>


## See also

[Table Inheritance Overview](table-inheritance-overview.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

