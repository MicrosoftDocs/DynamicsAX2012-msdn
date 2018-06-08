---
title: 'How to: Delete Elements from the Version Control System'
TOCTitle: 'How to: Delete Elements from the Version Control System'
ms:assetid: 5e906cb5-46fd-44e6-b2f1-9a7463d3d30e
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa607873(v=AX.60)
ms:contentKeyID: 35268031
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# How to: Delete Elements from the Version Control System 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

To delete an element that is under version control, you must delete the element from the AOT and then check in the change.

## Deleting an Element from the Version Control System and from the AOT

### To delete an element

1.  In the AOT, right-click the element and then click **Delete**.

2.  Click **Yes** to confirm the delete. An **Infolog** will open that reports that the element is open for delete, and then the element will disappear from the AOT.

3.  Click **Version control** \> **Pending objects**.
    
    You will see the element listed as checked out for delete.

4.  Click **Check in**, and then check in the change in the usual way.

## See also

[How to: Add Elements to the Version Control System](how-to-add-elements-to-the-version-control-system.md)

[How to: Check Elements into the Version Control System](how-to-check-elements-into-the-version-control-system.md)

[How to: Check Elements Out of the Version Control System](how-to-check-elements-out-of-the-version-control-system.md)

[How to: Rename Elements in the Version Control System](how-to-rename-elements-in-the-version-control-system.md)

