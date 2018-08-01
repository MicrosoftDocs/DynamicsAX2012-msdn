---
title: 'How to: Create Web Menu Items'
TOCTitle: 'How to: Create Web Menu Items'
ms:assetid: 9c95ec66-2fca-4805-a29f-02e23220e2eb
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa846824(v=AX.60)
ms:contentKeyID: 35245539
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# How to: Create Web Menu Items [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

You can create a web menu item that links to the following target types:

  - Web pages

  - Classes or jobs (to perform an action)

To display the web menu item on a web part page, you must add the item to a web menu. When the web menu is used on a web part page, the menu item will be available. For more information, see [How to: Add Page-level Navigation](how-to-add-page-level-navigation.md).

## Creating a Web Menu Item That Links to a Page

### To create a Web menu item that links to a Page

1.  In the AOT, expand the **Web** node, and then expand the **Web Menu Items** node.

2.  Right-click **URLs**, and then click **New URL**.

3.  Right-click the new URL that you created in step 2, and then click **Properties**.

4.  Specify the URL, with the following form:
    
    *Module*/Enterprise%20Portal/*PageName*.aspx
    
    Replace *Module* with the name of the module that contains the page and *PageName* with the name of the page to access. For example, the following URL points to the WorkOrderAddEdit page that is part of the Facility module:
    
    Facility/Enterprise%20Portal/WorkOrderAddEdit.aspx
    
    You can also use the ellipsis button (...) to open a dialog box that lets you select the page. Navigate to the module site and document library that contains the page. Select the page and then click OK.
    

    > [!NOTE]
    > <P>If an error message displays, install the update to Microsoft Windows available at <A class=uri href="http://go.microsoft.com/fwlink/?linkid=59932">http://go.microsoft.com/fwlink/?linkid=59932</A>.</P>



5.  Specify the properties indicating how the page will be opened. The following properties control how the page will be displayed:
    
    **WindowMode** – Specifies the type of window the page being opened will be displayed in. The possible values are as follows:
    
      - Inline – The page being opened will replace the existing content in the browser. If the web menu item is being accessed from a modal window, the page being opened will open in a new browser window.
    
      - Modal – If no modal window is open, a new modal will be created. If the web menu item is being accessed from a modal window, the page being opened will replace the content of the current modal window.
    
      - NewModal – The page being opened will always be displayed in a new modal window.
    
      - NewWindow – The page being opened will be opened in a new browser window.
    
    **WindowSize** – Specifies the size of the window that the page being opened will be displayed in. The possible values are as follows:
    
      - Smallest – 330 x 200 pixels
    
      - Small – 550 x 450 pixels
    
      - Medium – 800 x 630 pixels
    
      - Large – 930 x 630 pixels
    
      - Maximum – The largest size that will fit in the boundaries of the main browser window.
    
    **WindowParameters** – Specifies additional parameters for the SharePoint modal dialog that control its appearance. The parameters must be enclosed in braces {} and separated by commas. Some of the common SharePoint modal dialog properties are as follows:
    
      - width
    
      - height
    
      - showClose
    
      - allowMaximize
    
    The following example shows the settings for the WindowParameters property to display the modal dialog with the size 400 x 300 pixels, and having no close box or maximize buttons.
    
    {width:400, height:300, showClose:false, allowMaximize:false}

6.  In the property sheet, modify other properties as needed.

7.  Save the changes in the AOT.

## Creating a Web Menu Item That Links to a Class or a Job

### To create a Web menu item that links to a Class or a Job

1.  In the AOT, expand the **Web** node, and then expand the **Web Menu Items** node.

2.  Right-click **Actions**, and then click **New Action**.

3.  Right-click the action that you created in step 2, and then click **Properties**.

4.  In the property sheet, do the following:
    
    1.  Click **ObjectType**. Then, in the right column, select **Class** or **Job** in the drop-down menu, according to the type of action that you want the Web menu item to perform.
    
    2.  Click **Object**. Then, in the right column, select a class or job from the drop-down menu, according to the **ObjectType** property setting.

5.  Modify other properties as needed.

6.  Save the changes in the AOT.

## See also

[Menu Item Properties](https://msdn.microsoft.com/en-us/library/aa678720\(v=ax.60\))

[Web Menu Properties](https://msdn.microsoft.com/en-us/library/aa856237\(v=ax.60\))

