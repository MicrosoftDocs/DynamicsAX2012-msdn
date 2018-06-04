---
title: C# Proxy Source Code for X++ Classes
TOCTitle: C# Proxy Source Code for X++ Classes
ms:assetid: 890f26f7-8bdc-4e3a-95e0-19ed4e9f864d
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg846417(v=AX.60)
ms:contentKeyID: 35246302
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# C\# Proxy Source Code for X++ Classes 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

This topic describes details about the C\# source code that is written for X++ classes by the proxy generator. In Microsoft Dynamics AX, there are a few different techniques to invoke the proxy generator, but each technique produces the same output.


> [!NOTE]
> <P></P>
> <P>This topic uses the C# language. The information applies to any language that is supported by the Microsoft .NET common language runtime, including Microsoft Visual Basic.</P>



## Source Code Details

The following table describes details about the C\# source code that is written by the proxy generator.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Detail</p></th>
<th><p>Comment</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Proxies are automatically included for compile time dependencies.</p></td>
<td><p>When you generate a proxy for the X++ class QueryRun, a proxy is also generated for the X++ class ObjectRun. QueryRun depends on ObjectRun because QueryRun inherits from ObjectRun.</p>
<p>An X++ method creates a dependency on another X++ class if either of the following is true:</p>
<ul>
<li><p>The method inputs the other X++ class as a parameter, or</p></li>
<li><p>The other class is the return type of the method.</p></li>
</ul>
<p>No dependency is detected if the method only declares and uses a variable of other class type.</p></td>
</tr>
<tr class="even">
<td><p>Inheritance by the proxy class.</p></td>
<td><p>Every proxy class extends Microsoft.Dynamics.AX.ManagedInterop.Object.</p></td>
</tr>
<tr class="odd">
<td><p>Separate output file for each proxy.</p></td>
<td><p>Every proxy from the proxy generator is written to its own separate source code file.</p></td>
</tr>
<tr class="even">
<td><p>///&lt;summary&gt; XML documentation is included.</p></td>
<td><p>If the X++ source code contains ///&lt;summary&gt; XML documentation, the proxy generator copies the documentation to the output proxy.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SYS</strong> versus <strong>USR</strong> layers.</p></td>
<td><p>Proxy classes are built to match the changes to the target AOT element in all layers, regardless of which layer you are logged into with Microsoft Visual Studio.</p></td>
</tr>
<tr class="even">
<td><p>protected methods are omitted from the proxies.</p></td>
<td><p>You have only limited ability to create new classes in C# that inherit from a proxy class. X++ methods with the protected access modifier are excluded by the proxy generator.</p>
<div class="mtps-table">
<div class="mtps-row">
<img src="images/Aa589339.alert_note(en-us,AX.60).gif" title="Tip" alt="Tip" class="note" /><strong>Tip</strong>
</div>
<div class="mtps-row">
If you want to extend a proxy class, consider instead extending the X++ class before you generate the proxy.
</div>
</div></td>
</tr>
<tr class="odd">
<td><p>The abstract modifier in X++ is discarded from the C# proxy.</p></td>
<td><p>The proxy generator ignores the abstract modifiers it encounters in X++ classes. No proxy classes or members are ever abstract.</p></td>
</tr>
<tr class="even">
<td><p>Every X++ method is marked either virtual, override, or new in the C# proxy.</p></td>
<td><p>Suppose in X++ you have a class DerivedClass that extends X++ class BaseClass. In their C# proxies, the methods would be decorated as follows:</p>
<ul>
<li><p>int BaseClass.method22() – virtual</p></li>
<li><p>int method333() – virtual</p></li>
</ul>
<p></p>
<ul>
<li><p>int DerivedClass.method22() – override</p></li>
<li><p>int64 method333() – new</p></li>
<li><p>void Derived.method4444(bool b) – virtual</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>The new method in X++ is represented as a constructor in C#.</p></td>
<td><p>If the X++ class has no method that is named new, the proxy generator writes a default constructor in C#.</p></td>
</tr>
<tr class="even">
<td><p>X++ names are modified if they conflict with a C# keyword.</p></td>
<td><p>For example, an X++ class that is named stackalloc would conflict with the C# keyword keyword stackalloc. Therefore, in the proxy file the C# class name would be _stackalloc. However, this same proxy if generated in Visual Basic would have the unaltered class name of stackalloc.</p></td>
</tr>
</tbody>
</table>


## See also

[Proxy Classes for .NET Interop to X++](proxy-classes-for-net-interop-to-x.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

