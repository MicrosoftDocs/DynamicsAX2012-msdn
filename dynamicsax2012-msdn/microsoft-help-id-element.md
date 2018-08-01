---
title: Microsoft.Help.Id Element
TOCTitle: Microsoft.Help.Id Element
ms:assetid: 44983c8b-3125-4402-87f1-ddf99bc3815c
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg882342(v=AX.60)
ms:contentKeyID: 35257172
ms.date: 11/07/2012
mtps_version: v=AX.60
dev_langs:
- html
---

# Microsoft.Help.Id Element [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The Microsoft.Help.Id element is an XML element that specifies a unique ID for a content element.

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
<td><p>Specifies the ID value that uniquely identifies the content element.</p></td>
</tr>
</tbody>
</table>


## Remarks

Use this element to specify the ID of a content element. The ID value must be unique and cannot duplicate the ID of an existing content element. Typically, you use a GUID to ensure the ID value is unique but you can use a text value for the ID.

## Example

The following HTML example shows how to use a document **meta** element to specify the ID of a content element. You use **meta** elements to specify the metadata properties of a content element. Notice how the name and content properties of the **meta** element specify the Help system element and ID.

``` html
<meta name="Microsoft.Help.Id" content="c3fc5774-6ed0-4760-86f5-7899e825ab25" />
```

## See also

[Description Element](description-element.md)

[DocumentSets Element](documentsets-element.md)

[Microsoft.Help.F1 Element](microsoft-help-f1-element.md)

[Microsoft.Help.Keywords Element](microsoft-help-keywords-element.md)

[Ms.Locale Element](ms-locale-element.md)

[Publisher Element](publisher-element.md)

[SuppressedPublishers Element](suppressedpublishers-element.md)

[Title Element](title-element.md)

