---
title: Microsoft Dynamics AX IDE
TOCTitle: Microsoft Dynamics AX IDE
ms:assetid: 7e54604c-006c-4db6-80f0-40f748b0a452
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa676506(v=AX.60)
ms:contentKeyID: 35246123
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Microsoft Dynamics AX IDE 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The integrated development environment (IDE) in Microsoft Dynamics AX is called MorphX. It includes tools for designing, editing, compiling, and debugging code in Microsoft Dynamics AX. This topic describes the MorphX development environment, concepts, and development tools.

The programmable objects in Microsoft Dynamics AX—tables, forms, reports, classes, and so on—are organized in a tree structure called the Application Object Tree (AOT). Creating and editing objects is enhanced by drag-and-drop functionality, and by automatic settings for certain object properties. The source code for methods on classes, tables, forms, and other objects is available to help you extend and customize Microsoft Dynamics AX functionality.


> [!WARNING]
> <P>If your underlying database participates in Microsoft SQL Server replication, you must temporarily suspend replication before you use the AOT to make schema changes such as adding fields to tables.</P>



The concept of inheritance is central to the system—what is defined at the lowest level can be inherited by higher levels in the system. For example, if you change the length of a database field from 10 characters to 20, this change is automatically reflected on all forms in the application that displays this field.

X++ is the programming language in Microsoft Dynamics AX. X++ uses object-oriented programming principles, such as encapsulation, inheritance, classes, objects, methods, and properties. The X++ syntax will be familiar to C\# developers, and incorporates SQL data manipulation statements.

Microsoft Dynamics AX uses a layering system where layers are a hierarchy of levels in the application source code. This ensures that modifications and additions can be made without interfering with the application objects on other levels.

## See also

[MorphX Concepts](morphx-concepts.md)

[Layers](layers.md)

[AOT Overview](aot-overview.md)

[MorphX Development Tools](morphx-development-tools.md)

[MorphX Development Projects](morphx-development-projects.md)

[Workspaces](workspaces.md)

[Microsoft Dynamics AX Debugger](microsoft-dynamics-ax-debugger.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

