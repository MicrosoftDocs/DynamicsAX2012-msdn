---
title: 'How to: Add Folders to the Help Server'
TOCTitle: 'How to: Add Folders to the Help Server'
ms:assetid: 1761454d-0ae5-4172-a233-99690e3ee791
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg882311(v=AX.60)
ms:contentKeyID: 35257140
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# How to: Add Folders to the Help Server [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

To publish Help documentation, you add your content element and table of contents files to the **content** folder of the Help server. To avoid accidentally overwriting files that have similar names from other publishers, you should add folders that separate your files from those created by other publishers. The following steps show how to add folders for publisher ID and language to the file system of the Help server.


> [!WARNING]
> <P>Before you attempt to add folders, verify that your log-in has write permissions to the content folder.</P>



### To add folders to the file system of the Help server

1.  Use **Windows Explorer** to open the **content** folder in the file system of your Help server. The folder is typically found in the following location.
    
    C:\\inetpub\\wwwroot\\DynamicsAX6HelpServer\\content

2.  To add a publisher ID folder, right-click **content**, click **New**, and then click **Folder**. Enter your publisher ID or name for the folder name. Your folder name must be unique in the **content** folder of the Help server.

3.  Add a language folder. Right-click the folder that has your publisher ID or name, click **New**, and then click **Folder**. Enter a language code for the folder name. The folder name should specify the same language code you use in the language metadata property of your content elements. For example, use **EN-US** as the name of the folder where you will publish content elements written in U.S. English.
    
    Repeat this step to add a folder for each language you use to provide Help documentation.

4.  If you publish lots of files, you might add subfolders that help you organize and maintain your documentation. However, this step is optional. The Help server does not need or require these additional folders. To create a subfolder, right-click your language folder, click **New**, and then click **Folder**. Enter a name for the folder.

## See also

[How to: Add a Publisher to the Web.Config File](how-to-add-a-publisher-to-the-web-config-file.md)

[How to: Publish a Help Document](how-to-publish-a-help-document.md)

[How to: Publish Table of Contents Entries](how-to-publish-table-of-contents-entries.md)

