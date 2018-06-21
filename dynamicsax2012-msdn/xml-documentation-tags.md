---
title: XML Documentation Tags
TOCTitle: XML Documentation Tags
ms:assetid: 9af147a0-de83-410c-a6b9-78efbeda7be3
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc607340(v=AX.60)
ms:contentKeyID: 35248156
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# XML Documentation Tags [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

In X++, you can document the code you write by using XML comments. This topic describes the tags that are used in the XML comments.

## Tags Used in XML Comments

When you write XML comments, you must follow specific guidelines. Microsoft Dynamics AX conducts a best practices check of the XML comments to make sure that you provide documentation in tags that are required (the \<summary\> tag), and that the parameter documentation matches the parameters listed in the syntax. For information about best practice errors, see [Best Practices: XML Documentation](best-practices-xml-documentation.md).

### ![Cc607340.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc607340.collapse_all(en-us,AX.60).gif")Documenting Methods

The following XML tags are used to document methods in the source code.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>XML tag</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>&lt;summary&gt;</p></td>
<td><p>The summary should provide a brief description of the method. All documented methods should have a summary.</p></td>
</tr>
<tr class="even">
<td><p>&lt;param&gt;</p></td>
<td><p>The parameter tag is used to describe the parameters of the method. Parameter tags are inserted into the header template if parameters are in the syntax. The name of the parameter is inserted into the parameter tag. The parameter description should be brief.</p></td>
</tr>
<tr class="odd">
<td><p>&lt;returns&gt;</p></td>
<td><p>The returns tag is used to describe the value that the method returns. This tag is inserted into the header template if a return value is in the syntax of the method.</p></td>
</tr>
<tr class="even">
<td><p>&lt;remarks&gt;</p></td>
<td><p>The remarks tag can be used to provide information beyond what is documented in the other tags.</p></td>
</tr>
<tr class="odd">
<td><p>&lt;exception&gt;</p></td>
<td><p>The exception tag is used to describe the conditions that cause exceptions to be thrown by a method. This tag is inserted into the header template when it is appropriate.</p></td>
</tr>
<tr class="even">
<td><p>&lt;permission&gt;</p></td>
<td><p>The permission tag is used to describe the permission that is required to access methods using the CodeAccessSecurity.demand method.</p></td>
</tr>
<tr class="odd">
<td><p>&lt;seealso&gt;</p></td>
<td><p>The see also tag is used to provide links to related information.</p></td>
</tr>
</tbody>
</table>


For information about how to add XML documentation to the source code, see [How to: Add XML Documentation to X++ Source Code](how-to-add-xml-documentation-to-x-source-code.md).

### ![Cc607340.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc607340.collapse_all(en-us,AX.60).gif")Documenting Classes

The following XML tags are used to document classes in the source code. You can document classes by adding an XML header template to the classDeclaration code of the class that you want to document. An XML header template precedes X++ code and contains the XML documentation that describes the code.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>XML Tag</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>&lt;summary&gt;</p></td>
<td><p>The class summary should provide a brief description of what the class is used for. All documented classes should have a summary.</p></td>
</tr>
<tr class="even">
<td><p>&lt;remarks&gt;</p></td>
<td><p>The remarks tag can be used to provide information beyond what is documented in the summary.</p></td>
</tr>
</tbody>
</table>


For information about how to add XML documentation to the source code, see [How to: Add XML Documentation to X++ Source Code](how-to-add-xml-documentation-to-x-source-code.md).

## See also

[XML Documentation](xml-documentation.md)

[XML Documentation Overview](xml-documentation-overview.md)

[How to: Generate XML Documentation Files](how-to-generate-xml-documentation-files.md)

[Walkthrough: Creating XML Documentation in Microsoft Dynamics AX](walkthrough-creating-xml-documentation-in-microsoft-dynamics-ax.md)

[Best Practices: XML Documentation](best-practices-xml-documentation.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

