---
title: TableOfContents Element
TOCTitle: TableOfContents Element
ms:assetid: b236e77a-8b80-4c2a-9c14-cbfee51d471c
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg882380(v=AX.60)
ms:contentKeyID: 35257207
ms.date: 11/07/2012
mtps_version: v=AX.60
dev_langs:
- xml
---

# TableOfContents Element [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The TableOfContents element is an XML metadata element that specifies table of contents information for a document set.

## Members

The following table lists the members of this element.

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Element</p></th>
<th><p>Type</p></th>
<th><p>Required</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>publisher</p></td>
<td><p>publisher</p></td>
<td><p>Yes</p></td>
<td><p>An element that specifies the publisher of the table of contents.</p></td>
</tr>
<tr class="even">
<td><p>documentSets</p></td>
<td><p>documentSets</p></td>
<td><p>Yes</p></td>
<td><p>An element that specifies the name of a document set.</p></td>
</tr>
<tr class="odd">
<td><p>ms.locale</p></td>
<td><p>ms.locale</p></td>
<td><p>Yes</p></td>
<td><p>An element that specifies the language for the table of contents.</p></td>
</tr>
<tr class="even">
<td><p>entries</p></td>
<td><p>entry</p></td>
<td><p>Yes</p></td>
<td><p>The element you use to add one or more entry elements. Each entry element adds a record to the table of contents for the specified document set.</p></td>
</tr>
</tbody>
</table>


## Remarks

Use this element and child elements to supply table of contents information for a document set. The **tableOfContents** element is the root element of a document that is stored in an XML file.

To add topics to the table of contents, add child elements to **entries** that specify the ID of a help topic and the text to display in the table of contents.

## Examples

The following XML example shows how to use the **tableOfContents** element to add table of content entries to the document set named **UserDocumentation**. Notice the use of the **publisher**, **documentSets**, and **ms.locale** elements. Also, notice how **xmlns** attributes specify namespace information for the table of contents XML document.

``` xml
<?xml version="1.0" encoding="utf8"?>
<tableOfContents xmlns="http://schemas.microsoft.com/dynamicsHelp/2008/11" xmlns:xsl="http://www.w3.org/2001/XMLSchema-instance">
   <publisher>Microsoft</publisher>
   <documentSets>UserDocumentation</documentSets>
   <ms.locale>EN-US</ms.locale>
   <entries>
   </entries>
</tableOfContents>
```

## See also

[DocumentSets Element](documentsets-element.md)

[Entry Element](entry-element.md)

[Ms.Locale Element](ms-locale-element.md)

[Publisher Element](publisher-element.md)

