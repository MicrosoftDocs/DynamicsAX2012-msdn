---
title: 'How to: Publish a Help Document'
TOCTitle: 'How to: Publish a Help Document'
ms:assetid: 2ef1d42f-6253-4ca0-9370-3c183f398694
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg882324(v=AX.60)
ms:contentKeyID: 35257155
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# How to: Publish a Help Document 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

To publish a document, copy the HTML, Word, or other file that contains your documentation to the **content** folder of the Help server. Typically, you copy the files to a subfolder of the **content** folder.


> [!TIP]
> <P>Before you publish files, you might want to add a publisher ID and language folder to the Help server file system. For more information about how to add folders to the Help server, see <A href="how-to-add-folders-to-the-help-server.md">How to: Add Folders to the Help Server</A>.</P>



### To publish files to the Help server

1.  Open **Windows Explorer** and open the folder that contains the HTML or other types of document files that you want to publish.

2.  Open a second **Windows Explorer** window. Navigate to the **content** folder or one of its subfolders on the Help server where you want to publish Help documentation. Typically, the **content** folder includes subfolders that match the publisher ID and language metadata properties of your document. The following example shows a typical location for these folders.
    
    C:\\inetpub\\wwwroot\\\<HelpServerName\>\\content\\\<publisher ID\>\\\<language\>

3.  Copy the files you want to publish to the folder you opened in the previous step.
    

    > [!WARNING]
    > <P>Before you copy files to the <STRONG>content</STRONG> folder or subfolder, verify you are using a logon that has write permissions to that folder.</P>

    
    The following table specifies the files you use to publish each type of content element. For more information about how to create a content element that you can publish to the Help server, see [Authoring Help Documents](authoring-help-documents.md).
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Document type</p></th>
    <th><p>Description</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p>HTML</p></td>
    <td><p>Drag the .htm or .html file and drop that file into the folder you use to publish Help documentation.</p></td>
    </tr>
    <tr class="even">
    <td><p>Word</p></td>
    <td><p>If you use Word to create the document as a web page, drag the .mht file and drop the file into the folder you use to publish Help documentation. Next, drag the .htm file that contains the document properties for that content element and drop the file into the same folder.</p>
    <p>If you want to publish the Word file, drag the .docm or .docx file and drop the file into the folder you use to publish Help documentation. Next, drag the .htm file that contains the document properties for that content element and drop the file into the same folder.</p></td>
    </tr>
    <tr class="odd">
    <td><p>Other</p></td>
    <td><p>Drag the document file and the .htm file that contains the document properties for that content element and drop the file into the folder you use to publish Help documentation. Next, drag the .htm file that contains the document properties for that content element and drop the file into the same folder.</p></td>
    </tr>
    </tbody>
    </table>


4.  After copying the files, close the **Windows Explorer** windows. To see whether your Help documents were successfully published, open each content element in the Help viewer. If you added lots of files, you might want to give the **Windows Search Service** additional time to index all the files.

## See also

[How to: Publish Table of Contents Entries](how-to-publish-table-of-contents-entries.md)

[How to: Add Folders to the Help Server](how-to-add-folders-to-the-help-server.md)

