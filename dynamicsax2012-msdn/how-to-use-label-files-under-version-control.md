---
title: 'How to: Use Label Files Under Version Control'
TOCTitle: 'How to: Use Label Files Under Version Control'
ms:assetid: 7c4274d2-0a8b-4072-a942-7fe0f650b614
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa675766(v=AX.60)
ms:contentKeyID: 35268077
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# How to: Use Label Files Under Version Control 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

You can create Microsoft Dynamics AX label files and check them into version control in Microsoft Dynamics AX. You can create a new label file by using the **Label file wizard**. For more information, see [How to: Create a Label File](how-to-create-a-label-file.md). You can add a label file to version control by using the **Label editor**.

## Checking Out and Checking in the Label File

Create or edit labels by using the Label editor. When you create a new label, a temporary label ID is assigned to it.

### To add a label file to version control

1.  Click **Tools** \> **Label** \> **Label editor**.

2.  Click **Add to version control**.

### To check out the label file

1.  Click **Tools** \> **Label** \> **Label editor**.

2.  Click **Check out**.

When finished, check the label file back in. When you check in a new label, the temporary label ID and references to it are mapped to a globally unique label ID.


> [!NOTE]
> <P>If you create a label while the label file is checked out, do not start the client using the –labelsync flag before you check in the label file. If you do, the temporary label file will be added to the AOT.</P>



### To check in the label file

1.  On the **Label editor** form, click **Check in**.

2.  Type a description of the work you completed, and then click **OK**.

## Resolving References to a Temporary Label ID that is Not Valid

If you have references to a temporary label ID that has already been checked in, those references are not valid because the temporary label ID is replaced with a globally unique label ID when you check it in. This can happen when references to the temporary label ID are not in the scope of the check-in.

### To resolve references to temporary labels

1.  Manually locate references to a temporary label ID that should reference the new globally unique label ID.

2.  Update the references to point to the new globally unique label ID.

## See also

[How to: Check Elements into the Version Control System](how-to-check-elements-into-the-version-control-system.md)

[How to: Check Elements Out of the Version Control System](how-to-check-elements-out-of-the-version-control-system.md)

