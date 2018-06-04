---
title: 'How to: Add Image Files to Enterprise Portal Pages'
TOCTitle: 'How to: Add Image Files to Enterprise Portal Pages'
ms:assetid: 77a02ac5-bd9e-4c97-b346-d05c98aee38e
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa611089(v=AX.60)
ms:contentKeyID: 35245395
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# How to: Add Image Files to Enterprise Portal Pages 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

You can add image files to the Application Object Tree (AOT) in Microsoft Dynamics AX and then display them on web part pages.

## Adding an Image File to the AOT

You can add an image file (such as a .gif or .png) to the AOT, and then deploy it to an Enterprise Portal installation.

### To add an image file to the AOT

1.  In the AOT, expand the **Resources** node.

2.  Right-click the **Resources** node, and then click **Create from File**.

3.  Locate the image file to import, and then click **Open**.

4.  In the Microsoft Dynamics AX client, display the **Administration** pane. In the **Setup** group, expand the **Enterprise Portal** group, and then click **Publish images**.

5.  In the **Publish Images** window, click **OK**. This will publish images from the AOT to the web server.
    

    > [!IMPORTANT]
    > <P>To deploy the images, you must be a site collection administrator for the Enterprise Portal site collection. To verify the user that is the site collection administrator, open SharePoint Central Administration. Click <STRONG>Application Management</STRONG>. In the <STRONG>Site Collections</STRONG> group, click <STRONG>Change site collection administrators</STRONG>. The user who is the site collection administrator is displayed.</P>



## Displaying an Image File in Enterprise Portal

To use the image file on a page in Enterprise Portal, you need to reference it in a web part on a page. Typically, an Image Viewer web part is used to display an image.

### To display an image file in Enterprise Portal

1.  In Enterprise Portal, browse to the page where you want to display the image.

2.  Add an Image Viewer web part to the page. For more information, see [How to: Add Web Parts](how-to-add-web-parts.md).

3.  Set the properties for the Image Viewer web part. Be sure to set the **Image Link** property to the relative URL of the image to display. The images are deployed to the /ep/images folder, so the relative URL is:
    
    /\_layouts/ep/images/*filename*

4.  Set the other properties as needed for the web part.

5.  Save the changes you made for the Image Viewer web part and the page.

