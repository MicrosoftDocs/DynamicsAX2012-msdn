---
title: Help Document Set Properties
TOCTitle: Help Document Set Properties
ms:assetid: a1fe4226-d521-4f35-9b0c-76c1ad3aaa97
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg731860(v=AX.60)
ms:contentKeyID: 35132740
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# Help Document Set Properties [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

A Document Set is a collection of Help documentation associated with a Microsoft Dynamics AX workspace. When you publish a content element, you use metadata to add your content element or table of contents information to a document set.

To manage the relationship between a workspace and a document set, the Application Object Tree (AOT) includes a node named **Help Document Sets**. Each document set in the **Help Document Sets** node includes a collection of properties. You edit these properties when you add a new document set or change the relationship between a document set and a workspace.


> [!WARNING]
> <P>A workspace can be associated with only a single document set. While the AOT lets you add a new document set and associate it with a workspace, you will no longer see documentation from the document set that you replaced. Typically, you use <STRONG>UserDocumentation</STRONG> as the document set for any content element or table of contents entries that you publish to the Help server.</P>



The following table describes the properties for a document set in the **Help Document Sets** node of the AOT:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Property</p></th>
<th><p>Type</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DocumentSetName</p></td>
<td><p>String</p></td>
<td><p>A name that uniquely identifies the document set. The name is limited to 40 characters and must not contain whitespace. Use the value of this property when you set the value of the DocumentSets metadata element in a content element or table of contents file</p></td>
</tr>
<tr class="even">
<td><p>DocumentSetDescription</p></td>
<td><p>String</p></td>
<td><p>The text or label to display for the document set. This value appears in the <strong>Search content from</strong> list of the <strong>Options</strong> menu of the Help viewer.</p></td>
</tr>
<tr class="odd">
<td><p>AddToApplicationHelpMenu</p></td>
<td><p>Boolean</p></td>
<td><p>Set to <strong>Yes</strong> when you want the document set to appear in the Help menu of the application workspace.</p></td>
</tr>
<tr class="even">
<td><p>AddToDeveloperHelpMenu</p></td>
<td><p>Boolean</p></td>
<td><p>Set to <strong>Yes</strong> when you want the document set to appear in the Help menu of the developer workspace.</p></td>
</tr>
<tr class="odd">
<td><p>UserDocumentSet</p></td>
<td><p>Boolean</p></td>
<td><p>Set to <strong>Yes</strong> when you want to associate the document set with the application workspace. If you set this property to <strong>No</strong>, you will not be able to view the context-sensitive (F1) Help that was published by Microsoft.</p></td>
</tr>
<tr class="even">
<td><p>DeveloperDocumentSet</p></td>
<td><p>Boolean</p></td>
<td><p>Set to <strong>Yes</strong> when you want to associate the document set with the development workspace. If you set this property to <strong>No</strong>, you will not be able to view the context-sensitive (F1) Help that was published by Microsoft.</p></td>
</tr>
<tr class="odd">
<td><p>ContentLocation</p></td>
<td><p>Enumeration</p></td>
<td><p>An enumeration value that specifies where to retrieve documentation. The following table describes the enumeration.</p>
<div class="caption">
</div>
<div class="tableSection">
<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Value</p></th>
<th><p>Label</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1</p></td>
<td><p>Help server</p></td>
<td><p>The documentation is stored on the Help server. This option is used with the <strong>UserDocumentation</strong> and any document set that has files published on the Help server.</p></td>
</tr>
<tr class="even">
<td><p>2</p></td>
<td><p>World Wide Web</p></td>
<td><p>The documentation is stored on MSDN or a similar web site. This option is required for the <strong>DeveloperDocumentation</strong> documentation set and should not be used with any other document set.</p></td>
</tr>
</tbody>
</table>

</div></td>
</tr>
</tbody>
</table>


## See also

[Document Property Metadata Reference](document-property-metadata-reference.md)

