---
title: 'How to: Create a MorphX Development Project'
TOCTitle: 'How to: Create a MorphX Development Project'
ms:assetid: 1951e0b2-a2d2-47ea-97cf-1718713e4649
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa589339(v=AX.60)
ms:contentKeyID: 35241371
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Create a MorphX Development Project [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

To create a project in Microsoft Dynamics AX, do as follows:

1.  Click **View** \> **Project** \> **Project**. This opens the **Projects** window, which has both **Private** and **Shared** projects.

2.  Right-click either the **Private** or the **Shared** node, click **New**, and then click **Project** to create a standard project or **Test Project** if you are using the Test Unit Framework.
    

    > [!NOTE]
    > <P>You can create your own project types by creating a class that extends the project node.</P>



3.  Open the project by double-clicking it.

4.  Use a drag-and-drop operation to include objects from the AOT in the project. You can create new elements from within a project by using the **New** command on the shortcut menu.

5.  Save the project (it is automatically saved when the project window is closed).

6.  If you are using version control, add the object to the version control system. Private projects cannot be checked into version control.


> [!NOTE]
> <P>If you delete an item from a project, the item is also deleted from the AOT. To delete an item from a project but not from the AOT, right-click the item, and then select <STRONG>Remove</STRONG>.</P>




> [!TIP]
> <P>You can also create a project or add items to a project by using the <A href="how-to-use-the-project-filter.md">project filter function</A>&nbsp;<IMG title="Projects window" alt="Projects window" src="images/Aa589339.IDEFILT(en-us,AX.60).gif">.</P>



## See also

[MorphX Development Projects](morphx-development-projects.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

