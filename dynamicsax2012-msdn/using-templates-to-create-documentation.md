---
title: Using Templates to Create Documentation
TOCTitle: Using Templates to Create Documentation
ms:assetid: 944ea4fd-b909-4aa4-ab83-db06cb5508bb
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg882362(v=AX.60)
ms:contentKeyID: 35257191
ms.date: 05/19/2014
mtps_version: v=AX.60
---

# Using Templates to Create Documentation [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The Microsoft Dynamics AX Help system includes a collection of templates. A template is a document you use to create a content element that you can publish to the Help server. The template includes a framework of elements, styles, and guidelines. The templates are stored on the Help server and represent the common types of Help documentation.

To open a template on your computer, start the Microsoft Dynamics AX Help viewer. Type **Templates for Help Documentation** in the **Search Help** field, and then press ENTER. The content element that appears in the Help viewer contains a link to each template. To open a template on your computer, click the link to the template you want to use. The following sections describe the types of templates that are available. Or you can download the template file from [http://go.microsoft.com/fwlink/?LinkID=399149](http://go.microsoft.com/fwlink/?linkid=399149).

## Microsoft Word

You can create Help documentation with Microsoft Word 2007 or later versions by using the Microsoft Word template. The Microsoft Word template helps you create Help documentation by using familiar tools. In addition, you can use the Word template to convert existing Help documentation to a format that you can publish to the Help server. When you click **Save** from the template, you get one or more of the following types of files:

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
<td><p>Microsoft Word</p></td>
<td><p>By default, the template saves the document as a .docm file. The .docm file is the source document for your content element. Any changes or updates must be made to the .docm file. To publish a Microsoft Word document, you can also use a .docx file type.</p></td>
</tr>
<tr class="even">
<td><p>HTML</p></td>
<td><p>By default, the template automatically creates an .htm file that has same name as the .docm file. The .htm file contains the document property values that you entered in the <strong>Microsoft Dynamics Help</strong> tab. The Help server uses the document properties to match the content element to a Help request.</p>
<p>To specify whether to create the .htm file, you use the <strong>Automatically Save Properties</strong> check box in the <strong>Microsoft Dynamics Help</strong> tab.</p></td>
</tr>
<tr class="odd">
<td><p>Webpage</p></td>
<td><p>By default, the template automatically creates an .mht file that has same name as the .docm file. The .mht file is an HTML representation of the Microsoft Word document.</p>
<p>To specify whether to create the .mht file, you use the <strong>Save As Webpage</strong> check box in the <strong>Microsoft Dynamics Help</strong> tab.</p></td>
</tr>
</tbody>
</table>


To publish a content element that you created that uses the MicrosoftWord template, you have to select the files that you want to use. Use the following information to help you select the files you want to publish.

  - If you publish the webpage file, your content element will appear in the Help viewer. To publish the webpage file, you have to copy the .mht and .htm files to the same folder on the Help server.

  - If you publish the Word file, your content element opens in Word and not the Help viewer. As a result, each client computer must have Microsoft Word or another program that can view .docm or .docx files. To publish the Word file, you have to copy the .docm or .docx file and the .htm file to the same folder on the Help server.

The following table lists the Word templates.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Template name</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Dynamics Help Content Template.docm</p></td>
<td><p>Use this template to create Help documentation. You can create new documentation or copy documentation from an existing file and paste it into the template. For more information about how to use the Word template, see <a href="how-to-create-a-help-document-using-a-template.md">How to: Create a Help Document using a Template</a>.</p></td>
</tr>
</tbody>
</table>


## HTML

You can create content elements that resemble Help documentation created by Microsoft by using the HTML templates. To use an HTML template, you need an HTML or text editor installed on your computer. The editor must be able to save your documentation as an .htm or .html file. In addition, you have to be familiar with editing individual HTML elements and attributes.

Each template includes the basic HTML document framework that works with the Help viewer. The framework includes the style resources used by the Microsoft Dynamics AX Help documentation. To create a Help document:

  - You can add, copy, or remove elements from the template framework.

  - You add the content to the template that you want to appear in the Help viewer.

  - You update the HTML meta elements and supply a value for each document property.

For more information about how to use an HTML template, see [How to: Create a Help Document using a Template](how-to-create-a-help-document-using-a-template.md). The following table lists the HTML templates.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Template name</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Dynamics Help Concept Template.htm</p></td>
<td><p>Use this template to create an overview of a subject area. The template has the fewest elements and provides the greatest flexibility. The template includes elements that help you add an alert, a list, a table, and links to content elements</p></td>
</tr>
<tr class="even">
<td><p>Dynamics Help Form Template.htm</p></td>
<td><p>Use this template to create documentation for a specified form. The template helps you organize your documentation around the common user interface components and controls that you find on a form. The template includes elements that help you add a menu item, labels, an alert, links to content elements, and a table.</p></td>
</tr>
<tr class="odd">
<td><p>Dynamics Help KeyTask Template.htm</p></td>
<td><p>Use this template to create documentation for a more complex task. The template helps you organize your documentation around the steps and resources that you use to complete the task. The template includes elements that help you add links to section headings, links to content elements, an alert, a numbered list, and labels.</p></td>
</tr>
<tr class="even">
<td><p>Dynamics Help Orientation Template.htm</p></td>
<td><p>Use this template to create a document that links to related documentation. The template helps you introduce a subject area and provides links to the documentation for that subject area. The template includes elements that help you add links to content elements.</p></td>
</tr>
<tr class="odd">
<td><p>Dynamics Help Procedure Template.htm</p></td>
<td><p>Use this template to create documentation for a simple task. The template helps you organize your documentation into a series of numbered steps. The template includes elements that help you add an alert, a numbered list, labels, a table, and links to content elements.</p></td>
</tr>
</tbody>
</table>


## See also

[Authoring Help Documents](authoring-help-documents.md)

[How to: Publish a Help Document](how-to-publish-a-help-document.md)

  
**Announcements:** To see known issues and recent fixes, use [Issue search](http://go.microsoft.com/fwlink/?linkid=389258) in [Microsoft Dynamics Lifecycle Services](http://go.microsoft.com/fwlink/?linkid=306505) (LCS).

