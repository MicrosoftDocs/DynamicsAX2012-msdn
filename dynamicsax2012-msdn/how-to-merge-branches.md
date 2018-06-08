---
title: 'How to: Merge Branches'
TOCTitle: 'How to: Merge Branches'
ms:assetid: 5ec9943a-48fa-4068-858a-499928b94787
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh272175(v=AX.60)
ms:contentKeyID: 36544625
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# How to: Merge Branches 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Merging allows you to copy code from one branch to another, or to synchronize changes between two branches. You can only merge branches if you use TFS as your version control system. For more information about branching and merging in TFS, see [Branching and Merging](http://go.microsoft.com/fwlink/?linkid=223395) and for more information about how to set up branching for Microsoft Dynamics AX using TFS, see [How to: Configure Branching for Version Control](how-to-configure-branching-for-version-control.md).

## Merging Branches

Three possible merging scenarios are described below:

  - You can change your code in a release branch and then merge your changes into the main branch.

  - You can then merge those changes from the main branch to the development branch, even though the development branch has changes that are not yet reflected in the main branch.

  - You can also merge your changes from the development branch into the main branch to incorporate the development work that you have done.

### To merge a release branch with the main branch

1.  Apply a label to the release branch if the release branch does not already have a label. In Source Control Explorer, right-click the release branch and then click **Apply Label**. In the **New Label** screen, specify a name for the label. For example: Release 1.01. Click **Create**.

2.  Right-click the release branch, point to **Branching and Merging**, and then click **Merge…** The **Source Control Merge Wizard** appears.

3.  On the **Select the source and target branches for the merge operation** screen: In **Source branch**, specify the release branch. In **Target branch**, specify the main branch.

4.  Click **Next**, and then click **Finish**.

5.  Resolve any conflicts.

6.  Check in the merged changes to the main branch.

### To merge the main branch with the development branch

1.  Right-click the main branch, point to **Branching and Merging**, and then click **Merge…** The **Source Control Merge Wizard** appears.

2.  On the **Select the source and target branches for the merge operation** screen: In **Source branch**, specify the main branch. In **Target branch**, specify the development branch.

3.  Click **Next**, and then click **Finish**.

4.  Click **AutoMerge** or merge the changes manually.

5.  After the conflicts are resolved, click **Yes** to save the file.

6.  Click **Close**.

7.  Check in the merged changes to the development branch.

### To merge the development branch with the main branch

1.  Right-click the development branch, point to **Branching and Merging**, and then click **Merge…** The **Source Control Merge Wizard** appears.

2.  On the **Select the source and target branches for the merge operation** screen: In **Source branch**, specify the development branch. In **Target branch**, specify the main branch.

3.  Click **Next**, and then click **Finish**.

4.  Click **Merge Changes in Merge Tool** or merge the changes manually.

5.  After the conflicts are resolved, click **Yes** to save the file.

6.  Click **Close**.

7.  Check in the merged changes to the main branch.

## See also

[Version Control System](version-control-system.md)

[How to: Configure Branching for Version Control](how-to-configure-branching-for-version-control.md)

[Branching and Merging](http://go.microsoft.com/fwlink/?linkid=223395)

