---
title: Modifying the Shortcut Menu on Form Controls
TOCTitle: Modifying the Shortcut Menu on Form Controls
ms:assetid: 786ade59-01a7-46f8-81a3-0a556bba3340
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa674954(v=AX.60)
ms:contentKeyID: 35246012
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Modifying the Shortcut Menu on Form Controls 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The shortcut menu on controls appears when a user right-clicks on a form control. The content of the menu is controlled by the system and is defined according to the current context.

The following figure is an example of a shortcut menu.

![Example of a shortcut menu](images/Aa674954.Axdvgus00000134(en-us,AX.60).gif "Example of a shortcut menu")

When the user right-clicks a control, the context method for the control is called, and its super() call calls the showContextMenu method. The parameter to showContextMenu is a handle to the system’s shortcut menu.

Use showContextMenu to add your own item to the shortcut menu.

## Example

    int showContextMenu(int MenuHandle)
    {
        int ret;
        PopupMenu m = PopupMenu::create(MenuHandle,this.hWnd());
     
        // Save the handle of the appended menu item.
        int myMenuItem = m.insertItem("MyItem");
        ;   
        // Display the menu.
        ret   = m.draw(); 
     
        // Check if the user selected myMenuItem.
        if   (ret == myMenuItem) 
        {
            print   "MyItem was selected";
            pause;
            return   0;
        }
        else
        return ret;
    }

Note that the draw method is called instead of super().

The showContextMenu method should return the user’s selection if the system should take a menu action based on the selection, or zero (0) if no action should be taken.

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

