---
title: 'How to: Export Elements from a Selected Layer'
TOCTitle: 'How to: Export Elements from a Selected Layer'
ms:assetid: 795ee432-83ee-4b3b-9483-1c07825ccc19
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa611807(v=AX.60)
ms:contentKeyID: 35246033
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Export Elements from a Selected Layer 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

You can export one or more AOT elements from a layer to an .xpo file. Then you can import the elements into the same layer on a different Microsoft Dynamics AX installation, or you can import them into another layer on the same Microsoft Dynamics AX installation.

## Exporting Elements from a Layer

When you export elements from a layer, only the elements that are specific to that layer are exported. Tables and classes may have fields or methods that are located in more than one layer. For example, if you are in the USR layer and add a field to a table that was created in the SYS layer, then export elements from the USR layer, the other fields of that table that are in the SYS layer are not exported.

### To export elements from a layer

1.  Open the AOT and select the elements you want to export.

2.  Click **Command** \> **Export**.

3.  In the **Export to** dialog box, select the layer checkbox, and then select a layer from the list.

4.  Click **Browse** and specify a folder and a name for the export file. The extension for an export file is .xpo.

5.  Click **Export**.

All of the selected elements from the specified layer are exported.

If you want to export all the elements that are in a model, export the model itself. For information about how to export a model, see [How to: Export and Import a Model](how-to-export-and-import-a-model.md).

If you want to export all elements from a layer, consider creating a project that contains all the elements, and then export the project. For more information about projects, see [MorphX Development Projects](morphx-development-projects.md).

## See also

[Layers](layers.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

