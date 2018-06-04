---
title: 'How to: Create a Label File'
TOCTitle: 'How to: Create a Label File'
ms:assetid: 9881afb0-6b2a-409b-8c88-b3f76d6d0721
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa844896(v=AX.60)
ms:contentKeyID: 35247920
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Create a Label File 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

You can create label files to add new user interface text to Microsoft Dynamics AX for one or more languages.

Microsoft Dynamics AX ships with label files called AxSys\<country\>.ald. There is one file for each installed language, for example: AxSysEn-us.ald, AxSysDa.ald, and AxSysDe.ald. Files are updated whenever a new version is released.

New texts for service packs may be released in a label file called AxSyp\<country\>.ald.

## Create Label Files

1.  In the **Tools** menu, click **Tools** \> **Wizards** \> **Label File Wizard**.
    

    > [!NOTE]
    > <P>To ensure that only valid file names are used for label files, always use the Label File Wizard to create new files and languages. The label editor cannot open a label file that has an invalid name and users will see a message saying that the label file has been renamed.</P>



2.  Use the wizard to do one of the following:
    
      - Select **Create a label file ID** and **Create new label language** to generate a label file with a new label file ID for languages selected from the list of available languages.
    
      - Select **Create new label language** to generate a label file with an existing label ID for languages selected from the list of available languages.
    
    Click **Create new language** to create label files for a language that does not appear in the list.
    

    > [!NOTE]
    > <P>You cannot remove languages from the list of available languages. It is created on the basis of other language files current during installation.</P>



3.  Click **Finish** to create label files.

## See also

[How to: Create and Use Labels](how-to-create-and-use-labels.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

