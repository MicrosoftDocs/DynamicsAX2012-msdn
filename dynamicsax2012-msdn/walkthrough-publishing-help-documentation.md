---
title: 'Walkthrough: Publishing Help Documentation'
TOCTitle: 'Walkthrough: Publishing Help Documentation'
ms:assetid: b7321d10-e382-40ee-8567-884b2d834a7a
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg882381(v=AX.60)
ms:contentKeyID: 35257208
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# Walkthrough: Publishing Help Documentation [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

This topic shows how you create and publish a single content element to the Microsoft Dynamics AX Help server. A content element is a file or files that contain Help documentation for a specified topic. You publish a content element when you want to add custom documentation that appears in the Help viewer. The walkthrough includes the following tasks:

  - How you use a template to create a content element.

  - How you use the template to add the Help server document properties to a content element.

  - How you use the template to produce the files that you publish to the Help server.

  - How you add a folder to the file system of the Help server where you can put files.

  - How you copy files to the Help server.

  - How you view your content element in the Help viewer.

You will use the Microsoft Word template to create a content element. Typically, you use the Word template to create a simple content element that supplements an existing Help topic. The Word template is intended for people who are not comfortable working with HTML. For example, you use the controls in the Word ribbon when you want to add links, images, or tables to the documentation.

If your Help documentation requires links, illustrations, scripts, or styles, you might find the Word template does not provide enough flexibility to produce the documentation that you need. To produce more complex types of Help documentation or a content element that closely resembles existing Microsoft Dynamics AX Help documentation, you should use HTML. For information about how to create a content element that uses HTML, see [Walkthrough: Creating Help Documentation](walkthrough-creating-help-documentation.md).

## Prerequisites

To complete this walkthrough, you must have the following:

  - The Microsoft Dynamics AX client and Help viewer installed.

  - Microsoft Office Word 2007 or a later version installed.

  - You must log-in with an account that has permissions to add folders and files to the Help server file system. You might need a system administrator to give you access to the Help server file system.

## Open the Word Template

This section describes how to find and open the Microsoft Word template. The template is installed on the Help server and can be accessed from the Help viewer. You use the template to create the files that you will publish to the Help server.

### To find the Word template

1.  Start the Microsoft Dynamics AX workspace, and then press F1. The Help viewer opens on your computer.

2.  Enter **Templates for Help Documentation** into the search box and press **Enter**. The following illustration shows the search results.
    
    ![Use search to find the Word template](images/Gg882381.HelpSystem_SearchTemplates(AX.60).png "Use search to find the Word template")

3.  Click the **Templates for Help Documentation** link in the list of search results. The specified topic opens in the Help viewer.

### To open the template with Word

1.  In the Help viewer, click the **Dynamics Help Content Template.docm** link in the list of templates. The file opens using Word.
    
    The following illustration shows the **Dynamics Help Content Template.docm** link in the **Templates for Help Documentation** topic.
    
    ![Use the link to open the template](images/Gg882381.HelpSystem_FindTemplate(AX.60).png "Use the link to open the template")

2.  You have to enable macros for the template. The macros will produce the files that you publish to the help server. If you do not enable the macros, you will have to manually create the required files.
    
    To enable macros, click the **Developer** tab, click **Macro Security**. The Word **Trust Center** window opens. In the **Macro Settings** list, click **Enable all macros**. Click **OK**.

3.  Create a copy of the template file and save the copy to a location where you can work on your content element. The template you currently see in Word is the file from the Help server. You cannot save changes to that template file.
    
    To create a local copy of the template, click **File**, click **Save As**. The **Save As** window opens. Specify the location where you want to save the file. Click **Desktop** to save the file to your desktop.

4.  In the **Save As** window, click **File name:** and type Contoso Help Test.docm.

5.  Click **Save as type:**, click **Word Macro-Enabled Document**, and then click **Save**. The following illustration shows the **Save As** window.
    
    ![Save the template to the desktop](images/Gg882381.HelpSystem_TemplateSaveAs(AX.60).png "Save the template to the desktop")

6.  After the **Save As** window closes, view your desktop and verify that the Contoso Help Test.docm file was created.

## Add Help Content to the Template

This section describes how you use Word and the Contoso Help Test.docm template to create a content element. For more information about the Word and other templates that you can use, see [How to: Create a Help Document using a Template](how-to-create-a-help-document-using-a-template.md).

The following procedures show how to add a title, section heading, and procedure to the template.

### To specify the title for the content element

1.  Update the title text at the top of the template. To change the title, highlight the default text of **Using the Microsoft Dynamics Help Content Template for Microsoft Word**, and then type **Contoso Help Test**.

2.  To match the existing Microsoft Dynamics AX Help topics, use the controls in the **Font** group of the Word ribbon and specify the following values.
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Control name</p></th>
    <th><p>Description</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><strong>Font</strong></p></td>
    <td><p><strong>Segoe UI</strong></p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Font Size</strong></p></td>
    <td><p><strong>16</strong></p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Font Color</strong></p></td>
    <td><p>Click the drop-down button, click <strong>More Colors</strong>, click the <strong>Custom</strong> tab, and then set <strong>Color model</strong> to <strong>RGB</strong>. In the individual color boxes, enter 0 for <strong>Red</strong>, 110 for <strong>Green</strong>, and 18 for <strong>Blue</strong>. Click <strong>OK</strong>.</p></td>
    </tr>
    </tbody>
    </table>
    
    The following illustration shows how you can use the **Colors** window to specify the text color for the title. The specified color matches the title of existing Microsoft Dynamics AX Help documentation. However, you are not required to use the same colors or fonts.
    
    ![Specify the color for the title](images/Gg882381.HelpSystem_TitleTemplate(AX.60).png "Specify the color for the title")

3.  Move the document cursor to after the horizontal line underneath the title, and then delete all of the existing text from the template.

### To add an introduction to the content element

1.  Specify the font to use for the introductory paragraph. To match the paragraphs in existing Microsoft Dynamics AX Help topics, use the controls in the **Font** group of the Word ribbon and specify the following values.
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Control name</p></th>
    <th><p>Description</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><strong>Font</strong></p></td>
    <td><p><strong>Segoe UI</strong></p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Font Size</strong></p></td>
    <td><p><strong>10</strong></p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Font Color</strong></p></td>
    <td><p><strong>Automatic</strong></p></td>
    </tr>
    </tbody>
    </table>


2.  Type an introductory paragraph for the topic. Use the introduction to provide an overview of the information in the content element. The following illustration shows the introduction for the content element.
    
    ![Add an introduction below the title](images/Gg882381.HelpSystem_IntroductionTemplate(AX.60).png "Add an introduction below the title")

3.  Press **Enter** to move to the next line.

### To add a section heading to the content element

1.  Specify the font to use for the section heading. To match the section headings of existing Microsoft Dynamics AX Help topics, use the controls in the **Font** group of the Word ribbon and specify the following values.
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Control name</p></th>
    <th><p>Description</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><strong>Font</strong></p></td>
    <td><p><strong>Segoe UI</strong></p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Font Size</strong></p></td>
    <td><p><strong>14</strong></p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Font Color</strong></p></td>
    <td><p>Click the drop-down button, click <strong>More Colors</strong>, click the <strong>Custom</strong> tab, and then set <strong>Color model</strong> to <strong>RGB</strong>. In the individual color boxes enter 53 for <strong>Red</strong>, 90 for <strong>Green</strong>, and 136 for <strong>Blue</strong>. Click <strong>OK</strong>.</p></td>
    </tr>
    </tbody>
    </table>


2.  In the **Home** tab of the Word ribbon, set the **Style** to **No Spacing** and then type **Adding a section to a Help topic**.

3.  On the next line, click **Bottom Border** from the **Paragraph** group, and then click **Horizontal Line**. A line is added underneath the section heading.

4.  Right-click the horizontal line and then click **Format Horizontal Line**. The **Format Horizontal Line** window opens. Specify the following values:
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Parameter</p></th>
    <th><p>Value</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><strong>Width</strong></p></td>
    <td><p><strong>100%</strong></p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Measure in</strong></p></td>
    <td><p><strong>Percent</strong></p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Height</strong></p></td>
    <td><p><strong>1 pt</strong></p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Color</strong></p></td>
    <td><p>Click <strong>Use solid color (no shade)</strong>. Use the color selection to specify the same color you use for the heading text.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Alignment</strong></p></td>
    <td><p><strong>Center</strong></p></td>
    </tr>
    </tbody>
    </table>
    
    The following illustration shows the **Format Horizontal Line** window.
    
    ![Add a horizontal line under the section heading](images/Gg882381.HelpSystem_HorizontalLIne(AX.60).png "Add a horizontal line under the section heading")

5.  Press **Enter** to move to the next line.

### To add a paragraph to the section

1.  Specify the font to use for the section body. To match the font that is used in existing Microsoft Dynamics AX Help topics, use the controls in the **Font** group of the Word ribbon and specify the following values.
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Control name</p></th>
    <th><p>Description</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><strong>Font</strong></p></td>
    <td><p><strong>Segoe UI</strong></p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Font Size</strong></p></td>
    <td><p><strong>10</strong></p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Font Color</strong></p></td>
    <td><p><strong>Automatic</strong></p></td>
    </tr>
    </tbody>
    </table>


2.  In the **Styles** group of the ribbon, set the style to **Normal**.

3.  Enter the text that you want to appear in the paragraph. Provide information about the procedure that is contained in the content element.

4.  Press **Enter** to move to the next line.

### To add a numbered list for the steps of a procedure

1.  Click the **Numbering** button in the **Paragraph** group of the Word ribbon. A numbered list is started.
    
    To change the list style, click the arrow on the **Numbering** button. Use the **Numbering Library** to specify a style for the numbered list.

2.  Type a description for the first step in the task.

3.  Press **Enter** to add another numbered step. Type a description for that step. Repeat for each step that you want to add to the procedure.
    
    The following illustration shows a procedure that has four steps in a numbered list.
    
    ![Add a pargraph and a list of numbered steps](images/Gg882381.HelpSystem_EnumeratedList(AX.60).png "Add a pargraph and a list of numbered steps")

4.  To end the list, click the **Numbering** button.

## Add the Document Properties and Create the Files

This section describes how you use the template to populate the Microsoft Dynamics AX document properties for the content element. You use document properties to identify the content element and provide information that the Help server uses to match a content element to a request from the Help viewer. For more information about the document properties, see [Authoring Help Documents](authoring-help-documents.md).

This section also describes how you use the template to produce the files you will publish to the Help server. The Word template includes macros that generate the files for you. For more information, see [Using Templates to Create Documentation](using-templates-to-create-documentation.md).

### To specify the document properties

1.  Click the **Microsoft Dynamics Help** tab in the ribbon. The following illustration shows the tab in the Word ribbon.
    
    ![The Microsoft Dynamics Help tab in the template](images/Gg882381.HelpSystem_DynamicsAxTab(AX.60).png "The Microsoft Dynamics Help tab in the template")

2.  In the **Required Properties** group, provide values for the following properties.
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Property</p></th>
    <th><p>Value</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><strong>Title</strong></p></td>
    <td><p>Contoso Help Test</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>TopicID</strong></p></td>
    <td><p>MyContosoHelpTest</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Language</strong></p></td>
    <td><p><strong>English (United States)</strong></p></td>
    </tr>
    </tbody>
    </table>
    
    The following illustration shows the required document properties.
    
    ![Required document property values](images/Gg882381.HelpSystem_RequiredDocProperties(AX.60).png "Required document property values")

3.  In the **Optional Properties** group, provide values for the following properties.
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Property</p></th>
    <th><p>Value</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><strong>Publisher ID</strong></p></td>
    <td><p>Contoso</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Hide Publishers</strong></p></td>
    <td><p>Leave the text box empty.</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Keywords</strong></p></td>
    <td><p>Contoso;Test</p></td>
    </tr>
    </tbody>
    </table>
    
    The following illustration shows the optional document properties.
    
    ![Optional document property settings](images/Gg882381.HelpSystem_OptionalDocProperties(AX.60).png "Optional document property settings")

### To create files you can publish to the Help server

1.  In the **Save** group, click the **Automatically Save Properties** and **Save As Single File Webpage** so that both boxes have a check mark. The following illustration shows the controls in the **Save** group of the **Microsoft Dynamics Help** tab.
    
    ![Click the document save properties](images/Gg882381.HelpSystem_SaveDocProperties(AX.60).png "Click the document save properties")

2.  Click **File** in the Word Ribbon, and then click **Save**.

3.  Find the files you will publish to the Help server. View the location you specified for the Contoso Help Test.docm file. You should see that the macros in the template added the following files.
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>File name</p></th>
    <th><p>Description</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>Contoso Help Test.htm</p></td>
    <td><p>The file contains the document properties for the content element. The file redirects to the Contoso Help Text.mht file.</p></td>
    </tr>
    <tr class="even">
    <td><p>Contoso Help Test.mht</p></td>
    <td><p>The file contains the HTML that appears in the Help viewer.</p></td>
    </tr>
    </tbody>
    </table>


4.  After the file is saved, you can close Word.

## Add Folders to the Help Server

This section shows how you add the folders to the Help server file system where you will publish your content element. You use folders to separate your Help documentation from the documentation provided by other publishers. You can also use folders to organize your content elements. For more information, see [How to: Add Folders to the Help Server](how-to-add-folders-to-the-help-server.md).

The following procedures add a publisher and a language folder where you will publish the two files for the content element files. If you have an existing folder on your Help server where you want to publish the files, you can continue to the next section.

### To add a publisher folder to the Help server

1.  Use Windows Explorer and open the Content folder of the Help server. The folder is typically found in c:\\inetpub\\wwwroot\\DynamicsAX6HelpServer\\Content of the Help server but can be changed during install.

2.  Right-click the Content folder, click **New**, and then click **Folder**. A folder is added to Content. Right-click the new folder, click **Rename**, and then type Contoso for the folder name.

### To add a language folder for the publisher

1.  Right-click the Contoso folder, click **New**, and then click **Folder**. Right-click the new folder, click **Rename**, and then type EN-US for the folder name.

2.  Double-click the EN-US folder. Leave open the Windows Explorer that shows the folder.
    
    The following illustration shows the Contoso\\EN-US folders that you add to the Content folder of the Help server file system.
    
    ![Add folders for custom help documentation](images/JJ677317.HelpSystem_PublisherFolder(AX.60).png "Add folders for custom help documentation")

## Publish Files to the Help Server

This section shows how you publish the .mht, and .htm files for the content element to the Help server. You publish the files when you want your Help documentation to be available to the Help viewer. For more information, see [Publishing Overview](publishing-overview.md).

If you want to keep the source file together with the .htm and .mht files, you can also put the .docm file on the Help server. However, you are not required to add the .docm file to the Help server.


> [!NOTE]
> <P>The steps to publish a content element are the same for both Word and HTML content elements. You can also follow this procedure to publish the file for an HTML content element.</P>



### To copy the files for the content element to the Help server

1.  Open a second Windows Explorer window. Navigate to the desktop or the folder where you put the Contoso Help Test.mht, and Contoso Help Test.htm files.

2.  Press **Ctrl**, and then click the Contoso Help Test.mht, and Contoso Help Test.htm files. Right-click a highlighted file, and then click **Copy**.

3.  View the Windows Explorer window that you opened earlier when you added the Contoso\\EN-US folders. Click the EN-US folder, right-click, and then click **Paste**. The Contoso Help Test.mht and Contoso Help Test.htm files are copied to the EN-US folder of the Help server.
    
    The following illustration shows the files added to the Contoso\\EN-US folder of the Help server.
    
    ![Add the files to the publisher folder](images/Gg882381.HelpSystem_PublishFiles(AX.60).png "Add the files to the publisher folder")

## Next Steps

To view the content element in the Help viewer, press **F1** from the Microsoft Dynamics AX client workspace. After the Help viewer opens, type Contoso Help Test into the search box, and then press **Enter**. In the search results, click **Contoso Help Test**. The topic appears in the Help viewer. The following illustration shows the content element in the Help viewer.

![View content element in the Help viewer](images/Gg882381.HelpSystem_ViewFiles(AX.60).png "View content element in the Help viewer")

