---
title: 'Best Practices: XML Documentation'
TOCTitle: 'Best Practices: XML Documentation'
ms:assetid: ee059e3b-deec-43b7-a3f2-c8d68548ebad
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc641745(v=AX.60)
ms:contentKeyID: 35253260
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Best Practices: XML Documentation 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Microsoft Dynamics AX conducts a best practices check of the XML comments to make sure that you provide documentation in the appropriate tags. For information about how to set the options for best practice checks, see [Best practice parameters](best-practice-parameters.md).

## Best Practice Checks

The following table lists the best practices error messages and how to fix the errors.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Message</p></th>
<th><p>Message type</p></th>
<th><p>How to fix the error or warning</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Tag '%1' in XML documentation is not supported.</p></td>
<td><p>Warning</p></td>
<td><p>Add XML documentation. For information about how to add XML documentation, see <a href="how-to-add-xml-documentation-to-x-source-code.md">How to: Add XML Documentation to X++ Source Code</a>. Because this is a warning instead of an error, this is optional.</p></td>
</tr>
<tr class="even">
<td><p>Unsupported tag '%1' in XML documentation.</p></td>
<td><p>Error or Warning</p></td>
<td><p>Check the casing of the XML tags if this is reported as an error. If this is reported as a warning, an unsupported tag is present. Remove unsupported tags.</p></td>
</tr>
<tr class="odd">
<td><p>Missing tag '&lt;param name=&quot;%1&quot;&gt;' in XML documentation.</p></td>
<td><p>Error</p></td>
<td><p>Add &lt;param&gt; tags to the XML header template. The &lt;param&gt; tag must have a name attribute. The value of the attribute is case-sensitive and must match the casing in the method.</p></td>
</tr>
<tr class="even">
<td><p>Missing tag 'returns' in XML documentation.</p></td>
<td><p>Error</p></td>
<td><p>Add &lt;returns&gt; tags to the XML header template.</p></td>
</tr>
<tr class="odd">
<td><p>Missing tag 'summary' in XML documentation.</p></td>
<td><p>Error</p></td>
<td><p>Add &lt;summary&gt; tags to the XML header template.</p></td>
</tr>
<tr class="even">
<td><p>Tag '%1' exists more than once in XML documentation.</p></td>
<td><p>Error</p></td>
<td><p>Delete extra tags. This applies only when multiple tags are not appropriate.</p></td>
</tr>
<tr class="odd">
<td><p>Tag '&lt;param name=&quot;%1&quot;&gt;' has no content in XML documentation.</p></td>
<td><p>Error</p></td>
<td><p>Add a description of the parameter between the &lt;param&gt; tags.</p></td>
</tr>
<tr class="even">
<td><p>Tag '&lt;param name=&quot;%1&quot;&gt;' in XML documentation doesn't match actual implementation.</p></td>
<td><p>Error</p></td>
<td><p>Fix the value of the name attribute. It is case-sensitive and must match the casing in the method.</p></td>
</tr>
<tr class="odd">
<td><p>Tag 'exception' has no content in XML documentation.</p></td>
<td><p>Error</p></td>
<td><p>Add a description of the exception between the &lt;exception&gt; tags.</p></td>
</tr>
<tr class="even">
<td><p>Tag 'permission' has no content in XML documentation.</p></td>
<td><p>Error</p></td>
<td><p>Add a description of the required permission between the &lt;permission&gt; tags.</p></td>
</tr>
<tr class="odd">
<td><p>Tag 'remarks' has no content in XML documentation.</p></td>
<td><p>Error</p></td>
<td><p>Add content between the &lt;remarks&gt; tags or delete the &lt;remarks&gt; tags.</p></td>
</tr>
<tr class="even">
<td><p>Tag 'returns' has no content in XML documentation.</p></td>
<td><p>Error</p></td>
<td><p>Add a description of the return value between the &lt;returns&gt; tags.</p></td>
</tr>
<tr class="odd">
<td><p>Tag 'returns' in XML documentation doesn't match actual implementation.</p></td>
<td><p>Error</p></td>
<td><p>Delete the &lt;returns&gt; tags and the description of the return value.</p></td>
</tr>
<tr class="even">
<td><p>Tag 'summary' has no content in XML documentation.</p></td>
<td><p>Error</p></td>
<td><p>Add a topic summary between the &lt;summary&gt; tags.</p></td>
</tr>
<tr class="odd">
<td><p>XML documentation is not well-formed.</p></td>
<td><p>Error</p></td>
<td><p>Make sure that there are no mistakes in the XML tags. Each opening tag must have a corresponding closing tag.</p></td>
</tr>
<tr class="even">
<td><p>Tag 'seealso' has no content in XML documentation.</p></td>
<td><p>Error</p></td>
<td><p>Add content between the &lt;seealso&gt; tags or delete the &lt;seealso&gt; tags.</p></td>
</tr>
<tr class="odd">
<td><p>No XML documentation for this method.</p></td>
<td><p>Error</p></td>
<td><p>XML documentation has not been written for this method.</p></td>
</tr>
</tbody>
</table>


## See also

[XML Documentation](xml-documentation.md)

[XML Documentation Tags](xml-documentation-tags.md)

[XML Documentation Overview](xml-documentation-overview.md)

[How to: Add XML Documentation to X++ Source Code](how-to-add-xml-documentation-to-x-source-code.md)

[How to: Generate XML Documentation Files](how-to-generate-xml-documentation-files.md)

[Walkthrough: Creating XML Documentation in Microsoft Dynamics AX](walkthrough-creating-xml-documentation-in-microsoft-dynamics-ax.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

