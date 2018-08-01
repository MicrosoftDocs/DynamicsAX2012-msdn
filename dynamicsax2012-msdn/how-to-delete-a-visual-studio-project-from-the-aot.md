---
title: 'How to: Delete a Visual Studio Project from the AOT'
TOCTitle: 'How to: Delete a Visual Studio Project from the AOT'
ms:assetid: 22711d9a-0b8e-42a7-8bb0-0abeea77d4f4
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg889126(v=AX.60)
ms:contentKeyID: 35272024
ms.date: 11/21/2012
mtps_version: v=AX.60
---

# How to: Delete a Visual Studio Project from the AOT [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

You can delete a managed code project from either the MorphX or the Visual Studio Integrated Development Environment (IDE).


> [!WARNING]
> <P>Whichever method you use, deleting a project removes it from the model store and cannot be undone. However, the project is not deleted from the file system.</P>



### To delete a project from the AOT by using MorphX

1.  Open the AOT and navigate to your project under the **Visual Studio Projects** folder.

2.  Right-click the project and select **Delete**.

3.  A delete confirmation appears. Click **OK**.
    

    > [!TIP]
    > <P>When you delete a managed project in MorphX and you have Visual Studio open, the changes may not be reflected in the Application Explorer. To resolve this issue, right-click the <STRONG>Visual Studio Projects</STRONG> node and select <STRONG>Refresh</STRONG>.</P>



### To delete a project from the AOT by using Visual Studio

1.  In Visual Studio, click **View** \> **Application Explorer** to open the Application Explorer if it is not visible.

2.  Navigate to your project under the **Visual Studio Projects** folder.

3.  Right-click the project and select **Delete**.

4.  A delete confirmation appears. Click **OK**.

## Next Steps

If you have added a project to the AOT and you want to delete that project from the file system, it is recommended that you first delete it from the AOT.

## See also

[How to: Add a Visual Studio Project to the AOT](how-to-add-a-visual-studio-project-to-the-aot.md)

[Visual Studio Development for Microsoft Dynamics AX](visual-studio-development-for-microsoft-dynamics-ax.md)

