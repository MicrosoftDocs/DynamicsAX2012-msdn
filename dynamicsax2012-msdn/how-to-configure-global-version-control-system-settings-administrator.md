---
title: 'How to: Configure Global Version Control System Settings (Administrator)'
TOCTitle: 'How to: Configure Global Version Control System Settings (Administrator)'
ms:assetid: e7a633d6-6c61-46e6-88d5-2fb22a954bba
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa497046(v=AX.60)
ms:contentKeyID: 35268220
ms.date: 11/07/2012
mtps_version: v=AX.60
f1_keywords:
- Forms.SysVersionControlParametersAdm
---

# How to: Configure Global Version Control System Settings (Administrator) [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

As an administrator, you control the global settings for the version control system (VCS). Depending on the VCS that you choose, this may include specifying rules for elements in the VCS and rules for best practices.


> [!NOTE]
> <P>You must visit the Version Control Parameters form before you can access the version control system settings. For more information, see <A href="how-to-set-up-local-version-control-parameters-developer.md">How to: Set Up Local Version Control Parameters (Developer)</A></P>



### To set the system settings

1.  Click **Version control** \> **System settings**.
    

    > [!NOTE]
    > <P>The options in the System settings form depend on the VCS you specify in the Version control parameters form.</P>



2.  Set up the global parameters for the VCS, best practice settings for checking files in, and label file settings. For more information about best practices, see [Best Practices for Microsoft Dynamics AX Development](best-practices-for-microsoft-dynamics-ax-development.md).
    

    > [!NOTE]
    > <P>If you select the <STRONG>Run title case update</STRONG> check box and add an object that has incorrect casing to version control, the casing will be corrected. The object will be created in a new layer. The <STRONG>Compare</STRONG> tool is not case sensitive, so it will not detect the change.</P>



3.  Click the **Exclude element names** link. Add rules to reject element names. For example, add \<aaa. The regular expression \< means ‘begins with’. This rule will reject element names that begin with aaa.

4.  Click the **Exclude element types** link. Add rules to reject element types. For example, select Job and PrivateProject.

5.  Click the **Models** link. Set up additional folders that are used by the VCS when you create new objects in Visual Studio and specify the location of the label file to use for each subfolder.

## See also

[How to: Set Up Local Version Control Parameters (Developer)](how-to-set-up-local-version-control-parameters-developer.md)

