---
title: C# Proxy Source Code for X++ Tables
TOCTitle: C# Proxy Source Code for X++ Tables
ms:assetid: 483c8390-aae0-4bdf-a052-6c991e903216
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg845209(v=AX.60)
ms:contentKeyID: 35243096
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# C\# Proxy Source Code for X++ Tables 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

This topic describes details about the C\# source code that is produced by the proxy generator in Microsoft Dynamics AX. For information about how to run the proxy generator within Microsoft Visual Studio, see [Integration with X++ Objects from Visual Studio](integration-with-x-objects-from-visual-studio.md).


> [!NOTE]
> <P>The proxy generator can produce source code in C# or Visual Basic.</P>



## Source Code Details

The following table provides information about the C\# source code that is output by the proxy generator.

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
<td><p>///&lt;summary&gt; documentation.</p></td>
<td><p>The proxy generator uses the <strong>DeveloperDocumentation</strong> property value of the table to add ///&lt;summary&gt; documentation into the source code of the C# proxy.</p></td>
</tr>
<tr class="even">
<td><p>Fields are public properties.</p></td>
<td><p>Most table fields become public properties that you use to get or set the value. System fields are read-only properties that have values that you can get but cannot set.</p></td>
</tr>
<tr class="odd">
<td><p><strong>SYS</strong> versus <strong>USR</strong> layers.</p></td>
<td><p>Proxy classes are built to match the changes to the target AOT element in all layers, regardless of which layer you are logged into with Microsoft Visual Studio.</p></td>
</tr>
</tbody>
</table>


## See also

[C\# Proxy Source Code for X++ Classes](csharp-proxy-source-code-for-x-classes.md)

[Proxy Classes for .NET Interop to X++](proxy-classes-for-net-interop-to-x.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

