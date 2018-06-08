---
title: Adding a Visual Studio Project to the AOT
TOCTitle: Adding a Visual Studio Project to the AOT
ms:assetid: 5dbbcf69-7ff2-4687-8b56-eea56db94729
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg889206(v=AX.60)
ms:contentKeyID: 35272098
ms.date: 11/21/2012
mtps_version: v=AX.60
---

# Adding a Visual Studio Project to the AOT 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

After you create a project in Visual Studio, you can add that project to the Application Object Tree (AOT) in Microsoft Dynamics AX. Visual Studio projects appear in the Visual Studio Projects node in the AOT. For more information about how to add a project to the AOT, see [How to: Add a Visual Studio Project to the AOT](how-to-add-a-visual-studio-project-to-the-aot.md).

## Visual Studio Projects Folder in the AOT

Depending on the type of project you create, it will appear in the AOT in the corresponding folder below the Visual Studio Projects node:

  - Dynamics AX Model Projects

  - C Sharp Projects

  - Visual Basic Projects

  - Web Application Projects

  - Analysis Services Projects

## Project Files in the AOT

In the AOT, each project contains the following folders:

  - Project Content – Replicates the file hierarchy found in the project directory.

  - Project Output – Contains the primary output of the project. For example, this folder will contain the assembly (.dll) file for a class library project.

### Project Content

The Project Content folder contains the files found in the project directory including the project file and the proxy files. For example, if you add a C\# project to the AOT, the Project Content folder will contain MyProject.csproj.

In addition, this folder may also contain proxy files. There is a .axproxy file for each X++ object for which a proxy is generated. A proxy is generated when an X++ object is added to the project. For more information, see [Walkthrough: Adding an X++ Object to a Visual Studio Project](walkthrough-adding-an-x-object-to-a-visual-studio-project.md). So, for example, if you have an event handler project that contains the class XppPrePostArgs and the table CustTable, the Project Content folder will contain an .axproxy file for both XppPrePostArgs and CustTable.

Do not link to any .cs file that is in a different folder than the project root folder. This can prevent this project from opening in Dynamics AX.

### Project Output

The Project Output folder contains the output of the project. If your project is a class library, this will be a .dll file.

## How Managed Code Projects are Stored

When you add a managed code project to the AOT, the code is stored in the model store. For more information, see [Model store architecture](https://msdn.microsoft.com/en-us/library/dd362019\(v=ax.60\)). The project files are saved in the layer and model in which the user is working in as defined by the client configuration. This means that layer-based customizations are supported in managed code just as they are in standard X++ code. After you add a managed code project to the AOT, you should consider this the master copy even though you continue to work on it in Visual Studio.

## See also

[How to: Add a Visual Studio Project to the AOT](how-to-add-a-visual-studio-project-to-the-aot.md)

[XppPrePostArgs](https://msdn.microsoft.com/en-us/library/gg835235\(v=ax.60\))

