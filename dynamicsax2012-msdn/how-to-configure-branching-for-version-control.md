---
title: 'How to: Configure Branching for Version Control'
TOCTitle: 'How to: Configure Branching for Version Control'
ms:assetid: 3267bca6-6993-4878-9908-59a9487fd327
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh272174(v=AX.60)
ms:contentKeyID: 36544624
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# How to: Configure Branching for Version Control [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Branching allows development in Microsoft Dynamics AX to occur concurrently on more than one version of the code base. For example, you might be creating new code in a development branch, while making different changes in a release branch. Changes in both these branches might be periodically synchronized into a main branch. Each branch is a separate code repository. Branching is supported if you use Team Foundation Server (TFS) for version control.

## Setting up Branching

Branching occurs when you take a snapshot of code in the main project. This baseline is usually represented by a label. The snapshot is known as the child branch, and the source of the snapshot is called the main branch. You can use branching to create child branches for development or for a release.

To use branching, create a main branch and one or more child branches in TFS. For example, you might have a main branch, a development branch, and a release branch. The development and release branches are branched from the main branch and are considered child branches.

If you decide to modify code in the release branch, you can merge the changes into the main branch and then into the development branch. You can merge your changes from the development branch into the main branch to reflect the development work that you have done, and then merge the main branch into a release branch when you are ready to release your code.

### To create a main branch

1.  In Microsoft Visual Studio, connect to the Team Project root folder. Click **Team** \> **Connect to Team Foundation Server…**

2.  Select your Team Foundation Server and Team Project, and then click **Connect**.

3.  Click **Tools** \> **Options**. Click **Source Control** \> **Plug-in Selection**. Select **Visual Studio Team Foundation Server**. Click **OK**.

4.  In Team Explorer, double-click **Source Control**.

5.  Configure version control in Microsoft Dynamics AX to use TFS. For more information, see [How to: Set Up Local Version Control Parameters (Developer)](how-to-set-up-local-version-control-parameters-developer.md), [How to: Configure Global Version Control System Settings (Administrator)](how-to-configure-global-version-control-system-settings-administrator.md), and [How to: Create a Repository](how-to-create-a-repository.md).

6.  Right-click the folder that you want to be the main branch, point to **Branching and Merging**, and then click **Convert to Branch**. Type a description, and then click **Convert**.

### To create a child branch

1.  Right-click the main branch folder, point to **Branching and Merging**, and then click **Branch**.

2.  In **Target Branch Name**, specify the folder of the child branch, and then click **Branch**. Click **Yes** to continue to branch.

3.  If you want to apply a label to the branch, right-click the child branch and then click **Apply Label…**

4.  In **Name**, type a label to apply to the branch. For example: Release 1.1.

5.  Click **Create**.

## See also

[Version Control System](version-control-system.md)

[How to: Merge Branches](how-to-merge-branches.md)

