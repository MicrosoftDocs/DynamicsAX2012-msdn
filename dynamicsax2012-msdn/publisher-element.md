---
title: Publisher Element
TOCTitle: Publisher Element
ms:assetid: e3122c75-22cb-4f19-9300-fbdac05e452c
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg882387(v=AX.60)
ms:contentKeyID: 35257214
ms.date: 11/07/2012
mtps_version: v=AX.60
dev_langs:
- html
- xml
---

# Publisher Element [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The Publisher element is an XML metadata element that specifies a publisher ID.

## Members

The following table lists the elements of the data type.

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
<td><p>Specifies the name of the publisher.</p></td>
</tr>
</tbody>
</table>


## Remarks

Use this element to identify the publisher of a content element, or table of contents. Use the same publisher name that you added to the web.config file of the help server.


> [!WARNING]
> <P>If you specify a publisher name that is not in the web.config file, you will not be able to view your content element or table of contents information.</P>



## Example

The following HTML example shows how to use a document **meta** element to specify a publisher for a content element. You use **meta** elements to specify the metadata properties of a content element. Notice how the name and content properties of the **meta** element specify the Help system element and publisher name.

``` html
<meta name="publisher" content="Microsoft" />
```

The following XML example shows how to specify the publisher of a table of contents.

``` xml
<publisher>Microsoft</publisher>
```

## See also

[Description Element](description-element.md)

[DocumentSets Element](documentsets-element.md)

[Microsoft.Help.F1 Element](microsoft-help-f1-element.md)

[Microsoft.Help.Id Element](microsoft-help-id-element.md)

[Microsoft.Help.Keywords Element](microsoft-help-keywords-element.md)

[Ms.Locale Element](ms-locale-element.md)

[SuppressedPublishers Element](suppressedpublishers-element.md)

[TableOfContents Element](tableofcontents-element.md)

[Title Element](title-element.md)

