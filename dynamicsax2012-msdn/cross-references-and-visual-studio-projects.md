---
title: Cross-References and Visual Studio Projects
TOCTitle: Cross-References and Visual Studio Projects
ms:assetid: 266c360d-92b4-4192-ac7b-b230ca09fa8d
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg889138(v=AX.60)
ms:contentKeyID: 35272037
ms.date: 11/21/2012
mtps_version: v=AX.60
---

# Cross-References and Visual Studio Projects [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The [Cross-reference Tool](cross-reference-tool.md) in Microsoft Dynamics AX lets you see the relationships between objects. By using the Cross-reference tool, you can see which other objects the current object uses or which other objects use the current object. The Cross-reference tool fully supports Visual Studio projects (found in the Visual Studio Projects node) in the Application Object Tree (AOT).

## Updating Cross-References

In order to see cross-references for Visual Studio projects, you must first add them to the AOT by using the Application Explorer. For more information, see [Walkthrough: Using the Cross-Reference Tool with Visual Studio Projects](walkthrough-using-the-cross-reference-tool-with-visual-studio-projects.md).

After you add a project to the AOT, the project and its cross reference information are updated every time you build the project in Visual Studio. So, if you add two projects to the AOT and then add a reference from one project to another, it will automatically update the cross-references.

## See also

[Cross-reference Tool](cross-reference-tool.md)

[Walkthrough: Using the Cross-Reference Tool with Visual Studio Projects](walkthrough-using-the-cross-reference-tool-with-visual-studio-projects.md)

