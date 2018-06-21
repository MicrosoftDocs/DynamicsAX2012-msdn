---
title: Ms.Locale Element
TOCTitle: Ms.Locale Element
ms:assetid: b1946897-d05a-4a72-ba56-1c5f248970ec
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg882379(v=AX.60)
ms:contentKeyID: 35257206
ms.date: 11/07/2012
mtps_version: v=AX.60
dev_langs:
- html
- xml
---

# Ms.Locale Element [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

An ms.locale element is an XML metadata element that specifies a language.

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
<td><p>Specifies the language of a content element or the table of contents.</p></td>
</tr>
</tbody>
</table>


## Remarks

Use a value that identifies the language that is used for the content element or table of contents entries. Typically, you use a language code like EN-US for US English or DA for Danish to specify the language.

## Example

The following HTML example shows how to use a document **meta** element to specify the language. You use **meta** elements to specify the metadata properties of a content element. Notice how the name and content properties of the **meta** element specify the Help system element and a language code.

``` html
<meta name="ms.locale" content="EN-US" />
```

The following XML example shows how to use **ms.locale** to specify a language code for a table of contents.

``` xml
<ms.locale>EN-US</ms.locale>
```

## See also

[Description Element](description-element.md)

[DocumentSets Element](documentsets-element.md)

[Microsoft.Help.F1 Element](microsoft-help-f1-element.md)

[Microsoft.Help.Id Element](microsoft-help-id-element.md)

[Microsoft.Help.Keywords Element](microsoft-help-keywords-element.md)

[Publisher Element](publisher-element.md)

[SuppressedPublishers Element](suppressedpublishers-element.md)

[TableOfContents Element](tableofcontents-element.md)

[Title Element](title-element.md)

