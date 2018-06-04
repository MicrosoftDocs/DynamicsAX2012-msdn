---
title: Connection to AOT
TOCTitle: Connection to AOT
ms:assetid: ab3b4a5d-7751-4380-94cd-5d2eccb9e1e1
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc635353(v=AX.60)
ms:contentKeyID: 28119473
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# Connection to AOT 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

A web application project for Enterprise Portal User Controls maintains a connection to the AOT in Microsoft Dynamics AX, based upon the currently-active user configuration. This enables various items in the project to be retrieved from or written to the AOT in the layer the active user configuration has specified. After they are in the AOT, the items can be accessed by Enterprise Portal.

## User Controls

After new User Controls (.ascx files) are created in Visual Studio, they are added to the AOT. There they can be used in Enterprise Portal.

Existing User Controls in the AOT can be added to the current web application project so that they can be edited. When a User Control that has been added to the AOT is saved in Visual Studio, it is automatically updated in the AOT.

When setting properties for the components used to create User Controls, values are read from the AOT. For instance, the data sources available for an AxDataSource component are read directly from the AOT.

## Visual Studio Projects

Other Visual Studio projects in the AOT can be retrieved from the AOT and added to the web application project. These additional projects are needed when your project references classes, methods, enumerations, or other resources from them.

