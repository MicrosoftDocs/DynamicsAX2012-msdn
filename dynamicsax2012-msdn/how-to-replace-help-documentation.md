---
title: 'How to: Replace Help Documentation'
TOCTitle: 'How to: Replace Help Documentation'
ms:assetid: 196624fc-10b6-4e46-a39c-3404f7ac0f0b
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg882313(v=AX.60)
ms:contentKeyID: 35257141
ms.date: 11/07/2012
mtps_version: v=AX.60
dev_langs:
- html
---

# How to: Replace Help Documentation [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

This topic describes how to replace Help documentation created by other publishers. To update a help topic, you create a content element that replaces one or more existing content elements for a topic. When you replace a content element, the Help viewer hides the content element of a specified publisher. A content element that is hidden remains on the Help server and can be accessed by using Search.


> [!WARNING]
> <P>Do not edit or remove any files that were published to the Help server by another publisher. A refresh or reinstall of the files from that publisher might overwrite the changes that you made.</P>



To replace existing documentation, you must first create a content element that updates the documentation for the specified help topic. For information about how to create a content element, see [How to: Create a Help Document using a Template](how-to-create-a-help-document-using-a-template.md).

The following steps show how to use the metadata properties of your content element to hide documentation from another publisher.

### To replace an existing content element

1.  Use the Help viewer to open the content element that you want to replace. To view the metadata elements of that content element, right-click in the document window of the Help viewer, and then click View Source. The content element opens in a text editor.

2.  Search for the topic ID of the content element. To find the ID, use the text editor to search for meta name="Microsoft.Help.F1" Record the topic ID.

3.  Search for the ID of the publisher. To find the publisher ID, use the text editor to search for meta name="publisher". Record the publisher ID.

4.  Close the text editor and Help viewer windows.

5.  Open the content element that you created in an HTML or text editor. Search for the meta name="Microsoft.Help.F1" content="" /\> element. Set the content="" value to the topic ID that you retrieved earlier.
    
    The following example specifies the topic ID for a content element.
    
    ``` html
    <meta name="Microsoft.Help.F1" content="c3fc5774-6ed0-4760-86f5-7899e825ab25" />
    ```

6.  Search for the meta name="suppressedPublishers" content="" /\> element. Set the content="" value to the publisher ID that you retrieved earlier.
    

    > [!TIP]
    > <P>If you have to hide content elements of more than one publisher, use semicolons to separate each publisher ID.</P>

    
    The following example adds Microsoft to the suppressedPublishers element.
    
    ``` html
    <meta name="suppressedPublishers" content="Microsoft" />
    ```

7.  Save the file. To replace the specified documentation, publish your content element to the Help server. For more information about publishing, see [How to: Publish a Help Document](how-to-publish-a-help-document.md).

## See also

[Document Property Metadata Reference](document-property-metadata-reference.md)

