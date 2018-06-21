---
title: 'How to: Add Rules for Elements'
TOCTitle: 'How to: Add Rules for Elements'
ms:assetid: 9694d941-bc1a-4b23-9757-ab5aca1a8c9b
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa548610(v=AX.60)
ms:contentKeyID: 35268112
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# How to: Add Rules for Elements [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

When you enable the Version Control System (VCS) in Microsoft Dynamics AX, you can add rules that determine which element names and element types developers can check in. You must restart the Microsoft Dynamics AX client after you change the element rules for the changes to take effect.


> [!NOTE]
> <P>The system settings might be protected from changes so that only the VCS administrator can perform this task. We recommend that your development team follows the <A href="best-practices-for-microsoft-dynamics-ax-development.md">Best Practices for Microsoft Dynamics AX Development</A>.</P>



## Specify Unwanted Element Names

1.  Click **Version control** \> **System settings**.

2.  Click the **Object rules** tab.

3.  In **Unwanted object names**, type the element names or parts of element names that you do not want developers to check in to the VCS.

For example:

  - If you do not allow for element names that start with AAA, type \<AAA, where the less-than sign means "starts with".

  - If you do not allow for form names such as 'Form1', 'Form45', or something similar, type \<Form:d+, where :d+ represents one or more numeric characters.


> [!NOTE]
> <P>For more information about the special characters that you can use when you specify unwanted element names, see the remarks section for the <A href="https://msdn.microsoft.com/en-us/library/aa886279(v=ax.60)">match Function</A>.</P>



## Specify Unwanted Element Types

1.  Click **Version control** \> **System settings**.

2.  Click the **Object rules** tab.

3.  In **Unwanted object types**, select the element types that you do not want developers to create and check in to the VCS.

4.  Press CTRL+N to add more element types to the list.

## See also

[Best Practices for Microsoft Dynamics AX Development](best-practices-for-microsoft-dynamics-ax-development.md)

[match Function](https://msdn.microsoft.com/en-us/library/aa886279\(v=ax.60\))

