---
title: Microsoft.Help.Keywords Element
TOCTitle: Microsoft.Help.Keywords Element
ms:assetid: f31ca58d-a105-49bd-8889-9d744df08682
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg882388(v=AX.60)
ms:contentKeyID: 35257215
ms.date: 11/07/2012
mtps_version: v=AX.60
dev_langs:
- html
---

# Microsoft.Help.Keywords Element 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The Microsoft.Help.Keywords element is an XML metadata element that specifies search term.

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
<td><p>Specifies the word to use as a search term for the content element.</p></td>
</tr>
</tbody>
</table>


## Remarks

Use this element to associate keywords with a content element. Specify the words you expect to be included in a search query that is trying to locate your document. Your keywords can include multi-word terms. For example, you can use **document sets** as a keyword.

To add more than one keyword to a content element, use semicolons to separate each keyword.


> [!TIP]
> <P>Use multiple keywords to support term-variation searches for documents. For example, you might include both <STRONG>document sets</STRONG> and <STRONG>documentsets</STRONG> as keywords for a content element that discusses the use of a Help system document set.</P>



## Example

The following HTML example shows how to use a document **meta** element to specify keywords for a content element. You use **meta** elements to specify the metadata properties of a content element. Notice how the name and content properties of the **meta** element specify the Help system element and keywords. Also, notice how this content element includes two keywords.

``` html
<meta name="Microsoft.Help.Keywords" content="reversal; transfer" />
```

## See also

[Description Element](description-element.md)

[DocumentSets Element](documentsets-element.md)

[Microsoft.Help.F1 Element](microsoft-help-f1-element.md)

[Microsoft.Help.Id Element](microsoft-help-id-element.md)

[Ms.Locale Element](ms-locale-element.md)

[Publisher Element](publisher-element.md)

[SuppressedPublishers Element](suppressedpublishers-element.md)

[Title Element](title-element.md)

