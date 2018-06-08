---
title: Attributes on X++ Types and Methods
TOCTitle: Attributes on X++ Types and Methods
ms:assetid: 8e30d699-4744-4720-8c00-03b33a4226f9
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg846588(v=AX.60)
ms:contentKeyID: 35246486
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Attributes on X++ Types and Methods 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Any class that inherits from the SysAttribute class is called an attribute. An attribute can be attached to items such as classes and methods. The purpose of an attribute is to represent or store metadata about classes and methods.

The system provides several attributes, including the SysObsoleteAttribute class. One use of the SysObsoleteAttribute class is to tell the X++ compiler that it should fail if a particular method is called in the source code. The X++ compiler rejects the compile, and it displays the specific message that is stored in this use of the attribute.

## In This Section

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><a href="overview-of-attribute-classes.md">Overview of Attribute Classes</a></p></td>
</tr>
<tr class="even">
<td><p><a href="syntax-for-attribute-classes.md">Syntax for Attribute Classes</a></p></td>
</tr>
<tr class="odd">
<td><p><a href="how-to-use-reflection-to-get-attribute-class-metadata.md">How to: Use Reflection to Get Attribute Class Metadata</a></p></td>
</tr>
</tbody>
</table>

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

