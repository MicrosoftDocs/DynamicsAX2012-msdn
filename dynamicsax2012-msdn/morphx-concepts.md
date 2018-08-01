---
title: MorphX Concepts
TOCTitle: MorphX Concepts
ms:assetid: cdcd8b1e-40da-4ab7-9b6f-4beace7df474
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa869749(v=AX.60)
ms:contentKeyID: 35251682
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# MorphX Concepts [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Some central object-oriented mechanisms and terms appear repeatedly as you develop with MorphX. Below is a brief explanation of the most important ones.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>MorphX concept</p></th>
<th><p>What is it and how does it work?</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>System class</p></td>
<td><p>An interface to the functionality that is defined in MorphX, such as creating or running a form.</p></td>
</tr>
<tr class="even">
<td><p>Class</p></td>
<td><p>Defines an object's interfaces. A class instructs or explains how to construct an object of a particular type.</p>
<p>An essential characteristic of a class is that you can create a new instance (an object) of the class.</p>
<p>Forms are an example of a class. MorphX has a class definition that describes exactly what happens when a form object is created.</p></td>
</tr>
<tr class="odd">
<td><p>Controls</p></td>
<td><p>A graphical object, such as a text box, a check box, a command button, or a rectangle, that you place on a form or report when you are designing it to display data, perform an action, or make the form or report easier to read.</p></td>
</tr>
<tr class="even">
<td><p>Data Source</p></td>
<td><p>Holds the data variables that a form or a query uses. These data variables can be one or more tables, or they can be individual fields from tables.</p></td>
</tr>
<tr class="odd">
<td><p>Designs</p></td>
<td><p>Provides access to define the layout of a form or a report.</p></td>
</tr>
<tr class="even">
<td><p>Encapsulation</p></td>
<td><p>The data in the system is hidden behind methods and can be changed only by the methods.</p></td>
</tr>
<tr class="odd">
<td><p>Final</p></td>
<td><p>A class or method modifier that defines that the class or method cannot be extended (overridden).</p></td>
</tr>
<tr class="even">
<td><p>Inheritance</p></td>
<td><p>A central concept in MorphX. It means that what you define in one element can be inherited by elements that extend that element.</p>
<p>An illustration of the hierarchy of inheritance is that your own methods can extend one of the methods defined in MorphX. In the code this is indicated by the super reference.</p></td>
</tr>
<tr class="odd">
<td><p>Method</p></td>
<td><p>Tasks that you can tell an object to do.</p>
<p>Methods can be programmed at several levels:</p>
<ul>
<li><p>As part of a table</p></li>
<li><p>As part of a form</p></li>
<li><p>As part of a class</p></li>
</ul>
<p>Methods for a form can be related to:</p>
<ul>
<li><p>The general management of the form, such as running the form, or closing it</p></li>
<li><p>The data displayed in the form, such as deleting, or writing data</p></li>
<li><p>Form controls, such as moving the cursor</p></li>
<li><p>As part of queries</p></li>
<li><p>As part of a general class library</p></li>
</ul>
<p>Initially, the methods are only frames that activate the methods of MorphX (indicated by the super() call).</p>
<p>In a method you can:</p>
<ul>
<li><p>Add code to be executed prior to the main action of the method.</p></li>
<li><p>Write you own method or let MorphX handle it (the super() call).</p></li>
<li><p>Add code to be executed after the main action of the method.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Object</p></td>
<td><p>The central MorphX concept. Any form or control is an object. The database is an object.</p>
<p>Objects are created from classes. An object is an instance of a class.</p>
<p>Objects provide a convenient, logical way to organize procedures and data. Objects are encapsulated, which means that they contain both their code and their data.</p>
<p>To use an object, you must keep a reference to it in an object variable.</p></td>
</tr>
<tr class="odd">
<td><p>Property</p></td>
<td><p>Properties are data that describe an object. Each type of object has different types of properties. A method typically has only a few properties, one of which defines where it is to run. Conversely, a control frequently has about 50 properties which define position, size, color, and so on.</p></td>
</tr>
<tr class="even">
<td><p>Query</p></td>
<td><p>A query is a filter mechanism to retrieve the data you want to see from your database tables.</p>
<p>Queries are typically used as the source of records for forms and reports.</p></td>
</tr>
<tr class="odd">
<td><p>Workspace</p></td>
<td><p>The Development Workspace contains the Microsoft Dynamics AX application development tools. The Application Workspace is used to display the client for the end-user.</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

