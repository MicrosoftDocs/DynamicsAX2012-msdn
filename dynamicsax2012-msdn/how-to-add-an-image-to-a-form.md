---
title: 'How to: Add an Image to a Form'
TOCTitle: 'How to: Add an Image to a Form'
ms:assetid: f8d55608-75cb-4866-94e2-50695051c225
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa890890(v=AX.60)
ms:contentKeyID: 35253794
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Add an Image to a Form 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Add an image to a form, such as a company logo.

1.  Expand the **Designs** node for the form.

2.  Right-click the **Design** node, and then select **New Control** \> **Window**.

3.  Open the properties dialogue box for the new control by right-clicking the control and selecting properties.

4.  Specify the file name and location in the **ImageName** property.

5.  Set the ImageMode property to center the image, put it next to other controls or size the image to fit the default form size.

You can also specify the image for the control by using the DataSource and DataField properties, or the DataSource and DataMethod properties. For an example, see the tutorial\_Form\_Windowingrid form.

For more information about the properties available for a Window control, see [Form Control Properties](form-control-properties.md).

## Add a Image by Using Code

Specify the image for the control by using code to customize how your image is displayed.

For example, you have created a form with an unbound Window control (a control without a data source). The control is named CompanyLogo, and you want to display a bitmap named Image.bmp.

1.  Declare a variable for the bitmap in the classDeclaration method on the form.
    
       ```X++
       class FormRun extends ObjectRun
        {
            FormWindowControl compLogo;
        }
       ```
    
    FormWindowControl is a system class that implements all the properties of a Window control, and also contains methods to change the control.

2.  Override the init method for the form to add the code that accesses the CompanyLogo control.
    
       ```X++
       void init()
        {
            super();
            compLogo = element.design().control(control::CompanyLogo);
        }
       ```

3.  Write the code to initialize the bitmap display in the run method for the form.
    
       ```X++
       void run()
        {
            super();
            compLogo.imageName('Image.bmp');
        }
       ```
    
    In this example, the bitmap is located in the current directory. The complete path must be specified if the file is located elsewhere.

4.  To make sure that that the image is updated (if you decide to link to another form), insert the code in the linkActive method on the form’s **Data Sources** node.
    
       ```X++
       void linkActive()
        {
            super();
            compLogo.imageName('Image.bmp');
        }
       ```

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

