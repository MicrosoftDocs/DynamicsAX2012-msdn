---
title: Upgrade Support for Managed Code
TOCTitle: Upgrade Support for Managed Code
ms:assetid: 63a7740a-68d1-4196-9047-ca99cf9a385f
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg889224(v=AX.60)
ms:contentKeyID: 35272120
ms.date: 11/21/2012
mtps_version: v=AX.60
---

# Upgrade Support for Managed Code [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The layered architecture of Microsoft Dynamics AX enables you to customize the code base and add functionality. When an updated version of Microsoft Dynamics AX such as a service pack is released, conflicts can occur when the service pack contains changes to elements that you changed.

A typical code upgrade scenario is one in which Microsoft Dynamics AX has been deployed at a customer site. A value-added reseller (VAR) working with the customer has made customizations to their installation in order to support their specific business needs. Then Microsoft releases a service pack. Updates contained in the service pack may or may not conflict with customizations made by the VAR. For example, the VAR may customize a report which is then changed in the service pack. For more information about code upgrade, see [Code Upgrade Resources](code-upgrade-resources.md).

In this scenario, you can use the code upgrade tools to analyze the code and detect any conflicts. These tools support both X++ and managed code.

## Code Upgrade Tools

The code upgrade tools enable developers to detect and resolve conflicts between two versions of Microsoft Dynamics AX. These tools support managed code projects that have been added to the Microsoft Dynamics AX model store. The code upgrade tools include the following:

  - Detect code upgrade conflicts tool - Compares the elements in the current layer and the underlying layer. If any differing elements are found, the tool creates an upgrade project and moves the conflicting element in the current layer to that project. You then use the Compare tool to analyze the conflicts and decide which element should be included in the current layer.
    
    The Detect code upgrade conflicts tool - Supports managed code that has been added to the model store by using Application Explorer. This means you use the same process to upgrade code, whether that code originates from MorphX or Visual Studio.

  - Compare tool - Compares two elements in the Application Object Tree (AOT) or two elements in an upgrade project created by the Detect code upgrade conflicts tool. The Compare tool supports managed code so that you can compare two managed code files in the AOT.

## See also

[Code Upgrade Resources](code-upgrade-resources.md)

[Visual Studio Development for Microsoft Dynamics AX](visual-studio-development-for-microsoft-dynamics-ax.md)

[Layers](layers.md)

