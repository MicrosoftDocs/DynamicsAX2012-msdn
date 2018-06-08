---
title: 'Walkthrough: Creating Help Documentation'
TOCTitle: 'Walkthrough: Creating Help Documentation'
ms:assetid: 24041ed1-c9d3-45b6-afb2-a64d24775902
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg882314(v=AX.60)
ms:contentKeyID: 35257143
ms.date: 11/07/2012
mtps_version: v=AX.60
dev_langs:
- html
---

# Walkthrough: Creating Help Documentation 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The Microsoft Dynamics AX Help system enables you to create documentation you can add to the Help server. In this walkthrough, you create a content element for the Customers form that supplements the existing Help documentation for that form.

This walkthrough illustrates the following tasks:

  - How to create an HTML document.

  - How to add required sections and other HTML elements that the Help viewer uses to display the document in the Help viewer.

  - How to use stylesheets to make the document resemble existing Help documentation.

  - How to add labels from the client user interface to your document.

  - How to add a table that lists and describes important concepts.

  - How to add links to other Help documentation.

  - How to save the document to a file that you can publish to the Help server.

## Prerequisites

To complete this walkthrough you have to have the following on your computer:

  - You have to have an HTML or text editor like Microsoft Visual Studio 2008 or a later version. The steps that follow use Visual Studio to create the HTML Help document. However, you can use other HTML or text editors that can produce an .htm or .html file.

  - Access to the Microsoft Dynamics AX Help server

## Creating a Content Element

This section of the documentation describes how to create the file and the HTML document you use for the content element. When you complete this section, you have a basic HTML document.

### To Create the File

1.  Start Visual Studio 2008, click the **File** menu, and then click **New File**. The **New File** window opens.

2.  In the **New File** window, find the **Categories** list, and then click **General**. Review the list of **Visual Studio installed templates**, click **Text File**, and then click **Open**. A new text document opens in the editor window.

### To Create the HTML Document

1.  Add a DOCTYPE element and specify the document type definition. The following table shows the document type declarations you use for an HTML document that appears in the Help viewer.
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Name</p></th>
    <th><p>Value</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>TopElement</p></td>
    <td><p>html</p></td>
    </tr>
    <tr class="even">
    <td><p>Availability</p></td>
    <td><p>PUBLIC</p></td>
    </tr>
    <tr class="odd">
    <td><p>Document type definition</p></td>
    <td><p>-//W3C//DTD XHTML 1.0 Transitional//EN</p></td>
    </tr>
    <tr class="even">
    <td><p>URL</p></td>
    <td><p>http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd</p></td>
    </tr>
    </tbody>
    </table>
    
    The following code example adds the DOCTYPE and the required document type declarations.
    
    ``` html
    <!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd"[]>
    ```

2.  Add an html element, add the dir attribute, and set the attribute value to ltr (left-to-right). While dir is not required, the Help viewer uses the specified value to optimize the appearance of that document. The following example adds the html element and dirto the document.
    
    ``` html
    <!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd"[]>
    <html dir="ltr">
       
    </html>
    ```

3.  Add namespaces to the html element. To add a namespace, use xmlns, the name, and the URL or URN for that namespace. To provide definitions for custom elements, add the following namespaces.
    

    > [!WARNING]
    > <P>If you do not include each namespace, your document might not appear in the Help viewer.</P>

    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Namespace</p></th>
    <th><p>URL/URN</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>xmlns:xlink</p></td>
    <td><p>http://www.w3.org/1999/xlink</p></td>
    </tr>
    <tr class="even">
    <td><p>xmlns:dynHelp</p></td>
    <td><p>http://schemas.microsoft.com/dynamicsHelp/2008/11</p></td>
    </tr>
    <tr class="odd">
    <td><p>xmlns:dynHelpAx</p></td>
    <td><p>http://schemas.microsoft.com/dynamicsHelpAx/2008/11</p></td>
    </tr>
    <tr class="even">
    <td><p>xmlns:MSHelp</p></td>
    <td><p>http://msdn.microsoft.com/mshelp</p></td>
    </tr>
    <tr class="odd">
    <td><p>xmlns:mshelp</p></td>
    <td><p>http://msdn.microsoft.com/mshelp</p></td>
    </tr>
    <tr class="even">
    <td><p>xmlns:ddue</p></td>
    <td><p>http://ddue.schemas.microsoft.com/authoring/2003/5</p></td>
    </tr>
    <tr class="odd">
    <td><p>xmlns:msxsl</p></td>
    <td><p>urn:schemas-microsoft-com:xslt</p></td>
    </tr>
    </tbody>
    </table>
    
    The following example shows the HTML for the namespaces that are used in the document.
    
    ``` html
    <html DIR="LTR" xmlns:xlink="http://www.w3.org/1999/xlink" xmlns:dynHelp="http://schemas.microsoft.com/dynamicsHelp/2008/11" xmlns:dynHelpAx="http://schemas.microsoft.com/dynamicsHelpAx/2008/11" xmlns:MSHelp="http://msdn.microsoft.com/mshelp" xmlns:mshelp="http://msdn.microsoft.com/mshelp" xmlns:ddue="http://ddue.schemas.microsoft.com/authoring/2003/5" xmlns:msxsl="urn:schemas-microsoft-com:xslt">
    ```

4.  Add the HTML head and body elements to the document. The following example shows the HTML for the document.
    
    ``` html
    <!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Transitional//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-transitional.dtd"[]>
    <html DIR="LTR" xmlns:xlink="http://www.w3.org/1999/xlink" xmlns:dynHelp="http://schemas.microsoft.com/dynamicsHelp/2008/11" xmlns:dynHelpAx="http://schemas.microsoft.com/dynamicsHelpAx/2008/11" xmlns:MSHelp="http://msdn.microsoft.com/mshelp" xmlns:mshelp="http://msdn.microsoft.com/mshelp" xmlns:ddue="http://ddue.schemas.microsoft.com/authoring/2003/5" xmlns:msxsl="urn:schemas-microsoft-com:xslt">
       <head>
       </head>
          
       <body>
       </body>
    </html>
    ```

## Populating the Document Head

This section adds elements to the head section of the HTML document. The document head contains information that the document uses but does not appear in the Help viewer. The following sections add elements between the open and close tags of the head element that you added earlier.

### To Add the Required Elements

1.  Add a meta element and set the http-equiv attribute to **Content-Type**. Set the content attribute to **text/html; charset=UTF-8**.
    
    Add a meta element and set name to **save**. Set the content attribute to **history**.
    
    The following example adds the meta elements. Notice how the first meta element specifies the document type. Also notice how the second meta element specifies that the document be saved to the session memory of the browser.
    
    ``` html
    <meta http-equiv="Content-Type" content="text/html; charset=UTF-8" />
    <meta name="save" content="history" />
    ```

2.  Add a title element and enter **Contoso customer help information**. This text appears in the title bar of the Help viewer. The following HTML example adds the header title.
    
    ``` html
    <title>Contoso customer help information</title>
    ```

3.  Add three link elements. Use the link elements to specify the stylesheets you want to apply to your document. Add a rel attribute to each link element and set the value of the attribute to stylesheet. Add a type attribute to each link element and set the value of the attribute to text/css. Add a href attribute to each link element and use the following table to specify the value of each href attribute.
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Stylesheet</p></th>
    <th><p>Description</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>AX.css</p></td>
    <td><p>Enter ../../Microsoft/EN-US /local/AX.css.</p>
    <p>Specify a file path from the folder on the Help server where you will publish this document to the folder that contains the AX.css file. By default, the file is installed to the following folder of the Help server:</p>
    <p>c:/inetpub/wwwroot/&lt;HelpServerName&gt;/content/Microsoft/EN-US/local</p></td>
    </tr>
    <tr class="even">
    <td><p>presentation.css</p></td>
    <td><p>Enter ../../Microsoft/EN-US /local/presentation.css.</p>
    <p>Specify a file path from the folder on the Help server where you will publish this document to the folder that contains the presentation.css file. By default, the file is installed to the following folder of the Help server:</p>
    <p>c:/inetpub/wwwroot/&lt;HelpServerName&gt;/content/Microsoft/EN-US/local</p></td>
    </tr>
    <tr class="odd">
    <td><p>HxLink.css</p></td>
    <td><p>Enter ms-help://Hx/HxRuntime/HxLink.css.</p>
    <p>Specify the URL of the of the HxLink.css file.</p></td>
    </tr>
    </tbody>
    </table>
    
    The following HTML example adds link elements for the required stylesheets. Notice how the href attributes specify a relative path of the folder that contains the .css files. The code example assumes this content element is published to folders on the Help server that represent the publisher name and the language of the documentation. You might have a different path to the stylesheet files. Also notice how the third link element specifies a URL for the HxLink.css file.
    
    ``` html
    <link rel="stylesheet" type="text/css" href="../../Microsoft/EN-US /local/presentation.css" />
    <link rel="stylesheet" type="text/css" href="../../Microsoft/EN-US /local/AX.css" /> 
    <link rel="stylesheet" type="text/css" href="ms-help://Hx/HxRuntime/HxLink.css" />
    ```

4.  Add nine meta elements. Use the meta elements to provide the document properties that are required by the Help server. Add a name and content attribute to each element. Populate the name and content attribute of each element that has values from the following table.
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Name</p></th>
    <th><p>Content</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Title</p></td>
    <td><p>Contoso customer help information</p></td>
    </tr>
    <tr class="even">
    <td><p>Microsoft.Help.Id</p></td>
    <td><p>Contoso.Forms.CustTable</p></td>
    </tr>
    <tr class="odd">
    <td><p>ms.locale</p></td>
    <td><p>EN-US</p></td>
    </tr>
    <tr class="even">
    <td><p>publisher</p></td>
    <td><p>Contoso</p></td>
    </tr>
    <tr class="odd">
    <td><p>documentSets</p></td>
    <td><p>UserDocumentation</p></td>
    </tr>
    <tr class="even">
    <td><p>Microsoft.Help.Keywords</p></td>
    <td><p>Contoso; customer</p></td>
    </tr>
    <tr class="odd">
    <td><p>suppressedPublishers</p></td>
    <td><p>Leave the content element empty.</p></td>
    </tr>
    <tr class="even">
    <td><p>Microsoft.Help.F1</p></td>
    <td><p>Forms.CustTable</p></td>
    </tr>
    <tr class="odd">
    <td><p>description</p></td>
    <td><p>Describes Contoso customizations to the Customers form.</p></td>
    </tr>
    </tbody>
    </table>
    
    The following HTML example adds a meta element for each document property. Notice how the name and content attributes are populated to specify the document property and give a value for that property.
    
    ``` html
    <meta name="Title" content="Contoso customer help information" />
    <meta name="Microsoft.Help.Id" content="Contoso.Forms.CustTable" />
    <meta name="ms.locale" content="EN-US" />
    <meta name="publisher" content="Contoso" />
    <meta name="documentSets" content="UserDocumentation" />
    <meta name="Microsoft.Help.Keywords" content="Contoso; customer" />
    <meta name="suppressedPublishers" content="" />
    <meta name="Microsoft.Help.F1" content="Forms.CustTable" />
    <meta name="description" content="Describes Contoso customization to the Customers form" />
    ```

## Populating the Document Body

This section adds elements to the body section of the HTML document. The document body contains the documentation that appears in the Help viewer. The steps in the following sections add elements between the open and close tag of the body element that you added earlier.

### To Add Controls

  - Add input elements for two hidden controls. Add a type, id, and class attribute to each element. To populate the attributes, use the following values.
    
    <table>
    <colgroup>
    <col style="width: 33%" />
    <col style="width: 33%" />
    <col style="width: 33%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>type</p></th>
    <th><p>id</p></th>
    <th><p>class</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>hidden</p></td>
    <td><p>hiddenScrollOffset</p></td>
    <td><p>N/A</p>
    <p>This control does not require a class attribute.</p></td>
    </tr>
    <tr class="even">
    <td><p>hidden</p></td>
    <td><p>userDataCache</p></td>
    <td><p>userDataStyle</p></td>
    </tr>
    </tbody>
    </table>
    
    The following HTML example adds the input elements. Notice how the type attribute specifies that the controls are not visible, and the id attribute specifies the control name. Also notice how the class attribute of the userDataCache control is set to userDataStyle.
    
    ``` html
    <input type="hidden" id="userDataCache" class="userDataStyle" />
    <input type="hidden" id="hiddenScrollOffset" />
    ```

### To Add the Document Title

1.  Add a div element and set the id attribute to header. The following HTML example adds the div element.
    
    ``` html
    <div id="header">
       
    </div>
    ```

2.  Add a span element to the header section. Set the id attribute of the element to **runningHeaderText**.

3.  Add another span element to the header section. Set the id attribute of the element to **nsrTitle**. To specify the title that appears in the Help viewer, enter Contoso customer help information.

4.  Add an hr element to the header section. To keep the title visible during scrolling, set the class attribute to **title-divider**.
    
    The following example shows the HTML for the header section. Notice the use of the br element to add an empty line above the title.
    
    ``` html
    <div id="header">
       <br />
       <span id="runningHeaderText"> </span>
       <span id="nsrTitle">Contoso customer help information</span>
       
       <hr class="title-divider" />
    </div>
    ```

### To Add the MainSection

1.  Add a div element and set the id to mainSection.

2.  Add a div element between the open and close tags of the mainSection. Set the id to mainBody.

3.  Add another div element and set the id to footer. The following example shows the HTML for the mainSection.
    
    ``` html
    <div id="mainSection">
       <div id="mainBody">
          
       </div>
       
       <div id="footer">
          
       </div>
    </div>
    ```

## Populating the MainBody of the Document

To add the documentation that appears in the help viewer, you add to the mainBody section of the HTML document. All the elements in the following steps are added between the open and close tag of the mainBody. The following sections add an introduction, a description of a customization, and a list of links to related topics.

### To Add the Introduction

1.  Add a div element between the open and close tags of the mainBody section. Set the class attribute to **introduction**.

2.  Add two p (paragraph) elements and enter the text for each paragraph. The following example shows the HTML for the introduction.
    
    ``` html
    <div class="introduction">
       <p>
          This topic includes information about changes to the Customer form that have been added by Contoso.
       </p>
       <p>
          You can use the Customer form to view additional information about each of your customers.
       </p>
    </div>
    ```

### To Add the Help Documentation

1.  To create a section heading, add an h1 element and set the class attribute of the element to **heading**. Enter **Contoso customer information** between the open and close tags of the h1 element.

2.  Add a div element and set the class attribute to **section**.

3.  Add a p element between the open and close tag of the div element. Enter the text that introduces this section of the document.
    
    The following example shows the HTML for the section heading and the opening paragraph.
    
    ``` html
    <h1 class="heading"></h1>
    <div class="section">
       <p>
          The Contoso customer add-ons enable you to view important information about your relationship with your customer. To view the additional information, click one of the following buttons:
       </p>
    </div>
    ```

### To Add Labels from the Buttons

1.  To list the buttons, add a ul element, add two li elements to the ul element, and then add a p element to each li element. The following example adds the HTML framework for a bulleted list.
    
        <ul>
           <li>
              <p> </p>
           </li>
           <li>
              <p> </p>
           </li>
        </ul>

2.  Add text to each p element that describes a button. The following example adds information about two buttons.
    
    ``` html
    <ul>
       <li>
          <p>Click the Customer button to create a new customer record. </p>
       </li>
       <li>
          <p>Click the Edit button to update an existing customer record. </p>
       </li>
    </ul>
    ```

3.  Use the dynHelpAx:label element to replace the Customer and Edit button names with the labels from the controls. Populate the following attributes of the label element by using the specified values.
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Attribute</p></th>
    <th><p>Value</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>axtype</p></td>
    <td><p>Label</p></td>
    </tr>
    <tr class="even">
    <td><p>id</p></td>
    <td><p>Enter @SYS316442 for the first label.</p>
    <p>Enter @SYS453 for the second label.</p></td>
    </tr>
    </tbody>
    </table>
    
    The following HTML example adds labels for two buttons. Notice how each label specifies a default text value.
    
    ``` html
    <ul>
       <li>
          <p>Click the <dynHelpAx:label axtype="Label" id="@SYS316442">Customer</dynHelpAx:label> button to create a new customer record. </p>
       </li>
       <li>
          <p>Click the <dynHelpAx:label axtype="Label" id="@SYS453">Edit</dynHelpAx:label> button to update an existing customer record. </p>
       </li>
    </ul>
    ```

### To Add a Table

1.  Add a p element and enter text that describes the table. The following example shows the HTML you use to introduce the table.
    
    ``` html
    <p>The following table provides additional information about how to use Contoso customer information: </p>
    ```

2.  Add a div element and set the class attribute to **caption**.

3.  Add a div element and set the class attribute to **tableSection**.

4.  To create the table and column headings, add a table element, add a tr element, and then add two th elements. Set the colspan attribute of each th element to 1. Add a p element to each th column. Enter **Name** for the first column heading and **Description** for the second column heading. The following examples shows the HTML for the table.
    
    ``` html
    <div class="caption"></div>
    <div class="tableSection">
       <table>
          <tr>
             <th colspan="1">
                <p>Name </p>
             </th>
             <th colspan="1">
                <p>Description </p>
             </th>
          </tr>
       </table>

    </div>
    ```

5.  To add rows to the table, add two tr elements and then add two td elements to each row. Set the colspan attribute of each td element to 1.

6.  Add a p element to each td element. Use the following table to enter values for the name and description of each entry in the table.
    
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
    <td><p>Customer</p></td>
    <td><p>Create a new record that represents a person or organization.</p></td>
    </tr>
    <tr class="even">
    <td><p>Edit</p></td>
    <td><p>Perform updates to existing customer records.</p></td>
    </tr>
    </tbody>
    </table>
    
    The following example shows the HTML for the complete table.
    
    ``` html
    <table>
       <tr>
          <th colspan="1">
             <p>Name </p>
          </th>
          <th colspan="1">
             <p>Description </p>
          </th>
       </tr>
       <tr>
          <td colspan="1">
             <p>Customer </p>
          </td>
          <td colspan="1">
             <p>Create a new record that represents a person or organization. </p>
          </td>
       </tr>
       <tr>
          <td colspan="1">
             <p>Edit </p>
          </td>
          <td colspan="1">
             <p>Perform updates to existing customer records. </p>
          </td>
       </tr>
    </table>

    ```

### To Add Links to Related Topics

1.  To create a section heading, add an h1 element, and then set the class attribute to heading. Enter **See also** between the open and close tags of the h1 element.

2.  Add a div element and set the class attribute to **section**.

3.  Between the open and close tags of the div element, add another div element. Set the class attribute to **seeAlsoStyle**.

4.  Between the open and close tags of the seeAlsoStyle section, add a span element.

5.  Between the open and close tags of the span element, add a dynHelp:topicLink element. Enter **Create a customer account** as the text for the link. Populate the following attributes of the dynHelp:topicLink element by using the specified values.
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Attribute</p></th>
    <th><p>Value</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>topicId</p></td>
    <td><p>cc18943e-c00c-49e6-8bd2-03be6481b6dd</p></td>
    </tr>
    <tr class="even">
    <td><p>documentSet</p></td>
    <td><p>UserDocumentation</p></td>
    </tr>
    </tbody>
    </table>
    
    The following example shows the HTML for the See also section. Notice how the section includes a link to a related topic.
    
    ``` html
    <h1 class="heading">See also</h1>
    <div class="section">
       <div class="seeAlsoStyle">
          <span>
             <dynHelp:topicLink topicId="cc18943e-c00c-49e6-8bd2-03be6481b6dd" documentSet="UserDocumentation">Create a customer account</dynHelp:topicLink>
          </span>
       </div>
    </div>
    ```

## Populating the Footer Section

To match existing Help documents, you should include a line at the end of the document. The following documentation describes how to add a line to the footer section that you added earlier.

### To Add a Line

1.  Find the div element that has the id attribute of footer. Add a div element between the tags for the footer section. Set the class attribute to **footerline**.

2.  Add an hr element between the tags of the footerline section. Add the style attribute and set the following properties of the attribute by using the specified values.
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Property name</p></th>
    <th><p>Value</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>height</p></td>
    <td><p>2px</p></td>
    </tr>
    <tr class="even">
    <td><p>color</p></td>
    <td><p>Silver</p></td>
    </tr>
    </tbody>
    </table>
    
    The following example shows the HTML that adds a line to the footer.
    
    ``` html
    <div id="footer">
       <div class="footerLine">
          <hr style="height:2px; color:Silver" />
       </div>
       <p />
    </div>
    ```

## Saving the Document

After you complete the document, you have to save the document to an .htm or .html file. The following steps show how to use Visual Studio to save the document to an .htm file. If you use a different HTML or text editor, the steps to save the document to a file will be different.

### To Save to a File

1.  In the menu bar, click File, and then click Save As. The Save File As window opens.

2.  In the File name box, verify the folder that is used to save the file, and then enter **ContosoCustomerDoc.htm**. This specifies the name of the file.

3.  Verify that the Save as type box shows HTML Files (\*.htm; \*.html). If another file type is specified, click the arrow to open the drop down list and select the correct file type.

4.  Click the Save button. The file is added to the specified folder.

## Next Steps

After you save the document to a file, you can publish that file to the Help server. To view your document in the Help viewer, you have to publish the document file. For more information about how to publish, see [How to: Publish a Help Document](how-to-publish-a-help-document.md).

## See also

[Authoring Help Documents](authoring-help-documents.md)

[Using Templates to Create Documentation](using-templates-to-create-documentation.md)

[Publishing Overview](publishing-overview.md)

[Document Property Metadata Reference](document-property-metadata-reference.md)

