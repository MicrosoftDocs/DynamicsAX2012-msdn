---
title: 'How to: Create User Controls'
TOCTitle: 'How to: Create User Controls'
ms:assetid: 9ee68843-ecb3-41fe-8b41-9528cb4353c2
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc596115(v=AX.60)
ms:contentKeyID: 28119458
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# How to: Create User Controls 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

You can create your own User Controls for use on Enterprise Portal pages. User Controls are created by using an EP Web Application project in Visual Studio. For more information about how to create an EP Web Application project, see [How to: Create an EP Web Application Project](how-to-create-an-ep-web-application-project.md).

## Adding a New User Control

### To add a new User Control

1.  Start Visual Studio. If User Account Control (UAC) is active, be sure you start Visual Studio with administrative privileges.

2.  Open the EP Web Application project for which you are creating a User Control.

3.  Select the project in Solution Explorer.

4.  In the **Project** menu, click **Add New Item**.

5.  In the **Add New Item** window, expand the **Visual C\#** group of installed templates.

6.  Click **Microsoft Dynamics AX**.

7.  Select the type of User Control that you want to create for Enterprise Portal:
    
      - EP User Control
    
      - EP User Control with Form
    
      - EP User Control with Form and Grid
    
      - EP Chart Control

8.  Name the new User Control.

9.  Click **Add**.

## Designing a New User Control

To design a User Control, you will use the graphical design view in Visual Studio. There will also be cases where you will modify the source for the User Control directly.

### To design a new User Control

1.  In **Solution Explorer**, right-click the User Control.

2.  Click **View Designer** to view the graphical layout for the User Control.
    
    \- or -
    
    Click **View Code** to view the source that defines the User Control.

3.  Using the **Toolbox**, define the contents of the control by adding components from the **Dynamics AX** group in the Toolbox.

4.  Using the **Properties** window, set the properties as needed for the components.

5.  If required, add any code to the markup or the code-behind file for the User Control.

6.  Save the User Control by making the .ascx file for the control active in Visual Studio, and then clicking **Save** in the **File** menu. The control will be saved. It will also be and added to or updated in the AOT.

## Compiling a New User Control in the AOT

To have security work correctly for the new User Control, you must compile it the AOT. Be sure that the new User Control has been saved in Visual Studio, which will add the User Control to the AOT.

### To compile a new User Control in the AOT

1.  In the AOT, expand the **Web** node, and then expand the **Web Files** node.

2.  Expand the **Web Controls** node and locate the new User Control that you created.

3.  Right-click the new User Control and then click **Compile**.

4.  Verify that there are no compiling errors. If there are, correct them in Visual Studio and then compile again.

