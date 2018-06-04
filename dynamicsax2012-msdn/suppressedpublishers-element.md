---
title: SuppressedPublishers Element
TOCTitle: SuppressedPublishers Element
ms:assetid: d8fea9e6-6495-4f98-80ea-452881d7b95b
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg882386(v=AX.60)
ms:contentKeyID: 35257213
ms.date: 11/07/2012
mtps_version: v=AX.60
dev_langs:
- html
---

# SuppressedPublishers Element 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The SuppressedPublishers element is an XML metadata element that specifies the ID of a publisher.

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
<td><p>Specifies the ID of the publisher.</p></td>
</tr>
</tbody>
</table>


## Remarks

Use this element to hide the display of content elements from a specified publisher for a single Help topic. When the Help topic is requested, the Help viewer does not display content elements from the specified publisher. Typically, you use **suppressedPublisher** to make sure that your content element is viewed instead of a content element from another publisher.

To specify a publisher, use the publisher name that you find in the web.config file of the Help server.

## Examples

The following HTML example shows how to use a document **meta** element to identify a publisher. You use **meta** elements to specify the metadata properties of a content element. Notice how the name and content properties of the **meta** element specify the Help system element and the publisher.

``` html
<meta name="suppressedPublishers" content="Microsoft" />
```

## See also

[Description Element](description-element.md)

[DocumentSets Element](documentsets-element.md)

[Microsoft.Help.F1 Element](microsoft-help-f1-element.md)

[Microsoft.Help.Id Element](microsoft-help-id-element.md)

[Microsoft.Help.Keywords Element](microsoft-help-keywords-element.md)

[Ms.Locale Element](ms-locale-element.md)

[Publisher Element](publisher-element.md)

[Title Element](title-element.md)

