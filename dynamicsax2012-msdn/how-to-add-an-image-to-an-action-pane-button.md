---
title: 'How to: Add an Image to an Action Pane Button'
TOCTitle: 'How to: Add an Image to an Action Pane Button'
ms:assetid: dbd1eedc-d1e7-4c20-ad3c-bcec55df0253
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc621437(v=AX.60)
ms:contentKeyID: 35252077
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Add an Image to an Action Pane Button [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Each Microsoft Dynamics AX action pane button displays an image. The image makes the button easier to identify and represents the action that the button performs. To specify the image for an action pane button, you use one of the following image sources:

  - Use an image from the embedded resources. Embedded resources are the images that are used with existing action pane buttons.

  - Use an image from the **Resources** node of the Application Object Tree (AOT). In addition, you can add custom images to the **Resources** in the AOT.

  - Use an image from a specified file. You can use images from .bmp, .emf, .exif, .gif, .ico, .jpg, .png, .tiff, or .wmf files.

The following procedures show you how to use the **ImageLocation** and **NormalImage** properties of the button control to associate an image with a button.

## Using an Embedded Image Resource

Follow these steps to add an embedded image resource to an action pane button.

### To specify an embedded image resource

1.  In the AOT, expand **Forms**, and then click the form you want to update.

2.  To view the action pane, expand the form node, expand **Designs**, and then expand the **Design** node.

3.  Expand the action pane, expand the action pane tab, and then expand the button group that contains the button.

4.  Right-click the button, and then click **Properties.** The button properties window opens.

5.  In the **ImageLocation** property, click **EmbeddedResource**.

6.  In the **NormalImage** property, click the ellipsis button. The **Embedded resources** window opens. Use the **Embedded resources** window to find the image that you want to appear on the button.
    

    > [!WARNING]
    > <P>To guarantee consistency across forms, all the buttons that use the specified image should perform the same type of action.</P>



7.  Enter the Resource ID of the image in the **NormalImage** property. For example, enter **8010** to have the button display a green arrow icon.

8.  Right-click the form, and then click **Save**. To find and view the button, right-click the form and then click **Open**.

## Using an Image Resource from the AOT

The AOT includes a **Resources** node that includes images. To simplify the deployment of a custom action pane, you should add custom button images to **Resources**. When you add a custom image to **Resources**, the image is available from the Application Object Server (AOS) and does not require that you deploy the file that contains the image.

The following procedures show how to add an image to the AOT resources and how to use an image resource with an action pane button.

### To add an image resource to the AOT

1.  In the AOT, right-click **Resources**, and then click **Create from File**. The **Select file** window opens.

2.  Navigate to the location of the image file that you want to use for a button. Click the file, and then click **Open**. The image file is imported as a resource.

3.  By default, the resource name is set to the file name that you imported. You might want to change the name that appears in the **Resources** list. To change the name, click the resource, enter a value in the **Name** property, right-click the resource, and then click **Save**.

### To specify an AOT resource

1.  In the AOT, expand **Forms**, and then click the form you want to update.

2.  To view the action pane, expand the form node, expand **Designs**, and then expand the **Design** node.

3.  Expand the action pane, expand the action pane tab, and then expand the button group that contains the button.

4.  Right-click the button, and then click **Properties.** The button properties window opens.

5.  In the **ImageLocation** property, click **AOTResource**.

6.  Enter the name of the resource into the **NormalImage** property of the button.

7.  Right-click the form, and then click **Save**. To find and view the button, right-click the form and then click **Open**.

## Using an Image File

Follow these steps to add an image from a file to an action pane button.

### To specify an image file

1.  In the AOT, expand **Forms**, and then click the form you want to update.

2.  To view the action pane, expand the form node, expand **Designs**, and then expand the **Design** node.

3.  Expand the action pane, expand the action pane tab, and then expand the button group that contains the button.

4.  Right-click the button, and then click **Properties.** The button properties window opens.

5.  In the **ImageLocation** property, click **File**.

6.  In the **NormalImage** property, click the ellipsis button. Use the **Open** window to find the file that contains the image. Click the file that you want to use, and then click **Open**.
    
    For example, you use the **Open** window to open a folder named C:\\ListPageIcons\\, click a file that is named warning.png, and then click **Open**.
    

    > [!NOTE]
    > <P>When you deploy your customization, you have to add the image file to the specified location in each new environment.</P>



7.  Right-click the form, and then click **Save**. To find and view the button, right-click the form and then click **Open**.

## See also

[Action Pane Button Overview](action-pane-button-overview.md)

[How to: Create an Action Pane Button](how-to-create-an-action-pane-button.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

