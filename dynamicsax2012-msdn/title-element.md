---
title: Title Element
TOCTitle: Title Element
ms:assetid: 018aba5b-af04-44f4-a4cc-af8aedf8a24e
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg882291(v=AX.60)
ms:contentKeyID: 35257122
ms.date: 11/07/2012
mtps_version: v=AX.60
dev_langs:
- html
---

# Title Element 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The Title element is an XML metadata element that specifies the title of a content element.

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
<td><p>Yes</p></td>
<td><p>Specifies the title of a help topic.</p></td>
</tr>
</tbody>
</table>


## Remarks

Specify the text that the search results page or summary page uses to add this content element to the list. The terms in the title are also used to refine search results. If the title contains a specified search term, that content element it ranked higher in the list of search results.

## Examples

The following HTML example shows how to use a document **meta** element to specify a title for a content element. You use **meta** elements to specify the metadata properties of a content element. Notice how the name and content properties of the **meta** element specify the Help system element and the title.

``` html
<meta name="Title" content="Set up accounts receivable parameters" />
```

## See also

[Description Element](description-element.md)

[DocumentSets Element](documentsets-element.md)

[Microsoft.Help.F1 Element](microsoft-help-f1-element.md)

[Microsoft.Help.Id Element](microsoft-help-id-element.md)

[Microsoft.Help.Keywords Element](microsoft-help-keywords-element.md)

[Ms.Locale Element](ms-locale-element.md)

[Publisher Element](publisher-element.md)

[SuppressedPublishers Element](suppressedpublishers-element.md)

