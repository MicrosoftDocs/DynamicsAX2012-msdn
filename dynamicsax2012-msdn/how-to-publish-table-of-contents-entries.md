---
title: 'How to: Publish Table of Contents Entries'
TOCTitle: 'How to: Publish Table of Contents Entries'
ms:assetid: 6cb6a7f6-262f-4e8e-b9b0-d3b2f36c2fa0
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg882354(v=AX.60)
ms:contentKeyID: 35257182
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# How to: Publish Table of Contents Entries [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

To add table of contents information, you have to create a TableOfContents.xml file. This file must include the XML for each table of contents entry. To make the new table of contents entries available to the Help viewer, publish the XML file to the Help server.

The following steps describe how to publish a TableOfContents.xml file.


> [!TIP]
> <P>The following steps require that you copy the TableOfContents.xml file to a subfolder of the <STRONG>content</STRONG> folder on the Help server. The Help server can include more than one TableOfContents.xml file but each file must be in a separate folder. Before you publish the file, you might want to add publisher, language, and other subfolders to the <STRONG>content</STRONG> folder of the Help server. For more information about how to add folders to the Help server, see <A href="how-to-add-folders-to-the-help-server.md">How to: Add Folders to the Help Server</A>.</P>



### To publish a table of contents file on the Help server

1.  Use **Windows Explorer** to open the folder that contains your TableOfContents.xml file. For information about how to create the XML file, see [How to: Create Table of Contents Entries](how-to-create-table-of-contents-entries.md).
    

    > [!IMPORTANT]
    > <P>The Help server requires the file to be named TableOfContents.xml. If you do not name the file TableOfContents.xml or tableofcontents.xml, you will not be able to see the table of contents entries in the Help viewer.</P>



2.  Open a second **Windows Explorer** window. Open the folder on the Help server where you want to publish your XML file. Typically, you open a subfolder of the **content** folder. The following example shows a typical location. Notice that the publisher ID and language subfolders match the publisher and language metadata properties found in the XML file.
    
    C:\\inetpub\\wwwroot\\DynamicsAX6HelpServer\\content\\\<publisher ID\>\\\<language\>\\TOCResources

3.  To copy the file, click the TableOfContents.xml file. Drag the file from the current location and drop it in the TOCResources folder on the Help server.
    

    > [!WARNING]
    > <P>Before you copy the file, verify you are using a logon that has write permissions to the specified folder.</P>



4.  After copying the XML file, close the **Windows Explorer** windows. To view the table of contents entries, open the Help viewer. Your entries are added to the existing table of contents.

## See also

[How to: Publish a Help Document](how-to-publish-a-help-document.md)

[How to: Add Folders to the Help Server](how-to-add-folders-to-the-help-server.md)

