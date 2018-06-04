---
title: 'How to: Use the Project Filter'
TOCTitle: 'How to: Use the Project Filter'
ms:assetid: 4473180d-8fca-482e-9a63-0117683dc767
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa637684(v=AX.60)
ms:contentKeyID: 35242958
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Use the Project Filter 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

You can use the project filter function to set up criteria for searching the Application Object Tree (AOT). The objects that are found by the search are automatically included in your project.

1.  [Create a new project](how-to-create-a-morphx-development-project.md).

2.  Double-click the project to open it.

3.  Click the filter icon ![Projects window](images/Aa589339.IDEFILT(en-us,AX.60).gif "Projects window") on the project toolbar to open the **Project Filter** dialog box.

4.  Select **Append** to save the contents of the current project before new objects are added. Select **Overwrite** to delete the project's former contents before new objects are added.

5.  Click one of the following buttons (under **Grouping)** to define how the system should group the objects in the project:
    
      - **None** – Adds objects directly to project node
    
      - **AOT** – Groups objects in nodes similar to the AOT (classes, forms, menu items, and so on).
    
      - **Per user** – Groups objects in nodes labeled with user identification.

6.  Click **Select** to define a query.

7.  Click **OK** to save the query and close the dialog box. The query is saved so that you can modify it later and re-create the project.

8.  Click **OK** in the **Project filter** dialog box to generate a project according to the query defined.

## See also

[MorphX Development Projects](morphx-development-projects.md)

[How to: Create a MorphX Development Project](how-to-create-a-morphx-development-project.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

