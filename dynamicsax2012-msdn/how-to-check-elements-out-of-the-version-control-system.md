---
title: 'How to: Check Elements Out of the Version Control System'
TOCTitle: 'How to: Check Elements Out of the Version Control System'
ms:assetid: e7c5ae96-66a4-4597-bc1b-2bc8c4dee0a4
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa881948(v=AX.60)
ms:contentKeyID: 35268226
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# How to: Check Elements Out of the Version Control System 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

If you use a version control system, you must check items out from the Application Object Tree (AOT) or from Visual Studio before you can edit them.

## Checking out an element

### To check out an element from the AOT

  - In the AOT, right-click the element, and then click **Check Out**.
    

    > [!NOTE]
    > <P>If you see an <STRONG>Add to Version Control</STRONG> option instead of a <STRONG>Check Out</STRONG> option, the element has not yet been added to the version control system. Click <STRONG>Add to Version Control</STRONG>, and then check in the item.</P>



The **Check Out** command synchronizes the local copy with the version control system copy before checking it out. You can select multiple items in the AOT and check them out in one step.


> [!NOTE]
> <P>You can only check out whole elements, not their individual members. For example, you cannot check out a method without checking out the class that contains it.</P>



## See also

[How to: Add Elements to the Version Control System](how-to-add-elements-to-the-version-control-system.md)

[How to: Check Elements into the Version Control System](how-to-check-elements-into-the-version-control-system.md)

[How to: Use Label Files Under Version Control](how-to-use-label-files-under-version-control.md)

