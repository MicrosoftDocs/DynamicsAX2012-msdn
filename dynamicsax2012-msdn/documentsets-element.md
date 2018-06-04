---
title: DocumentSets Element
TOCTitle: DocumentSets Element
ms:assetid: 15559b12-102a-47fc-bfc2-5e54b7d03e66
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg882309(v=AX.60)
ms:contentKeyID: 35257137
ms.date: 11/07/2012
mtps_version: v=AX.60
dev_langs:
- html
- xml
---

# DocumentSets Element 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The DocumentSets element is an XML metadata element that specifies a document set.

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
<td><p>Specifies the name of one or more document sets.</p></td>
</tr>
</tbody>
</table>


## Remarks

Use this element to specify the document set for a content element or table of contents. To associate a content element with more than one document set, use semicolons to separate each document set name.

## Example

The following HTML example shows how to use a document **meta** element to specify a document set for a content element. You use **meta** elements to specify the metadata properties of a content element. Notice how the name and content properties of the **meta** element specify the Help system element and the name of a document set.

``` html
<meta name="documentSets" content="UserDocumentation" />
```

The following XML example shows how to use **documentSets** to specify the document set for the table of contents.

``` xml
<documentSets>UserDocumentation</documentSets>
```

## See also

[Description Element](description-element.md)

[Microsoft.Help.F1 Element](microsoft-help-f1-element.md)

[Microsoft.Help.Id Element](microsoft-help-id-element.md)

[Microsoft.Help.Keywords Element](microsoft-help-keywords-element.md)

[Ms.Locale Element](ms-locale-element.md)

[Publisher Element](publisher-element.md)

[SuppressedPublishers Element](suppressedpublishers-element.md)

[TableOfContents Element](tableofcontents-element.md)

[Title Element](title-element.md)

