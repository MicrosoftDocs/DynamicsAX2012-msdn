---
title: Authoring Help Documents
TOCTitle: Authoring Help Documents
ms:assetid: 0bd20f64-f93d-4172-9e1e-bd63836eb4ed
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg882301(v=AX.60)
ms:contentKeyID: 35257131
ms.date: 04/29/2013
mtps_version: v=AX.60
dev_langs:
- html
---

# Authoring Help Documents [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Authoring is the process you use to create documentation for the Help system. The Microsoft Dynamics AX Help server lets you add custom Help documentation that can appear in the Help viewer. To add custom documentation, you can create a file called a content element. You can also add an XML file that adds table of contents entries that link to new content elements.

The following sections provide an overview of types of custom documentation along with the files, tools, and components you can use to create a content element:

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Types of Custom Help Documentation</p></td>
</tr>
<tr class="even">
<td><p>File Types for Help Documentation</p></td>
</tr>
<tr class="odd">
<td><p>Customization Tools</p></td>
</tr>
<tr class="even">
<td><p>Using XHTML in Help Documentation</p></td>
</tr>
<tr class="odd">
<td><p>Document Properties</p></td>
</tr>
<tr class="even">
<td><p>Adding Links to Other Help Topics</p></td>
</tr>
<tr class="odd">
<td><p>Using Labels in Help Documentation</p></td>
</tr>
<tr class="even">
<td><p>Using Images in Help Documentation</p></td>
</tr>
<tr class="odd">
<td><p>Using Cascading Style Sheets with Help Documentation</p></td>
</tr>
<tr class="even">
<td><p>Using Script Files with Help Documentation</p></td>
</tr>
</tbody>
</table>


## Types of Custom Help Documentation

To customize the documentation that appears in the Help viewer, you have to add files that contain documentation to the Help server. The Help server supports a limited number of customization options. The following table describes the types of actions that you can use to add custom documentation.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Customization</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Create or update a Help topic</p></td>
<td><p>To create a new topic or update an existing topic, you add a content element to the Help server. A content element is a file that contains Help documentation for a specified topic.</p></td>
</tr>
<tr class="even">
<td><p>Add a topic to the table of contents</p></td>
<td><p>To add an entry to the table of contents that appears in the Help viewer, you add an entry to an XML file that goes on the Help server.</p></td>
</tr>
</tbody>
</table>


## File Types for Help Documentation

After you identify the type of customization you want to make, you select the type of file to use for the content element. The typical content element is an HTML document and is stored on the Help server as an HTML file. However, you can use other types of documents. The following table lists the types of files you use to create Help documentation.

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
<td><p>The documentation that appears in the Help viewer uses HTML. To create a new content element that use the same style and script elements as the Microsoft Help documentation, use HTML to create your documentation. When you complete your documentation, save that content element as an .mht, .htm, or .html file.</p></td>
</tr>
<tr class="even">
<td><p>Microsoft Office Word</p></td>
<td><p>To simplify how to create documentation or to publish existing documentation, use Microsoft Office Word to create your Help documentation. Use Word to save the document as a .docx or .docm file.</p>
<p>To add a Word document to the Help server, you have to supply an HTML file together with your Word document. You use the HTML file to specify values for the document properties the Help server uses to match a content element to a Help request.</p>
<p>The Help viewer does not display Word documents. To view the documentation in a Word file, each client computer must have an application that can open and view .docx or .docm files.</p></td>
</tr>
<tr class="odd">
<td><p>Other document types</p></td>
<td><p>To publish existing documentation or to use other types of documentation, you can create content elements that use file types other than HTML or Word.</p>
<p>To use other file types, you have to supply an HTML file together with each file. You use the HTML file to specify values for the document properties that the Help server uses to match a content element to a Help request.</p>
<p>The Help viewer does not display non-HTML documents. To view these types of documents, each client computer must have an application that can open and view the specified type of file.</p></td>
</tr>
<tr class="even">
<td><p>XML</p></td>
<td><p>To add entries to the table of contents that appears in the Help viewer, you have to use an XML file. For more information about how to create an XML entry for the table of contents, see <a href="how-to-create-table-of-contents-entries.md">How to: Create Table of Contents Entries</a>.</p></td>
</tr>
</tbody>
</table>


To help you create a content element, the Help system includes a collection of HTML and Word templates. A template is a special type of document that you use to create files that you can publish to the Help server. Each template is a framework of elements, styles, and guidelines that help you create documentation.

The templates are stored on the Help server and represent common types of documentation. To see a list of the templates, open the Help viewer, enter **Templates for Help Documentation** in the search box, and press ENTER. There are templates for the following types of documentation files:

  - The HTML templates help you create documentation that resembles the Help documentation from Microsoft. To use an HTML template, you have to know how to write and edit HTML. The HTML templates help you create content elements that appear in the Help viewer.

  - The Word templates help you use Microsoft Office Word 2007 or a later version to create documentation. The template follows the style and organization of existing Microsoft documentation. In addition, the Word template includes the ability to create the supplemental HTML file that is required for each Word file.

## Customization Tools

After you identify the template or file type you want to use, you need an application that creates the specified type of documentation. The following table identifies applications that are used for the most common file types.

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
<td><p>To produce content elements that use HTML, you can use any text or HTML editor that produces HTML. Your editor must be able to save your documentation as an .htm or .html file.</p></td>
</tr>
<tr class="even">
<td><p>Microsoft Office Word</p></td>
<td><p>To produce content element that uses a Word file, you have to use Microsoft Word 2007 or later versions. Use Word to save your documentation as a .docm file.</p>
<p>If you use a Word template, use the template to create the .mht and .htm HTML files for that content element. To create the HTML files, you must enable macros in Word.</p>
<p>If you do not use a template, you must use a text or HTML editor to create the HTML file for your Word document.</p></td>
</tr>
<tr class="odd">
<td><p>Other</p></td>
<td><p>To produce other types of documentation, use the application that creates and saves the type of file that you want to use.</p>
<p>In addition, you have to use a text or HTML editor to create the HTML file for your documentation. Use the HTML file to specify values for the document properties that apply to your content element. Save the file as an .htm or .html file.</p></td>
</tr>
<tr class="even">
<td><p>XML</p></td>
<td><p>To add entries to the table of contents, use a text or XML editor that can produce and save an .xml file.</p></td>
</tr>
</tbody>
</table>


## Using XHTML in Help Documentation

The Help documentation that you publish to the Help server has to comply with XHTML standards. If you view a content element on the Help server, you will find the following declaration. Notice how the declaration specifies the XHTML 1.0 transitional document type definition (DTD).

    <!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd"[]>

XHTML is a document type that uses XML to reproduce and extend HTML. The XHTML transitional DTD includes all HTML elements and attributes. Framesets are not allowed. In addition, the DTD requires that your markup be written as well-formed XML.

If your document does not meet the XHTML standard, your document will not appear in the Help viewer. For example, you can use \&nbsp; in HTML to represent a blank space. However, XHTML does not include \&nbsp;. If you add \&nbsp; to a content element, that content element will not be indexed by the Help server and cannot be accessed from the Help viewer.


> [!TIP]
> <P>To specify a blank space in a content element, you should replace &amp;nbsp; with &amp;#160; which is how you specify a blank space in XHTML. You can also use the following document type declaration to replace &amp;nbsp; in a content element &lt;!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd"[&lt;!ENTITY nbsp "&amp;#160;"&gt;]&gt;.</P>



## Document Properties

A document property is a metadata element that provides additional information about the documentation in a content element. Each content element on the Help server includes a collection of document properties. The document properties represent important attributes that the Help server uses to match content elements to a request for documentation.


> [!WARNING]
> <P>If you do not provide the required document properties for a content element, your Help documentation might not appear in the Help viewer.</P>



In an HTML file, the document properties are embedded as metadata elements. For Word documents and other non-HTML files, you have to provide a separate HTML file that includes the document properties for that document. If you provide a supplemental HTML file, that file must have the same file name as the document file. For more information about each document property, see [Document Property Metadata Reference](document-property-metadata-reference.md).

The following table describes the document properties for a content element.

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Property name</p></th>
<th><p>Metadata name</p></th>
<th><p>Required</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Content ID</p></td>
<td><p>Microsoft.Help.Id</p></td>
<td><p>Yes</p></td>
<td><p>A text value that specifies a unique ID value for a content element. To create a unique ID, consider using a GUID value. However, you are not required to use a GUID.</p>

> [!NOTE]
> <P>The ID must be unique across all the content elements provided by the specified publisher.</P>


</td>
</tr>
<tr class="even">
<td><p>Description</p></td>
<td><p>description</p></td>
<td><p>No</p></td>
<td><p>A text value that specifies the brief summary of the content element that appears in the search results in the Help viewer.</p></td>
</tr>
<tr class="odd">
<td><p>Document set</p></td>
<td><p>documentSets</p></td>
<td><p>Yes</p></td>
<td><p>An enumeration value that specifies the document collection for the content element. This should be set to UserDocumentation.</p></td>
</tr>
<tr class="even">
<td><p>Search keywords</p></td>
<td><p>Microsoft.Help.Keywords</p></td>
<td><p>No</p></td>
<td><p>A semi-colon delimited collection of keyword entries that specify search terms for the content element.</p>
<p>If a keyword matches a term in a search request, the search service ranks that content element higher in the list of the search results that appear in the Help viewer.</p></td>
</tr>
<tr class="odd">
<td><p>Ms.locale</p></td>
<td><p>ms.locale</p></td>
<td><p>Yes</p></td>
<td><p>A text value that specifies the language for the content element. Use a language code to identify the language. For example, use EN-US for United States English.</p>
<p>The ms.locale property supports the use of localized content. To specify the preferred language for Help documentation, change the language code in the <strong>Alternative help language</strong> field of the <strong>User options</strong> form.</p></td>
</tr>
<tr class="even">
<td><p>Publisher ID</p></td>
<td><p>publisher</p></td>
<td><p>Yes</p></td>
<td><p>A text value that specifies the publisher of the content element. Use the value that uniquely identifies the publisher.</p></td>
</tr>
<tr class="odd">
<td><p>Hide Publishers</p></td>
<td><p>suppressedPublishers</p></td>
<td><p>No</p></td>
<td><p>A semi-colon delimited list of publisher IDs. Use the Hide Publishers property to prevent the Help viewer from displaying conflicting or outdated information for a specified topic. The Help viewer hides the content elements from the specified publishers. However, the hidden content element is still available and can be accessed from the Help viewer.</p></td>
</tr>
<tr class="even">
<td><p>Topic Title</p></td>
<td><p>Title</p></td>
<td><p>Yes</p></td>
<td><p>A text value that specifies the title that appears in the title bar of the Help viewer.</p></td>
</tr>
<tr class="odd">
<td><p>Topic ID</p></td>
<td><p>Microsoft.Help.F1</p></td>
<td><p>Yes</p></td>
<td><p>A semi-colon delimited list of Topic IDs. Use the Topic ID field to associate the content element together with a class, form, or other object in the Microsoft Dynamics AX client. The Topic ID enables you to supply context-sensitive help information for the specified class, form, or other object. For more information about context-sensitive help, see <a href="context-sensitive-help.md">Context Sensitive Help</a>.</p></td>
</tr>
</tbody>
</table>


The following code example shows the metadata elements that you use to add the document properties to the HTML of a content element. You use the content attribute to specify the value for each property.

``` html
<meta name="Title" content="" />
<meta name="Microsoft.Help.Id" content="" />
<meta name="ms.locale" content="" />
<meta name="publisher" content="" />
<meta name="documentSets" content="UserDocumentation" />
<meta name="Microsoft.Help.Keywords" content="" />
<meta name="suppressedPublishers" content="" />
<meta name="Microsoft.Help.F1" content="" />
<meta name="description" content="" />
```

## Adding Links to Other Help Topics

A link is the text in a content element that you click to open another content element in the Help viewer. You add links to a content element when you want to provide access to related Help documentation. Typically, you add links that open other content elements on the Help server but you can link to documentation on other web sites.

**HTML**

To create a link, you add one of the following elements to your content element.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Element</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>&lt;a/&gt;</p></td>
<td><p>You use the href attribute to specify the content element that you want the link to open.</p>
<p>You can also use this element to open related Help documentation that is published outside the Help server. However, links to documentation that is located outside the Help server opens in a browser window and not the Help viewer.</p></td>
</tr>
<tr class="even">
<td><p>&lt;dynHelp:topicLink/&gt;</p></td>
<td><p>You use the topicID and documentSet attributes to specify the content element you want the link to open.</p>
<p>The link is active when you view the content element in the Help viewer. If you view the topic in an editor or browser, the link is not active.</p></td>
</tr>
</tbody>
</table>


To specify the content element that you want to appear when you click the link, you use the value of the Microsoft.Help.F1 document property of the targeted content element. For more information, see [How to: Add a Link to a Content Element](how-to-add-a-link-to-a-content-element.md).

**Word**

You use the **Hyperlink** button in the **Insert** tab of the Word ribbon to add a link. Use the **URL** to specify the file you want to open.


> [!WARNING]
> <P>When the Word template creates the .mht file, all the hyperlinks are converted to static link values. If you later deploy the topic to another server or folder on the server, the specified link might not work. For more information about using hyperlinks with .mht files, view the Help documentation for Word.</P>



## Using Labels in Help Documentation

If you create documentation that refers to individual controls on forms and other user interface (UI) components, you might want to use the text from those controls in your documentation. You typically use labels when you create documentation for forms that support more than one language. You can use labels to show the specified text in the same language that is displayed by the form. The language you see is specified by the **Language** field of the **User Options** form.


> [!WARNING]
> <P>To use labels, you have to use HTML to create the content element. The Help server performs label replacement with only .htm or .html files.</P>



When you use a label in your document, the Help server retrieves the label from the Application Object Server and inserts the text from that label into your documentation. For more information about how to use labels in documentation, see [How to: Add Labels, Fields, and Menu Items to a Content Element](how-to-add-labels-fields-and-menu-items-to-a-content-element.md).

## Using Images in Help Documentation

You can add images like screenshots or illustrations to your Help documentation. The images help the reader follow a lengthy procedure or better understand complex information. In addition, you can add more than one image to the content elements that you create.

To use an image, you have to place the image in a separate file. You then use the filename to import the image to the content element. When you publish the content element you might have to place the image files for that topic on the Help server.

For example, the Microsoft Dynamics AX Help documentation includes many images. The image files are found in Art and Local folders of the Microsoft content folder on the Help server. Typically, you find the Art folder for US-English Help in the following location:

    C:\inetpub\wwwroot\DynamicsAX6HelpServer\Content\Microsoft\EN-US\Art

You can use the images in the Microsoft Help documentation.


> [!WARNING]
> <P>The Microsoft Dynamics AX image files might change during a Help server update. To minimize the impact of an update on your custom documentation, you should copy the Microsoft Dynamics AX image files you want to use to a separate folder. For information about how to add a folder to the Help server, see <A href="how-to-add-folders-to-the-help-server.md">How to: Add Folders to the Help Server</A>.</P>



**HTML**

To add an image to a content element, you use the HTML \<img\> element. You then use the src attribute of that element to specify an image file. The file contains the image that you want to appear in the content element.

The following HTML example uses the \<img\> element to add an image. The src attribute specifies the image file. Notice how a relative path is used to specify the location of the file. When you publish your content element, the image file must also be published to the specified location. If the file is not in that location your image will not appear in the Help viewer. Also notice how the alt attribute specifies an alternative text description for the image.

``` html
<img alt=”Help system topology” src=”../Art/HelpSystem_Architecture2.png” />
```

**Word**

To add an image when you use the Word template, you use the **Illustrations** buttons in the **Insert** tab of the Word ribbon. If you use the template to create a .mht file, the specified image will be included in that file. When you publish the .mht file to the Help server, the image will appear when you view the topic in the Help viewer. You do not need to publish the image file to the Help server.

## Using Cascading Style Sheets in Help Documentation

To standardize the look of Microsoft Dynamics AX Help documentation, you use cascading style sheets (CSS) that specify fonts, colors, and layout for content elements that appear in the Help viewer. You use CSS when you want to have a common look and feel across many content elements. However, the use of CSS is optional. You are not required to use Microsoft Dynamics AX CSS or any other CSS when you create a new content element.

You can use CSS with the content elements that you create. For example, you might want to use the CSS that Microsoft Dynamics AX uses so that your content elements are similar to the existing Help documentation.


> [!IMPORTANT]
> <P>A content element that you create with the Word template does not use CSS. You have to use the style tools in Word to specify fonts, colors, and styles for each content element that you create.</P>



The Microsoft Dynamics AX CSS are in the AX.css and presentation.css files. Do not make changes to the Microsoft Dynamics AX CSS files. In addition, you should be aware that the contents of the CSS files might change during an update of the Help server. You can find the CSS files on the Help server in the following folder or a similar location:

    C:\inetpub\wwwroot\DynamicsAX6HelpServer\Content\Microsoft\EN-US\Local

To use CSS with a content element, you have to first add a \<link/\> element to your HTML. You then use the rel, type, and href attributes of the \<link/\> element to specify the type and location of the CSS file. The following code example shows the \<link/\> elements that specify the CSS files for a Microsoft Dynamics AX content element. Notice how the href attribute specifies the path from the location of the content element file to the location of the CSS file.

``` html
<link rel=”stylesheet” type=”text/css” href=”../local/presentation.css” />
<link rel=”stylesheet” type=”text/css” href=”../local/AX.css” />
```

You might have to change the href path to reflect the location where you publish the content element. The following example shows the path for a content element published to a new folder on the Help server named c:\\inetpub\\wwwroot\\DynamicsAX6HelpServer\\Content\\Contoso.

``` html
<link rel=”stylesheet” type=”text/css” href=”../Microsoft/EN-US/local/presentation.css” />
<link rel=”stylesheet” type=”text/css” href=”../Microsoft/EN-US/local/AX.css” />
```

To use CSS style rules with HTML elements, you use the id or class attributes of the element. You use the attribute to specify the style rule in the style sheet for the element. For example, you use the following to specify the style for the title of a content element. Notice how the value of the id element specifies the style for the title text:

``` html
<h1>
    <span id="nsrTitle">Title of the content element</span>
</h1>
```

The Help server includes a collection of HTML templates you can use to create new help topics. The templates include the most commonly used CSS styles from the Microsoft Dynamics AX Help documentation. To learn how to add CSS styles to new Help documentation, review the HTML source code from one of the templates.

To find the templates, use the Help viewer and search for **Templates for Help Documentation**. The specified topic includes a list of the available templates. If you use a template, you might have to update the href attribute of the link elements to reflect the location where you expect to publish the content element. For more information about the templates, see [Using Templates to Create Documentation](using-templates-to-create-documentation.md).

## Using Script Files in Help Documentation

A script file is a file that contains executable code that you can associate with one or more content elements. Typically, you use scripts to give you more control over how a content element appears or behaves in the Help viewer. The use of scripts is not required. You should only use scripts if you are comfortable using scripting languages with HTML.


> [!NOTE]
> <P>A content element that you create with the Word template does not use Help server script files.</P>



The Help server includes several JScript files. Each file contains a collection of functions that enable you to perform actions from the content element that appears in the Help viewer. When you install the Help server, the Microsoft Dynamics AX JScript files are placed in the following folder or a folder that you specified:

    C:\inetpub\wwwroot\DynamicsAX6HelpServer\Content\Microsoft\EN-US\Local

You can use a function from a Microsoft Dynamics AX JScript file in your content element. However, you should not edit or change any existing Microsoft Dynamics AX JScript file. A script error might make it difficult to view all Help documentation in the Help viewer. In addition, the contents of the Microsoft Dynamics AX script file can change in a future update. To insure that an update does not change the behavior of your documentation, you should copy any JScript files that you use to a separate folder on the Help server.

You can also create your own script files. You can use scripts to add unique functionality to the content elements that you create. To use the functions in a script file, you have to publish the file to a folder on the Help server.

To use a function, you first add a \<script\> element to the HTML of that content element. You use the script element to specify the file and where the file is found. The following code example adds a script element that references a Jscript file named script\_manifold.js. Notice how the src attribute specifies the location of the Jscript file. The file path indicates the script file is located in a folder named local that is next to the folder where the content element is published.

``` html
<script type="text/javascript" src="../local/script_manifold.js"></script>
```

After you add the reference to the file, you can associate a function in that file with a user initiated event in the content element. For example, the following HTML span element associates the ExpandCollapse function with the onclick event for a section heading.

``` html
<span onclick="ExpandCollapse(sectionToggle0)" style="cursor:default;" tabindex="0">
```

When you click the section heading, the section will disappear from view and when you click the section heading again, the section reappears in the Help viewer. For more information about collapsing and expanding sections, see [How to: Add a Collapsible and Expandable Section](how-to-add-a-collapsible-and-expandable-section.md).

## See also

[Using Templates to Create Documentation](using-templates-to-create-documentation.md)

[How to: Create a Help Document using a Template](how-to-create-a-help-document-using-a-template.md)

[Walkthrough: Creating Help Documentation](walkthrough-creating-help-documentation.md)

[How to: Create a Non-HTML Content Element](how-to-create-a-non-html-content-element.md)

[How to: Create Table of Contents Entries](how-to-create-table-of-contents-entries.md)

[Document Property Metadata Reference](document-property-metadata-reference.md)

[Publishing Documentation to the Help System](publishing-documentation-to-the-help-system.md)

