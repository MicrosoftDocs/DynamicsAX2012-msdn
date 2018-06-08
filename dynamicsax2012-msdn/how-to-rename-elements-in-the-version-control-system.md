---
title: 'How to: Rename Elements in the Version Control System'
TOCTitle: 'How to: Rename Elements in the Version Control System'
ms:assetid: ecd32698-86cb-414e-b963-c0785c4d9aed
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa884321(v=AX.60)
ms:contentKeyID: 35268265
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# How to: Rename Elements in the Version Control System 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

To rename elements that are under version control in Microsoft Dynamics AX, do the following:

  - Rename the element in the AOT.

  - Update interdependencies between elements.

## Renaming an Element in the AOT While Under Version Control

### To rename an element in the AOT

1.  In the AOT, right-click the element and then click **Rename**.

2.  Type the new name. A new element with the new name is created.

3.  Click **Version control** \> **Pending objects**.

4.  Check in the two elements.
    

    > [!NOTE]
    > <P>To update all elements that reference the renamed element, you must check out all elements that refer to the element you want to rename.</P>



When you rename an element, two copies of the element are created: one with the old name and one with the new name. When you check in these elements (for delete and add, respectively), the system integrates both elements to maintain the history.


> [!NOTE]
> <P>If you disable version control, rename an element, and then enable version control again, the name of the element will not revert to what it was before you disabled version control.</P>



## Updating Interdependencies Between Elements

When you rename an element, you must update all other references to the element.

### To update interdependencies between elements

1.  In the AOT, right-click the element you have renamed, and then click **Add-Ins** \> **Cross-reference** \> **Used by**.

2.  Check out all the elements that are listed.

3.  Update the references and then check in the elements.

## See also

[How to: Add Elements to the Version Control System](how-to-add-elements-to-the-version-control-system.md)

[How to: Delete Elements from the Version Control System](how-to-delete-elements-from-the-version-control-system.md)

[How to: Roll Back to a Previous Version of an Element](how-to-roll-back-to-a-previous-version-of-an-element.md)

