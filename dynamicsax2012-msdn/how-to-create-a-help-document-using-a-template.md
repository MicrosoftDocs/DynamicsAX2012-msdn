---
title: 'How to: Create a Help Document using a Template'
TOCTitle: 'How to: Create a Help Document using a Template'
ms:assetid: af5563fc-b1cd-4038-b8de-ab832ec0ea82
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg882374(v=AX.60)
ms:contentKeyID: 35257203
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# How to: Create a Help Document using a Template [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

This topic describes how to use a template to create new Help documentation that you can publish to the Help server. Each template includes the basic components of a content element and helps you focus on the information that is unique to your Help documentation. The following table specifies the types of templates:

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Template type</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>HTML</p></td>
<td><p>The HTML templates help you create documentation that appears in the Help viewer. The HTML templates help you produce a content element that uses the same style and resources as the existing Help documentation. To use an HTML template, you have to have an HTML or text editor that can open and save .htm files.</p></td>
</tr>
<tr class="even">
<td><p>Microsoft Word</p></td>
<td><p>The Word template helps you use Word 2007 or a later version to create documentation. The Word template offers the flexibility to create new types of Help documentation or add existing documentation to the Help server. In addition, you can use the template to automatically create the HTML file that is required to publish a Word document on the Help server.</p></td>
</tr>
</tbody>
</table>


The following sections provide information about how to use each type of template to produce Help documentation:

  - To Use the Word Template to Create a Content Element

  - To Use an HTML Template to Create a Content Element

### To Use the Word Template to Create a Content Element

1.  Open the Microsoft Dynamics AX Help viewer. Type **Templates for Help Documentation** in the **Search Help** field, and then press ENTER. The specified topic appears in the Help viewer.

2.  In the Help viewer, find the table that contains the Word template, and then click the name of the template. The template opens on your computer. For example, click **Dynamics Help Content Template.docm** to open that template. The template opens using the default program associated with the .docm file type on your computer.
    
    If you are prompted to select a program for the template, specify that Word 2007 or a later version. Word might notify you that the document includes macros and that the macros are currently disabled. Use Word to enable macros for this document.
    

    > [!WARNING]
    > <P>If you do not enable macros, you will not be able to use the template to produce the HTML file that contains the document properties for the content element.</P>



3.  In Word 2007, click the Office button and then click **Save As**. In Word 2010, click **File** and then click **Save As**. In the **Save As** window, specify the folder where you want to save the file, enter a name for the file, click .docm in the **Save as type** list, and then click **Save**.
    
    Word saves the file in the specified folder. In addition, the template automatically creates and saves two files that have the same name. The following table shows the types of files that are created:
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>File extension</p></th>
    <th><p>Description</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>.docm</p></td>
    <td><p>The Word file that you use to create a Help document.</p></td>
    </tr>
    <tr class="even">
    <td><p>.htm</p></td>
    <td><p>An HTML file that contains the document properties for the Word document.</p></td>
    </tr>
    <tr class="odd">
    <td><p>.mht</p></td>
    <td><p>An HTML file that saves the Word document as a webpage.</p></td>
    </tr>
    </tbody>
    </table>


4.  Use Word to add the title, headings, paragraphs, and other documentation to the template. You can enter the text into the template or cut documentation from an existing document and paste it into the template.

5.  Click the **Dynamics Help** tab. The following table lists the **Required Properties** that must be populated with values:
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Name</p></th>
    <th><p>Description</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Title</p></td>
    <td><p>Specify the text you want to display for this documentation when it appears in a list of search results or a summary page.</p></td>
    </tr>
    <tr class="even">
    <td><p>Topic ID</p></td>
    <td><p>Specify a value that identifies the topic associated with this content element. If you specify more than one ID, use semicolons to separate each entry.</p></td>
    </tr>
    <tr class="odd">
    <td><p>Language</p></td>
    <td><p>Select a language from the drop-down list.</p></td>
    </tr>
    </tbody>
    </table>


6.  Populate the **Optional Properties** for your document. Supply values for the properties in the following table that apply to your document:
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Name</p></th>
    <th><p>Description</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Publisher ID</p></td>
    <td><p>Specify the ID of the publisher of the document.</p></td>
    </tr>
    <tr class="even">
    <td><p>Hide Publishers</p></td>
    <td><p>Specify one or more publisher IDs. Separate each publisher ID value with a semicolon.</p></td>
    </tr>
    <tr class="odd">
    <td><p>Keywords</p></td>
    <td><p>Specify one or more search keywords associated with the documentation. Separate each keyword with a semicolon.</p></td>
    </tr>
    </tbody>
    </table>


7.  Verify that the **Automatically Save Properties** check box is selected. This ensures the values in the document properties boxes are saved to the .htm file every time that you save the Word document.

8.  Verify that the **Save As Webpage** check box is selected. This guarantees that the .mht webpage file is created or updated every time that you save the Word document.

9.  To save the document, click **Save** in the **Quick Access** toolbar. The .docm file, the .html file, and the .mht file are saved in the folder that you specified earlier.

### To Use an HTML Template to Create a Content Element

1.  Press F1 to open the Help viewer. Type **Templates for Help Documentation** in the **Search Help** field, and then press ENTER. The specified topic appears in the Help viewer.

2.  In the Help viewer, find the table that lists the HTML templates. Click the name of the template you want to use. For example, if you want to create documentation that introduces a new component, click **ConceptualTemplate.htm**.
    

    > [!IMPORTANT]
    > <P>The template opens using the default program associated with the .htm file type on your computer. If the template opens in a Web browser, you might have to save the template file to your computer so that you can open the file by using an HTML or text editor.</P>



3.  To create the file for the content element, click the **Save As** option of the HTML or text editor, specify the name for the file, specify that the file type as .htm or .html, and then click **Save**. An .htm or.html file that uses the specified file name is created.

4.  Use the HTML editor to find the meta elements for the document properties. You have to specify a value for the content attribute for the following elements:
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Name</p></th>
    <th><p>Description</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>documentSets</p></td>
    <td><p>Type <strong>UserDocumentation</strong>.</p></td>
    </tr>
    <tr class="even">
    <td><p>Microsoft.Help.Id</p></td>
    <td><p>Specify a value that uniquely identifies this content element. To ensure the ID is unique, you might want to use a GUID.</p></td>
    </tr>
    <tr class="odd">
    <td><p>Microsoft.Help.F1</p></td>
    <td><p>Specify a value that identifies the topic associated with this content element. If you enter more than one ID, use semi-colons to separate each entry.</p></td>
    </tr>
    <tr class="even">
    <td><p>ms.locale</p></td>
    <td><p>Select a language from the drop-down list.</p></td>
    </tr>
    <tr class="odd">
    <td><p>Title</p></td>
    <td><p>Specify the text you want to display for this documentation when it appears in a list of search results or a summary page.</p></td>
    </tr>
    </tbody>
    </table>


5.  Specify values for the optional document properties that apply to your content element. Use the HTML editor to populate the content attribute for the following document properties that apply to your documentation:
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Name</p></th>
    <th><p>Description</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>description</p></td>
    <td><p>Provide text that summarizes the information in the content element.</p></td>
    </tr>
    <tr class="even">
    <td><p>publisher</p></td>
    <td><p>Specify the ID that identifies the publisher of the document.</p></td>
    </tr>
    <tr class="odd">
    <td><p>suppressedPublishers</p></td>
    <td><p>Enter one or more publisher IDs. Separate each publisher ID value with a semicolon.</p></td>
    </tr>
    <tr class="even">
    <td><p>Microsoft.Help.Keywords</p></td>
    <td><p>Specify one or more search keywords associated with the documentation. Separate each keyword with a semicolon.</p></td>
    </tr>
    </tbody>
    </table>


6.  Use the HTML editor to find the link, script, and img elements. Verify that the src attribute of each element correctly specifies the path of targeted file. If needed, update the file path of the location of the file on your Help server. Typically, the target files are installed in the **c:/inetput/wwwroot/\<HelpServer\>/content/Microsoft/en-us/local** folder of the Help server.

7.  Use the HTML editor to add the title, headings, paragraphs, and other documentation to the template.

8.  To add links to related content elements, find the **seeAlsoSection**. Use an existing dynHelp element to add the link. To create the link, populate the topicId attribute by using the ID of the content element, populate the documentSet attribute by using UserDocumentation, and then add the text you want the link to display. The following code example shows a link that opens the **Customers (form)** content element:
    
        <div class="seeAlsoStyle">
            <span>
                <dynHelp:topicLink topicId="c3fc5774-6ed0-4760-86f5-7899e825ab25" documentSet="UserDocumentation">Customers (form)</dynHelp:topicLink>
            </span>
        </div>

9.  To save the document, click **Save** in the HTML or text editor.

## See also

[Using Templates to Create Documentation](using-templates-to-create-documentation.md)

[Authoring Help Documents](authoring-help-documents.md)

[Publishing Documentation to the Help System](publishing-documentation-to-the-help-system.md)

