---
title: 'Walkthrough: Updating Existing Help Documentation'
TOCTitle: 'Walkthrough: Updating Existing Help Documentation'
ms:assetid: fd9d8c13-1686-47c5-9dc2-a317c7741393
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ677317(v=AX.60)
ms:contentKeyID: 49384088
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# Walkthrough: Updating Existing Help Documentation [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2_

This topic describes how you update a content element that was originally created by another publisher. A content element is a file that contains Help documentation for a specified topic. You might update a content element after you customize an existing Microsoft Dynamics AX form so that the Help documentation reflects the changes that you made to the form. You can then have the Help viewer show your updated content element when you request help for the form.

To show how you update an existing content element, the following walkthrough modifies the Help documentation for the **Customers** form. In the steps that follow, you will learn to find a content element, modify the documentation, and then publish the updated content element to the Help server. To complete the walkthrough, you perform the following tasks:

  - You use the Help viewer to find the content element that you want to update.

  - You create an HTML file that contains the existing Help documentation.

  - You update the Help documentation by adding new content to the HTML file.

  - You update the values for the document properties of the content element.

  - You hide the existing Microsoft Help documentation for the form.

  - You make CSS, image, and script files available to your updated content element.

  - You publish your content element to the Help server.

  - You view the modified content element in the Help viewer.

## Prerequisites

To complete this walkthrough, you have to have the following:

  - The Microsoft Dynamics AX client and Help viewer installed.

  - A text editor like Notepad.exe you can use to view the source code of the documentation that appears in the Help viewer.

  - An HTML editor you can use to modify the contents of an HTML file. The walkthrough uses Visual Studio but you can use another HTML editor.

  - You must log-in with an account that has permissions to add folders and files to the Help server file system. You might need a system administrator to give you access to the Help server file system.

## Creating a Copy of the Content Element

This section describes how to find a content element and how to copy the HTML from that content element to a file. The steps that follow create a copy of the Microsoft Dynamics AX Help documentation for the Customers form. For more information about content elements, see [Customizing the Help System](customizing-the-help-system.md).

### To find the documentation for the Customers form

1.  Open the Microsoft Dynamics AX client workspace. In the Navigation Pane, click **Accounts Receivable**, click **Common**, click **Customers**, and then click **All customers**. The list page opens in the client.
    
    The following illustration shows **All customers** in the Navigation Pane.
    
    ![Find All customers in the Navigation Pane](images/JJ677317.HelpSystem_AllCustomersForm(AX.60).png "Find All customers in the Navigation Pane")

2.  Double-click a customer record that appears in the **All customers** list. The **Customers** form opens in a separate window.

3.  To get the Help documentation for the form, click the **Customers** window, and then press **F1**. The Help viewer appears and shows the **Customers (form)** Help documentation.
    
    The following illustration shows the **Customers (form)** Help documentation in the Help viewer.
    
    ![View the Customers (form) Help documentation](images/JJ677317.HelpSystem_CustomersFormHelp(AX.60).png "View the Customers (form) Help documentation")

### To copy documentation from the Help viewer to a file

1.  Right-click **Customers (form)** in the Help viewer, and then click **View source** in the menu. The content element opens in a text editor and shows the HTML source code for that content element.
    
    Typically, the source code appears in Notepad.exe. If you have associated another text editor with file types of .htm or .html, you might see a different text editor. You can use that text editor to complete the remaining steps.

2.  In Notepad, click the **File** menu, and then click **Save As**. The **Save As** window opens. Enter the following values in the fields of the **Save As** window.
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Field</p></th>
    <th><p>Value</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Location</p></td>
    <td><p>Click <strong>Desktop</strong>.</p>
    <p>You can specify another location. You should put the file in a location where you can later find and modify the contents of the file.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>File name:</strong></p></td>
    <td><p>Enter <strong>ContosoCustomerFormUpdate.htm</strong>.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Save as type:</strong></p></td>
    <td><p>Click <strong>All Files (*.*)</strong>.</p></td>
    </tr>
    </tbody>
    </table>
    
    The following illustration shows the **Save As** window for Notepad.
    
    ![Save the HTML to a file](images/JJ677317.HelpSystem_ViewSource(AX.60).png "Save the HTML to a file")

3.  Click **Save**. The ContosoCustomerFormUpdate.htm file appears on your desktop. You can close Notepad and the Help viewer.

## Updating the Customers (form) Help documentation

This section describes how to add documentation to the copy of the **Customers (form)** content element that you created earlier. The following steps use Visual Studio to update the HTML file that contains the Help documentation for the **Customers (form)**. However, you can use another HTML editor to follow these steps.

### To open the ContosoCustomerFormUpdate.htm file in an HTML editor

1.  Start Visual Studio, click **File** in the menu bar, click **Open**, and then click **File**. In the **Open File** window, move to the **Desktop**, click ContosoCustomerFormUpdate.htm, and then click **Open**. The file appears in the editor.

2.  At the bottom of the editor, click the **Design** button. The Design view shows the content that will appear in the Help viewer.
    
    The following illustration shows the content element in the Design view of Visual Studio. Notice that the images, styles, and scripts are missing. The missing components use file references that bring in information from specified files. The missing components will be restored when you publish the content element.
    
    ![Update the content in the file](images/JJ677317.HelpSystem_Edit(AX.60).png "Update the content in the file")

### To update the documentation for the Customers form

1.  Click the line that contains Customers (form). Move the pointer to the start of the line and then type the following text:
    
        Contoso

2.  Click the paragraph that contains the text Use this form to create and maintain your organization’s customer records. Move the pointer to the end of the paragraph and add the following text:
    
        This is the Contoso customized version of the Customers (form) Help documentation.
    
    The following illustration shows the updated content element.
    
    ![Customize the content in the Help documentation](images/JJ677317.HelpSystem_(AX.60).png "Customize the content in the Help documentation")

3.  Click **Save**.

## Updating the Document Properties of the Content Element

This section describes how to update the document properties for a content element. A document property is a metadata element that enables the Help server to match a content element to a request from the Help viewer. For more information about document properties, see [Authoring Help Documents](authoring-help-documents.md).

### To specify new values for the document properties

1.  At the bottom of the editor, click the **Source** button. The Source view shows the HTML code from the ContosoCustomerFormUpdate.htm file.

2.  Press Ctrl + F. The **Find and Replace** window opens.

3.  In the **Find what:** text box, type meta name=”Title”, in the **Look in:** text box click **Current Document**, and then click **Find Next**. The pointer moves to the location of the first document property.
    
    After you locate the document properties, close the **Find and Replace** window.

4.  You will find the document properties as a series of HTML \<meta\> elements. You have to update the value of the content attribute for each document property.
    
    The following table specifies the document properties and the value that you use to populate the content attribute of each document property.
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Property name</p></th>
    <th><p>Content value</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Title</p></td>
    <td><p>Contoso Customers (form)</p></td>
    </tr>
    <tr class="even">
    <td><p>Microsoft.Help.Id</p></td>
    <td><p>Enter a GUID value.</p>
    <p>In Visual Studio, click <strong>Tools</strong>, click <strong>Create GUID</strong>, and then click <strong>Copy</strong>. To replace the existing ID, highlight the value, and then click <strong>Paste</strong>. The content attribute now has the new GUID value. If the GUID include braces, make sure that you remove them. To close the <strong>Create GUID</strong> window, click <strong>Exit</strong>.</p></td>
    </tr>
    <tr class="odd">
    <td><p>Ms.locale</p></td>
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
    <td><p>Add Contoso to the existing keyword list: Customer; Customers; Contoso. Use a semicolon to separate the entries in the list.</p></td>
    </tr>
    <tr class="odd">
    <td><p>suppressedPublishers</p></td>
    <td><p>Microsoft</p>
    <p>You use this property to specify the ID of a publisher. Content elements from the specified publisher are at first hidden in the Help viewer. As a result, pressing <strong>F1</strong> from the <strong>Customers</strong> form will return this customized version of the <strong>Customers (form)</strong> Help documentation.</p></td>
    </tr>
    <tr class="even">
    <td><p>Microsoft.Help.F1</p></td>
    <td><p>Forms.CustTable</p></td>
    </tr>
    <tr class="odd">
    <td><p>description</p></td>
    <td><p>Add the following to the existing text that appears in the description: This content element has been customized by Contoso.</p></td>
    </tr>
    </tbody>
    </table>
    
    The following illustration shows the document properties from the **Source** view of the Visual Studio HTML editor.
    
    ![Update the document properties](images/JJ677317.HelpSystem_CustomersDocProperties(AX.60).png "Update the document properties")

5.  Click **Save**. The updated ContosoCustomerFormUpdate.htm file is saved to your desktop. You can close Visual Studio.

## Publishing the Updated Content Element

This section describes how you publish a content element to the Help server. Before you publish the HTML file, you might want to add a publisher and language folder to the Help server. You use these folders to organize and store the HTML files for your content elements. If you already have an existing folder on your Help server where you want to publish the files, you can skip the procedures for adding folders. For more information about how to publish a content element, see [Publishing Overview](publishing-overview.md).

This section also shows how you can copy the Microsoft cascading style sheet (CSS), image, and script files to the publisher folder. If your content element includes references to CSS, image, or script files, you have to make those files available to your content element. Take care that the files are in the location specified by the src attributes of the elements that reference a CSS, image, or script file.

### To add a publisher folder to the Help server

1.  Use Windows Explorer and open the Content folder of the Help server. The folder is typically found in c:\\inetpub\\wwwroot\\DynamicsAX6HelpServer\\Content of the Help server but can be changed during install.

2.  Right-click the Content folder, click **New**, and then click **Folder**. A folder is added to Content. Right-click the new folder, click **Rename**, and then type Contoso for the folder name.

### To add a language folder to the publisher folder

1.  Right-click the Contoso folder, click **New**, and then click **Folder**. Right-click the new folder, click **Rename**, and then type EN-US for the folder name.

2.  Double-click the EN-US folder. You will copy the ContosoCustomerFormUpdate.htm file to this folder.
    
    The following illustration shows the Contoso\\EN-US folders that you add to the Content folder of the Help server.
    
    ![Add folders for custom help documentation](images/JJ677317.HelpSystem_PublisherFolder(AX.60).png "Add folders for custom help documentation")

### To copy style, image, and script files to the publisher folder

1.  Use Windows Explorer to move to the Content folder of the Help server. The folder is typically found at c:\\inetpub\\wwwroot\\DynamicsAX6HelpServer\\Content of the Help server.

2.  Expand Microsoft, expand EN-US, right-click the Local folder, and then click **Copy**.

3.  Use Windows Explorer to move to the Contoso folder that you added earlier. Right-click the Contoso folder, and then click **Paste**. A copy of the Local folder is added to that folder.
    
    The following illustration shows that a copy of Local has been added to the Contoso folder.
    
    ![Copy the Local folder to the Contoso folder](images/JJ677317.HelpSystem_CopyLocalFolder(AX.60).png "Copy the Local folder to the Contoso folder")

### To publish the ContosoCustomerFormUpdate.htm file

1.  Find the ContosoCustomerFormUpdate.htm that you put on the desktop or another location. Right-click the file, and then click **Copy**.

2.  In Windows Explorer, move to the Contoso\\EN-US folder. Right-click the folder, and then click **Paste**. The ContosoCustomerFormUpdate.htm file is added to the folder.
    
    The following illustration shows that the ContosoCustomerFormUpdate.htm file has been published to the Contoso\\EN-US folder.
    
    ![Copy the HTML file to the folder](images/JJ677317.HelpSystem_PublishCustomers(AX.60).png "Copy the HTML file to the folder")

## Next Steps

To view the customized content element, open the **Customers** form and press **F1**. You should see the customized content element appear in the Help viewer. The following illustration shows the **Contoso Customers (form)** content element in the Help viewer.

![View the updated documentation for the form](images/JJ677317.HelpSystem_ContosoCustomerHelp(AX.60).png "View the updated documentation for the form")

## See also

[Walkthrough: Creating Help Documentation](walkthrough-creating-help-documentation.md)

[Walkthrough: Publishing Help Documentation](walkthrough-publishing-help-documentation.md)

