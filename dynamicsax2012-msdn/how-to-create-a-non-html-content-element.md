---
title: 'How to: Create a Non-HTML Content Element'
TOCTitle: 'How to: Create a Non-HTML Content Element'
ms:assetid: 3eea50c9-b006-4b76-abb3-6e136a332e75
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg882338(v=AX.60)
ms:contentKeyID: 35257165
ms.date: 11/07/2012
mtps_version: v=AX.60
dev_langs:
- html
---

# How to: Create a Non-HTML Content Element [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

This topic describes how to create a non-HTML document that you can publish to the Microsoft Dynamics AX Help server. While the help viewer cannot display a non-HTML file, the viewer can open another application that can display the document. For example, you might use Microsoft Office Word to view Help documentation in a .docx file.

To use a non-HTML document together with the help viewer, you must have the following components:

  - To publish a non-HTML file on the help server, you must include an HTML file that contains the help system metadata properties and a script that targets the non-HTML file. The HTML file must have the same name as the content element file. In addition, both files must be published to the same folder on the help server.

  - To view your non-HTML content element, the computer on which the help viewer is installed must have an application that can display that type of file. In addition, that application must be the default viewer for that type of file. If there is no viewer application associated with the specified file type, the file will not open.

The following steps show you how to create a non-HTML content element and the required HTML metadata file.

### To create the content element

1.  Open the application that creates and displays the non-HTML content and create a new file. For example, open Microsoft Office Word and create a new document.
    

    > [!TIP]
    > <P>If you use Microsoft Office Word for a content element, consider using one of the templates included with the help system. The templates help you quickly create a content element that resembles existing Help documentation.</P>



2.  Use the application to add Help documentation to the file. To create a typical content element, add a title, section headings, and paragraphs.

3.  Save the file. Note the file name. You will use this file name when you create the HTML file that provides the metadata for your new content element. To continue the Microsoft Office Word example, save the file as SampleContentElement.docx.

### To create the HTML metadata file

1.  Use a text or HTML editor to create a new file.

2.  Add the HTML for a basic webpage. The following HTML example creates a basic webpage.
    
    ``` html
    <html>
       <head>
       
       </head>
    </html>
    ```

3.  Add an HTML \<meta\> element to the file for the following metadata properties.
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Property</p></th>
    <th><p>Required</p></th>
    <th><p>Description</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>description</p></td>
    <td><p>No</p></td>
    <td><p>Specify the brief summary of the content element that appears in a list of search results.</p></td>
    </tr>
    <tr class="even">
    <td><p>documentSets</p></td>
    <td><p>Yes</p></td>
    <td><p>Specify the ID of the document set by setting this property to UserDocumentation.</p></td>
    </tr>
    <tr class="odd">
    <td><p>Microsoft.Help.F1</p></td>
    <td><p>Yes</p></td>
    <td><p>Specify a topic ID for the content element. If the content element applies to more than one topic, use a semicolon delimited list to specify the ID of each topic.</p></td>
    </tr>
    <tr class="even">
    <td><p>Microsoft.Help.Id</p></td>
    <td><p>Yes</p></td>
    <td><p>Specify a text value that uniquely identifies the content element.</p></td>
    </tr>
    <tr class="odd">
    <td><p>Microsoft.Help.Keywords</p></td>
    <td><p>No</p></td>
    <td><p>Specify a semicolon delimited collection of keyword entries. Search keywords are optional and the property can be empty.</p></td>
    </tr>
    <tr class="even">
    <td><p>ms.locale</p></td>
    <td><p>Yes</p></td>
    <td><p>Specify the language for the content element. For example, use EN-US to specify that the content element contains United States English.</p></td>
    </tr>
    <tr class="odd">
    <td><p>publisher</p></td>
    <td><p>Yes</p></td>
    <td><p>Specify your publisher ID.</p></td>
    </tr>
    <tr class="even">
    <td><p>suppressedPublishers</p></td>
    <td><p>No</p></td>
    <td><p>Specify a semicolon delimited list of publisher IDs. Hiding content elements produced by other publishers is optional and the property can be empty.</p></td>
    </tr>
    <tr class="odd">
    <td><p>Title</p></td>
    <td><p>Yes</p></td>
    <td><p>Specify the text that displays in the title bar of the help viewer.</p></td>
    </tr>
    </tbody>
    </table>
    
    The following example shows the metadata properties for a sample content element:
    
    ``` html
    <head>
       <meta name="Title" content="Sample content element" />
       <meta name="Microsoft.Help.Id" content="8D937F19-3A00-4F37-A316-0A48D052D627" />
       <meta name="ms.locale" content="En-Us" />
       <meta name="publisher" content="Microsoft" />
       <meta name="documentSets" content="UserDocumentation" />
       <meta name="Microsoft.Help.Keywords" content="" />
       <meta name="suppressedPublishers" content="" />
       <meta name="Microsoft.Help.F1" content="SampleContentElement" />
       <meta name="description" content="An example of a non-HTML content element that was published to the Help system." />
    </head>
    ```

4.  Add a script element and specify the file that you want to open. Specify the script type as javascript and use the window.location object to specify the file. The following HTML example shows a script element that opens the file that is named SampleContentElement.docx.
    
    ``` html
    <script type="text/javascript">
       <!-- 
          window.location="SampleContentElement.docx" 
       //-->
    </script>
    ```

5.  Save the file. The file name must match your content element file. The file name extension must be .htm. For example, use SampleContentElement.htm to match the SampleContentElement.docx example from the previous step.

## Example

The following HTML example shows the contents of an HTML file. Notice how the \<meta\> elements provide the metadata properties and the \<script\> element specifies the file that contains the content element.

``` html
<html>
   <head>
      <meta name="Title" content="Sample content element" />
      <meta name="Microsoft.Help.Id" content="8D937F19-3A00-4F37-A316-0A48D052D627" />
      <meta name="ms.locale" content="EN-US" />
      <meta name="publisher" content="Microsoft" />
      <meta name="documentSets" content="UserDocumentation" />
      <meta name="Microsoft.Help.Keywords" content="" />
      <meta name="suppressedPublishers" content="" />
      <meta name="Microsoft.Help.F1" content="SampleContentElement" />
      <meta name="description" content="An example of a non-HTML content element that was published to the Help system." />

      <script type="text/javascript">
         <!-- 
            window.location=" SampleContentElement.docx" 
         //-->
      </script>

   </head>
</html>
```

## See also

[How to: Create a Help Document using a Template](how-to-create-a-help-document-using-a-template.md)

[How to: Publish a Help Document](how-to-publish-a-help-document.md)

[Document Property Metadata Reference](document-property-metadata-reference.md)

