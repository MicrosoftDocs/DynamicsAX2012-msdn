---
title: 'How to: Add a Script to the Code Editor'
TOCTitle: 'How to: Add a Script to the Code Editor'
ms:assetid: 7ced6a11-a34d-4669-a654-397ebfe07632
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa676080(v=AX.60)
ms:contentKeyID: 35246095
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Add a Script to the Code Editor 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Editor scripts help you to perform frequent tasks more quickly in the X++ code editor. They are accessed by clicking the Scripts button in the code editor window.

To create a new script:

1.  Add a new method to the EditorScripts class.

2.  Name the method.
    
    The name is used as the name of the item in the **Scripts** menu. For example, a method called insertHeader will create a menu item called InsertHeader.
    
    To create a submenu with several items, create a method for each item where the first part of the name is the submenu name, for example.
    
    void sendTo\_file(Editor editor)
    
    void sendTo\_mailRecipient(Editor editor)
    
    void sendTo\_printer(Editor editor)
    
    ![Custom item in the Scripts menu](images/Aa676080.IdeEditorScript(en-us,AX.60).gif "Custom item in the Scripts menu")

3.  Add the editor object as a parameter.

4.  Write the X++ code to perform the desired task, for example.
    
        void sendTo_mailRecipient(Editor editor)
        {
            SysINetMail mail = new SysINetMail();
            ;
            mail.sendMail(
                '',
                e.path(),
                EditorScripts::getSelectedText(e),
                true);
        }

## See also

[Editor Scripts](editor-scripts.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

