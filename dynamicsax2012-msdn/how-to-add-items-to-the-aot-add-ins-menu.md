---
title: 'How to: Add Items to the AOT Add-Ins Menu'
TOCTitle: 'How to: Add Items to the AOT Add-Ins Menu'
ms:assetid: edf1f81d-5b0a-4779-8b3a-7d5104529b79
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa884843(v=AX.60)
ms:contentKeyID: 35253254
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Add Items to the AOT Add-Ins Menu [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

In Microsoft Dynamics AX, you can customize the **Add-Ins** menu on the shortcut menu in the Application Object Tree (AOT). The **Add-Ins** menu has various development tools such as the Cross-reference and Security tools. This topic describes how to add your own development tool to the **Add-ins** menu, how to disable the display of a tool that is based on the selection context, and a code example.

### To add an item to the Add-Ins menu

1.  Create a new Action or Display menu item for the tool. For more information, see [How to: Create Menus and Menu Items](how-to-create-menus-and-menu-items.md).

2.  In the AOT, expand **Menus**, and then drag-and-drop the menu item onto the **sysContextMenu**.

## Enabling and Disabling Menu Items According to Context

By default, all items in the **sysContextMenu** menu are always displayed in the **Add-Ins** menu. If you want to disable a menu item based on the selection of an application object, you will have to add code to the verifyItem method for the SysContextMenu class.

The verifyItem method parameters (identifiername menuItemName, MenuItemType menuItemType) are automatically called for each menu item that you add to the **sysContextMenu** menu. The method takes the name of the menu item and the menu item type as parameters, and must return 0 if the menu item should not be displayed.

### ![Aa884843.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa884843.collapse_all(en-us,AX.60).gif")Example

The following code example from SysContextMenu class shows the validation when the Reverse Engineer tool is used as the parameter.

```X++  
    // Only show 'Reverse Engineer'menu item
    // on projects and perspective as we only want to reverse
    // engineer project elements
    case menuitemdisplaystr( SysVisioAddIn ):
        if ( firstNode.handle() == classnum(ProjectNode) &&
        // launch from project node
        match(#pathProjects,firstNode.treeNodePath()))
            {
                return 1;
            }

        if (firstNode.sysNodeType() == #NT_PERSPECTIVE)
        // launch from perspective node
            {
                return 1;
            }
            return 0;
```


> [!TIP]
> <P>There are other classes called SysContextMenu*, for example, SysContextMenuCompare. These classes are used when there are several levels in the add-ins hierarchy. For example, when you select Compare on two objects, the <STRONG>Add-Ins</STRONG> menu is also available in the <STRONG>Compare</STRONG> dialog box. The first() and next() methods on sysContextMenuCompare define the correct context.</P>



## See also

[Shortcut Menu Commands: AOT](shortcut-menu-commands-aot.md)

[Add-Ins Submenu](add-ins-submenu.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

