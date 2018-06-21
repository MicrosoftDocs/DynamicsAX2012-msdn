---
title: 'How to: Add a Publisher to the Web.Config File'
TOCTitle: 'How to: Add a Publisher to the Web.Config File'
ms:assetid: b13355dc-9fe7-48d5-a01b-6775bf158b4a
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg882378(v=AX.60)
ms:contentKeyID: 35257205
ms.date: 11/07/2012
mtps_version: v=AX.60
dev_langs:
- xml
---

# How to: Add a Publisher to the Web.Config File [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

To refine search results and summary pages, the Microsoft Dynamics AX Help server keeps a list of publishers in the web.config file of the server. You update this list to complete the following tasks:

  - You want to add or remove a publisher from the **Search Options** menu of the Help viewer. You use the publisher search option to restrict your search to Help documents created by the specified publisher.

  - You want content elements from one publisher to be listed before or after content elements from another publisher. If your Help request includes content elements from more than one publisher, the summary page uses the publisher list to specify the sort order of the content elements.

  - You want to specify where a group of table of contents entries appears in the Help viewer. The Help server always groups table of contents entries by publisher. When the Help server sends the table of contents to the Help viewer, the server uses the publisher list in the web.config file to determine the order that the entries for each publisher are added to the table of contents.

The following steps show how to add a publisher.


> [!WARNING]
> <P>These steps require that you modify the web.config file of the Help server. Before making any changes, save a copy of your web.config file to a safe location. If you encounter problems with the Help server, use the saved copy of the web.config file to restore your original configuration.</P>



### To add a publisher to the web.config file

1.  Find the web.config file on your Help server and open the file by using a text editor. To change the web.config file, you might have to copy the file to a separate working folder. The web.config file is found in the root folder of your Help server. The following example shows the typical installation folder for the web.config file:
    
        C:\inetpub\wwwroot\DynamicsAX6HelpServer

2.  Find the **publishers** element. The list of publishers is in the **dynamicsHelpConfig** section of the file. The following XML example shows the publishers element from a web.config file.
    
    ``` xml
    <publishers>
       <add publisherId="Microsoft" name="Microsoft" />
    </publishers>
    ```

3.  Add a publisher to the list. The following table specifies the required attributes of the publisher element.
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Attribute name</p></th>
    <th><p>Value</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><strong>publisherId</strong></p></td>
    <td><p>A value that uniquely identifies the publisher. The ID must match the publisher ID specified in the metadata for content elements and the table of contents.</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>name</strong></p></td>
    <td><p>The text to be displayed as the name of the publisher. The <strong>Search Options</strong> menu of the Help viewer displays this name.</p></td>
    </tr>
    </tbody>
    </table>
    
    The following XML example adds a publisher. Notice the order of the publishers in the list. If a summary page includes content elements from both publishers, content elements from the first publisher are listed before content elements from the second publisher.
    
    ``` xml
    <publishers>
       <add publisherId="Contoso" name="Contoso" />
       <add publisherId="Microsoft" name="Microsoft" />
    </publishers>
    ```

4.  Save your changes to the web.config file. If the file is in a working folder, copy your updated web.config file to the **DynamicsAX6HelpServer** folder on your Help server.

## See also

[How to: Add Folders to the Help Server](how-to-add-folders-to-the-help-server.md)

[How to: Publish a Help Document](how-to-publish-a-help-document.md)

[How to: Publish Table of Contents Entries](how-to-publish-table-of-contents-entries.md)

