---
title: Publishing Overview
TOCTitle: Publishing Overview
ms:assetid: 9b030c0d-f5c9-45af-b0ef-abcd27ab55ce
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg882369(v=AX.60)
ms:contentKeyID: 35257198
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# Publishing Overview 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Publishing is the process you use to add or update documentation in Microsoft Dynamics AX Help. To publish new or updated documentation, you copy HTML or XML files to the Help server. You publish files to make the following types of documentation changes:

  - Create a new Help topic.

  - Update an existing Help topic.

  - Add entries to the table of contents.

The following sections provide information about each component of the publishing process.

## File Types

To add or update documentation, you publish the file or files that contain your documentation on the Help server. Typically, you publish files that add content elements and entries for the table of contents. For information about how to create content elements or table of contents documentation, see [Writing Documentation for the Help System](writing-documentation-for-the-help-system.md). The following table describes the types of file that you can publish to the Help server.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>File type</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>HTML</p></td>
<td><p>You use an .html file to publish a single content element. The file contains documentation that creates a new topic or updates an existing topic.</p></td>
</tr>
<tr class="even">
<td><p>Other</p></td>
<td><p>You can also use a non-HTML file to publish a content element. For example, you can use a <strong>Microsoft Word</strong> document. However, you must pair the <strong>Microsoft Word</strong> file together with an HTML file that supplies the metadata properties for your content element.</p></td>
</tr>
<tr class="odd">
<td><p>XML</p></td>
<td><p>You use an .xml file to publish new entries to the table of contents. The file must be named <strong>TableOfContents.xml</strong> or you will not see your entries in the table of contents of the Help viewer.</p></td>
</tr>
</tbody>
</table>


## Metadata

Each content element or table of contents file includes XML metadata properties. When you publish a file, the Help server uses that metadata for the following tasks:

  - The **Windows Search Service** adds the values of the metadata properties to the search index.

  - The Help server queries the search service to find content elements that have metadata values that match criteria specified by a Help request. For example, you might use the help viewer to request the content elements for a specified topic that were published by a specified publisher. To respond to the query, the search service finds the content elements that have metadata values that meet the specified topic and publisher criteria.

  - The Help server uses the metadata in each published **TableOfContents.xml** file to produce the table of contents shown by the Help viewer. The table of contents that you see is the combination of the metadata supplied by each publisher.

## Help Server

To publish documentation, you just copy an HTML or XML file to a folder on the Help server. To organize the published documentation the Help server provides a folder named **content** that contains all published files for that Help server. Typically, you find the **content** folder in the following location:

c:/inetpub/wwwroot/DynamicsAX6HelpServer/content


> [!WARNING]
> <P>When you publish, be careful not to accidentally overwrite existing files that have the same file name. If you overwrite a file, you lose the Help documentation that was contained in the original file.</P>



To reduce the risk of overwriting documentation files from other publishers, a publisher can add one or more subfolders to the **content** folder. These subfolders separate your HTML and XML files from those created by other publishers. Typically, you add sub folders that specify your publisher ID and the language of your content elements. The following example shows the location of the documentation published by Microsoft.

c:/inetpub/wwwroot/DynamicsAX6HelpServer/content/Microsoft/EN-US

The use of subfolders is not required but does represent a best practice for the Help server. The following table describes the most common types of subfolders that you would add to the **content** folder of the Help server:

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Folder name</p></th>
<th><p>Recommended/Optional</p></th>
<th><p>Example</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Publisher ID</p></td>
<td><p>Recommended</p></td>
<td><p>Microsoft</p></td>
<td><p>Specify a name that uniquely identifies the publisher of Help documentation. Typically, you use your Publisher ID from the metadata properties of your content elements. For example, the <strong>Microsoft</strong> folder contains the Help documentation published by Microsoft.</p>
<p>The Publisher ID folder typically contains one or more sub-folders. Use the subfolders to specify the language of your Help documentation.</p></td>
</tr>
<tr class="even">
<td><p>Language</p></td>
<td><p>Recommended</p></td>
<td><p>En-US</p></td>
<td><p>Specify the language of a group of content elements. Typically, you use the same Language value that you use in the metadata properties of the content elements. For example, Microsoft adds a <strong>en-us</strong> subfolder for a collection of content elements written in U.S. English.</p>

> [!WARNING]
> <P>You cannot change the value of the Language metadata property of a content element by changing the name of the folder where it is published.</P>


<p>When you publish HTML or XML files, you copy the files to the language folder for that content element or table of contents file. Typically, a Language folder contains a single TableOfContents.xml file.</p></td>
</tr>
<tr class="odd">
<td><p>Other</p></td>
<td><p>Optional</p></td>
<td><p>TOCResources</p></td>
<td><p>Add subfolders that group related content elements. Use folder names that help you organize and maintain your documentation.</p></td>
</tr>
</tbody>
</table>


To delete existing Help documentation, find the file that contains the content element and remove that file from the Help server. Once the file is removed, the content element is no longer available to the Help viewer.


> [!TIP]
> <P>If you remove a content element file, you might also want to update the table of contents. To ensure the table of contents is accurate, remove or update entries that target the deleted content element.</P>



## Web Configuration

The Help server includes a configuration option that you can use to organize the display of documentation. The Help server groups documentation by publisher ID. To specify the order that documentation from each publisher appears in the Help viewer, use the **Publishers** element in the web.config file of the Help server. The web.config file is typically found in the following location.

c:/inetpub/wwwroot/DynamicsAX6HelpServer/web.config

You use the list of publisher IDs in the **Publishers** element of the web.config file to configure how the Help viewer displays the following information:

  - You want to specify where each publisher appears in the **Search Options** list.

  - You want to organize how content elements are listed on a summary page. For example, you want the summary page to always list your content elements before content elements from another publisher.

  - You want to specify where your entries for the table of contents appear. For example, you want your entries to be added to the beginning of the existing table of contents.

When you publish documentation to the Help server, consider whether to add your publisher ID to the list of publishers in the web.config file. If you do not add your publisher ID to the web.config file, the location of your documentation is determined by the Help server. For information about how to change the web.config file, see [How to: Add a Publisher to the Web.Config File](how-to-add-a-publisher-to-the-web-config-file.md).

## Windows Search Service

The publishing process is complete when the Windows Search Service (WSS) adds metadata information from your HTML or XML file to the search index. You must make sure that the WSS service is running on the Help server.

The Help server uses the search service and its index to locate each content element that matches a help request. As a result, you will not see a newly published content element in the Help viewer until that content element is indexed by WSS.


> [!NOTE]
> <P>You cannot control when WSS indexes a specific file. In addition, WSS is a low priority service that runs after higher priority tasks have completed. The time between copying your HTML or XML file to the Help server and viewing your documentation in the Help viewer can vary. However, if you add just a few files to a Help server that was previously indexed, the new files should be immediately indexed.</P>



## Help Viewer

After WSS has indexed your HTML or XML file, you can use the Help viewer to see the documentation that you added or updated. If you cannot retrieve your documentation, check that the content element file has been indexed. For more information about how to troubleshoot the publishing process, see [Troubleshooting the Publishing Process](troubleshooting-the-publishing-process.md).

## See also

[How to: Add Folders to the Help Server](how-to-add-folders-to-the-help-server.md)

[How to: Add a Publisher to the Web.Config File](how-to-add-a-publisher-to-the-web-config-file.md)

[How to: Publish a Help Document](how-to-publish-a-help-document.md)

[How to: Publish Table of Contents Entries](how-to-publish-table-of-contents-entries.md)

[Document Property Metadata Reference](document-property-metadata-reference.md)

