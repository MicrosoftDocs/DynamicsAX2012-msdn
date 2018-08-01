---
title: Description Element
TOCTitle: Description Element
ms:assetid: 7a55058f-604d-4c57-97bc-d254fd112900
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg882357(v=AX.60)
ms:contentKeyID: 35257185
ms.date: 11/07/2012
mtps_version: v=AX.60
dev_langs:
- html
---

# Description Element [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The Description element is an XML metadata element that specifies a brief summary of a content element.

## Members

The following table lists the members of the element.

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Attributes/Properties</p></th>
<th><p>Type</p></th>
<th><p>Required</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>content</p></td>
<td><p>string</p></td>
<td><p>No</p></td>
<td><p>Specifies the brief summary of the content element that appears in the list of search results.</p></td>
</tr>
</tbody>
</table>


## Remarks

Use this element to provide the summary for a content element that appears when that content element is included in a list of search results.

## Example

The following HTML example shows how to use a document **meta** element to specify a description for a content element. You use **meta** elements to specify the metadata properties of a content element. Notice how the name and content properties of the **meta** element specify the Help system element and provide a brief summary of that content element.

``` html
<meta name="description" content="A brief overview of the information in the content element. " />
```

## See also

[Microsoft.Help.F1 Element](microsoft-help-f1-element.md)

[Microsoft.Help.Id Element](microsoft-help-id-element.md)

[Microsoft.Help.Keywords Element](microsoft-help-keywords-element.md)

[Ms.Locale Element](ms-locale-element.md)

[Publisher Element](publisher-element.md)

[SuppressedPublishers Element](suppressedpublishers-element.md)

[TableOfContents Element](tableofcontents-element.md)

[Title Element](title-element.md)

