---
title: 'How to: Check Elements into the Version Control System'
TOCTitle: 'How to: Check Elements into the Version Control System'
ms:assetid: d3ea22a7-26d8-46d4-8060-ce11bc68a4d8
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa872655(v=AX.60)
ms:contentKeyID: 35268204
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# How to: Check Elements into the Version Control System [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

When you have finished working with objects that are under version control in Microsoft Dynamics AX, you must check them back into the version control system.

## Checking an Object into Version Control

### To check an object into version control

1.  In the AOT, right-click the object that you checked out, and then click **Check In**.
    
    or
    
    Click **Version control** \> **Check In**.
    
    or
    
    Press ALT+I.
    
    or
    
    Click the **Check In** button located at the top of the AOT.
    
    or
    
    Click **Version control** \> **Pending objects**, select elements to check in, and then click **Check In**.

2.  Write a comment about the changes that you have made in the **Description** box.
    

    > [!NOTE]
    > <P>If you get errors during this procedure, it may be because your object has violated a rule. For more information, see <A href="how-to-add-rules-for-elements.md">How to: Add Rules for Elements</A>.</P>



3.  If you want to remove some of the items from the check-in list, select them and press ALT + F9.

4.  If you want to select all or none of the items for check-in, click the **All** or **None** button.

5.  If you use TFS for version control, you can associate work items with your check-in. For more information, see [How to: Associate a TFS Work Item with a Check-in](how-to-associate-a-tfs-work-item-with-a-check-in.md)

6.  Click **OK**.

If you have not changed an object but want to check it back in, or if you do not want to check in your changes; you can select **Undo check out** on the **Pending objects** form.


> [!NOTE]
> <P>It is a Best Practice error <IMG title="Error icon" alt="Error icon" src="images/Aa872655.ErrorIcon(AX.60).gif"> if you try to check in an object that refers to an object that is not in the version control system. You can refer to new objects that have been created in the same check-in list.</P>



## See also

[How to: Add Elements to the Version Control System](how-to-add-elements-to-the-version-control-system.md)

[How to: Check Elements Out of the Version Control System](how-to-check-elements-out-of-the-version-control-system.md)

[How to: Rename Elements in the Version Control System](how-to-rename-elements-in-the-version-control-system.md)

[How to: Roll Back to a Previous Version of an Element](how-to-roll-back-to-a-previous-version-of-an-element.md)

[How to: Synchronize Your Local Repository with the Version Control System](how-to-synchronize-your-local-repository-with-the-version-control-system.md)

