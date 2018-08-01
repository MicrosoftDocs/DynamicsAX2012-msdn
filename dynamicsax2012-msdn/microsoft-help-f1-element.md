---
title: Microsoft.Help.F1 Element
TOCTitle: Microsoft.Help.F1 Element
ms:assetid: c02eba4f-8f00-4374-8d11-1496beded1c5
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg882384(v=AX.60)
ms:contentKeyID: 35257211
ms.date: 11/07/2012
mtps_version: v=AX.60
dev_langs:
- html
- xml
---

# Microsoft.Help.F1 Element [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The Microsoft.Help.F1 element is an XML metadata element that specifies the ID of a Microsoft Dynamics AX Help topic.

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
<td><p>Specifies the ID of a Help topic.</p></td>
</tr>
</tbody>
</table>


## Remarks

Use this element to associate a content element with a topic. When you press F1 from the workspace, the Help system uses the ID value to identify which content elements to retrieve. To associate a content element with more than one topic, use semi-colons to separate the ID of each topic. One of the examples that follow shows how to associate a content element to more than one topic.

You also use this element to specify a topic ID for a table of contents entry. The Help system uses the ID value to identify the content elements to retrieve when you click that entry in the table of contents. An entry in a table of contents cannot include more than a single topic ID value.

## Examples

The following HTML example shows how to use a document **meta** element to specify a topic ID for a content element. You use **meta** elements to specify the metadata properties of a content element. Notice how the name and content properties of the **meta** element specify the Help system element and ID. Also, notice how this content element includes two topic IDs.

``` html
<meta name="Microsoft.Help.F1" content="Forms.CustTable; c3fc5774-6ed0-4760-86f5-7899e825ab25" />
```

The following XML example shows how to use **Microsoft.Help.F1** to specify the topic ID for a table of content entry.

``` xml
<Microsoft.Help.F1>c3fc5774-6ed0-4760-86f5-7899e825ab25</Microsoft.Help.F1>
```

## See also

[Description Element](description-element.md)

[DocumentSets Element](documentsets-element.md)

[Microsoft.Help.Id Element](microsoft-help-id-element.md)

[Microsoft.Help.Keywords Element](microsoft-help-keywords-element.md)

[Ms.Locale Element](ms-locale-element.md)

[Publisher Element](publisher-element.md)

[SuppressedPublishers Element](suppressedpublishers-element.md)

[TableOfContents Element](tableofcontents-element.md)

[Title Element](title-element.md)

