---
title: 'How to: Create New MorphX Development Project Types'
TOCTitle: 'How to: Create New MorphX Development Project Types'
ms:assetid: b0cb9e33-230b-425a-8196-837516eded87
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa856269(v=AX.60)
ms:contentKeyID: 35249737
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Create New MorphX Development Project Types [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

You can create your own project type by extending the ProjectNode system class and adding an enumeration value to the SysProjectType base enumeration.

This feature is used in the standard application to create test projects.

## Procedures

By overriding methods, you can have code executed when a project is created, loaded, saved, exported, and imported. You can also change the icons on specific nodes in the project. By using the loadProject and saveProject methods, you can read and write your own custom data with the project.

### ![Aa856269.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa856269.collapse_all(en-us,AX.60).gif")Creating New Project Types

To create your own project type, you must create a new class that extends the ProjectNode system class. You must also add an enumeration value to the SysProjectType base enumeration that shares the name of the class that you created.

### To create a new project type

1.  Right-click the **Classes** node in the AOT and select **New Class**.

2.  Double-click **Class1** to open the Code Editor.

3.  In the Code Editor, rename the class MyProjectType and extend MyProjectType by changing the class declaration to the following:
    ```X++  
        class MyProjectType extends ProjectNode
        {
        }
    ```
4.  In the AOT, expand the **Data Dictionary** node, expand the **Base Enums** node, right-click the **SysProjectType** base enumeration, and then click **New Element**.

5.  Name the element MyProjectType. The name must match the name of the class that you created.

6.  Right-click the **Shared** node in the **Projects** window and point to **New**. The MyProjectType project type will be in the menu.
    

    > [!NOTE]
    > <P>You may have to restart Microsoft Dynamics AX before you can see the changes.</P>


  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

