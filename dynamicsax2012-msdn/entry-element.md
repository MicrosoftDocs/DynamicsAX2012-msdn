---
title: Entry Element
TOCTitle: Entry Element
ms:assetid: 63aeaf8a-8c06-445f-ad4e-936814afbdf8
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg882351(v=AX.60)
ms:contentKeyID: 35257179
ms.date: 11/07/2012
mtps_version: v=AX.60
dev_langs:
- xml
---

# Entry Element 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The Entry element is an XML element that specifies a table of contents entry.

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
<td><p>text</p></td>
<td><p>string</p></td>
<td><p>Yes</p></td>
<td><p>The text for the title that displays in the table of contents.</p></td>
</tr>
<tr class="even">
<td><p>Microsoft.Help.F1</p></td>
<td><p>Microsoft.Help.F1</p></td>
<td><p>Yes</p></td>
<td><p>Specifies the ID of the Help topic.</p></td>
</tr>
<tr class="odd">
<td><p>children</p></td>
<td><p>entry</p></td>
<td><p>No</p></td>
<td><p>A collection of entry elements that are nested under the current topic in the table of contents.</p></td>
</tr>
</tbody>
</table>


## Remarks

Use this element to add information to the table of contents for a document set. You use this element as a child of **entries** for the **tableOfContents** element. When you click an entry in the table of contents, the help server returns all content elements that have the same **Microsoft.Help.F1** ID as the table of contents entry.

You also use this element to add **children** to an existing **entry** element. Each **entry** you add to **children** appears in the table of contents as a nested subentry. This enables you to group related entries in the table of contents.

## Example

The following XML example shows how to use the **entry** element to add a record to the table of contents. Notice the use of **children** that adds two related subentries.

``` xml
<entry>
   <text>Search functionality</text>
   <Microsoft.Help.F1>4af8f624-e7f2-40d6-9c87-0b79e2ed2d7b</Microsoft.Help.F1>
   <children>
      <entry>
         <text>Overview of search</text>
         <Microsoft.Help.F1>36a473e2-d967-4ce6-87ed-83cf3ba77527</Microsoft.Help.F1>
      </entry>
      <entry>
         <text>Using search</text>
         <Microsoft.Help.F1>78ad7d04-9381-42a4-8e1d-c2b1a9d756fa</Microsoft.Help.F1>
      </entry>
   </children>
</entry>
```

## See also

[TableOfContents Element](tableofcontents-element.md)

