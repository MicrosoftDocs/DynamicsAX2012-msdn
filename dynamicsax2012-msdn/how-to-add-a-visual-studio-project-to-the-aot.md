---
title: 'How to: Add a Visual Studio Project to the AOT'
TOCTitle: 'How to: Add a Visual Studio Project to the AOT'
ms:assetid: 71a99dff-dbe2-43a3-a017-d28318759c46
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg889249(v=AX.60)
ms:contentKeyID: 35272149
ms.date: 11/21/2012
mtps_version: v=AX.60
---

# How to: Add a Visual Studio Project to the AOT [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

After you create a project in Visual Studio, you can add that project to the Application Object Tree (AOT) in Microsoft Dynamics AX. Visual Studio projects appear in the Visual Studio Projects node in the AOT. This topic shows you how to add a C\# project to the AOT, but the process is the same for any of the supported project types. For more information about supported project types, see [Adding a Visual Studio Project to the AOT](adding-a-visual-studio-project-to-the-aot.md).


> [!TIP]
> <P>You cannot add a project that resides in a solution folder within Solution Explorer to the AOT.</P>



## Prerequisites

To complete this walkthrough you will need:

  - Microsoft Dynamics AX with Visual Studio Tools installed

  - Visual Studio 2010

### To Add a Visual Studio Project to the AOT

1.  Create a new C\# class library project in Visual Studio. To create a new project, select **File** \> **New** \> **Project**.

2.  From the Installed Templates tree, click **Visual C\#** \> **Windows** and select the **Class Library** template. Accept the default project name, for example, ClassLibrary1.

3.  In Solution Explorer, create and add another C\# class library project to the solution by right-clicking the solution and selecting **Add** \> **New Project**.

4.  Select the **Class Library** template. Accept the default project name, for example, ClassLibrary2.

5.  In Solution Explorer, click the ClassLibrary1 project and add a project reference to the ClassLibrary2 project by right-clicking and selecting **Add Reference**. On the **Projects** tab, select the ClassLibrary2 project.

6.  In Solution Explorer, click the ClassLibrary1 project and select **File** \> **Add ClassLibrary1 to AOT**. When you add a project to the AOT, the system will prompt you to add any dependent projects in the solution. When a dialog appears that prompts you to add ClassLibrary2 to the AOT, click **OK**. If you add a project that has no other project references to the AOT, this prompt does not appear.
    
    Both projects have now been added to the AOT and you can view them in Visual Studio or MorphX.
    
      - In Visual Studio, you can see the projects in the Application Explorer by selecting **View** \> **Application Explorer**. Expand the Visual Studio Projects node, open the **C Sharp Projects** folder, and you will see the ClassLibrary1 and ClassLibrary2 projects. For more information, see [Application Explorer](application-explorer.md).
    
      - In MorphX, to see the project in the AOT, open the AOT, expand the **Visual Studio Projects** node, and open the **C Sharp Projects** folder. For more information, see [Application Object Tree (AOT)](application-object-tree-aot.md).
    

    > [!TIP]
    > <P>After you add a project to the AOT by using the Application Explorer, there may be a delay before the project is visible in the AOT through MorphX. If you do not see your project in the folder, you may need to refresh the AOT. To do this, open the AOT, navigate to the C# Projects Folder, right-click, and then select <STRONG>Refresh</STRONG>.</P>



## Next Steps

After you have added a managed code project to the AOT, the AOS must be running in order to open that project in Visual Studio. If the AOS is not running and you attempt to open a project that has been added to the AOT, you will receive an error.

## See also

[Visual Studio Development for Microsoft Dynamics AX](visual-studio-development-for-microsoft-dynamics-ax.md)

[Adding a Visual Studio Project to the AOT](adding-a-visual-studio-project-to-the-aot.md)

[Application Explorer](application-explorer.md)

[Application Object Tree (AOT)](application-object-tree-aot.md)

