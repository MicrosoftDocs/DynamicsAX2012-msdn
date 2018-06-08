---
title: Troubleshooting the Publishing Process
TOCTitle: Troubleshooting the Publishing Process
ms:assetid: 147c3b71-d0e4-47f3-a198-30668759dd53
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg882305(v=AX.60)
ms:contentKeyID: 35257134
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# Troubleshooting the Publishing Process 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

This topic describes what to do when the content element or table of contents entry that you published to the Help server is not visible in the Help viewer. The following sections can help you to identify and resolve common publishing issues.

## Help Server

Check whether the Help viewer can connect to the Help server where you published your content element, or table of contents entry. To view a documentation change, the Help viewer must be able to request and retrieve information from the Help server. The following list suggests solutions to common connection issues.

  - Verify that the Help viewer is configured to connect to the Help server where you published changes. If you use more than one Help server for development, testing and production, make sure that the Help viewer connects to the server where you published your changes. To view the specified Help system, use the application workspace and then click **Administration**, **Setup**, and then click **Help System Parameters**. The **Help System Parameters** window opens and displays the URL of the Help service.

  - Use **Internet Information Services (IIS) Manager** on the Help server to verify that the **DynamicsAX6HelpServer** web service is available. To open **Internet Information Services Manager**, click **Start**, click **All Programs**, click **Administrative Tools**, and then click **Internet Information Services (IIS) Manager**. Review the status of the **Application Pools** and **Sites**. If the web service or application pool for the Help service is stopped or not working, the Help server will not respond to requests for help topics.

## Windows Search Service

Check whether the **Windows Search Service** (WSS) is running on the server. WSS plays an important role in the publishing of content elements. A content element will not appear in the Help viewer until it has been indexed by WSS. If WSS is not running, use the **Services** window to restart the service. Allow WSS to find and index the files you published to the Help server.

If you verify WSS and find that the service is running, you might have to give the indexing process more time to find your content element. The WSS index operation will slow down or stop if the server is busy. You might have to wait for a decrease in server activity before your published content element is available in the Help viewer.

## Event Logs

Check whether the Help server or WSS logged any error messages in the **Application** log of the server. To look for error messages, open the **Event Viewer** window and then click on the **Application** log. Both the Help server and WSS record errors and warnings in the **Application** log.

## Content Element

Check whether the Help server can open and process the .html file of the specified content element. If the Help server cannot locate the file or the file does not include the required metadata, the Help server will not send that content element to the Help viewer. The following list suggests solutions to common .html file issues.

  - Verify that the .html file is in a folder that the Help server uses to store content element files. If the .html file was incorrectly put on the server or was accidentally removed, the content element will not be available in the Help viewer. For more information about publishing content elements, see [Publishing Overview](publishing-overview.md).

  - Verify that the content element includes all required metadata fields. To guarantee that required fields are populated, review the template that was used to create the .html file. If you find that a required metadata field is not populated, add the missing metadata and republish the content element. For more information about how to populate the metadata fields of the template, see [Authoring Help Documents](authoring-help-documents.md).

  - To identify a content element that has incorrect HTML, open the folder that contains the file for the content element in **Windows Explorer**. Add a column to **Windows Explorer** that represents a metadata property from your content element. If **Windows Explorer** does not display a value for that metadata property, the Help service was not able to process the HTML in that file. Review that file to find and fix the HTML syntax error.

## Table of Contents

Check whether the Help server can open and process the XML files that contain the table of contents entries. If the Help server cannot locate the file or the file does not include required metadata, the Help server will not add your entries to the table of contents. The following list suggests solutions to common XML file issues.

  - Verify that the XML file is in a folder that the Help server uses to store table of contents metadata files. If the file was incorrectly put on the server or was accidentally removed, you will not be able to see the table of contents entries in the Help viewer. For more information about publishing table of contents entries, see [Publishing Overview](publishing-overview.md).

  - Verify that the table of contents entry includes all required metadata elements. To ensure the required metadata was included, review the metadata in the XML file. If you find that a required metadata field is not populated, add the missing metadata and republish the XML file. For more information about table of contents metadata, see [How to: Create Table of Contents Entries](how-to-create-table-of-contents-entries.md).

  - Verify that the ID in the Microsoft.Help.F1 property of the table of contents entry identifies a single topic. If two or more topics have the same ID, the Help viewer only opens one topic with that ID. When you use the table of contents to view a content element, the list of topics with the same ID does not appear. As a result, the other topics with that ID cannot be opened from the table of contents.

  - To identify a TableOfContents.xml file that has incorrect XML, open the folder that contains the file in **Windows Explorer**. Add a column to **Windows Explorer** that represents a metadata property from the table of contents. If **Windows Explorer** does not display a value for that metadata property, the Help service was not able to process the XML in the file. Review the TableOfContents.xml file to find and fix the XML syntax error.

## See also

[Publishing Overview](publishing-overview.md)

[How to: Publish a Help Document](how-to-publish-a-help-document.md)

[How to: Publish Table of Contents Entries](how-to-publish-table-of-contents-entries.md)

[Help Document Set Properties](help-document-set-properties.md)

