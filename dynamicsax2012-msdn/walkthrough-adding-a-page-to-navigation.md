---
title: 'Walkthrough: Adding a Page to Navigation'
TOCTitle: 'Walkthrough: Adding a Page to Navigation'
ms:assetid: bddd0978-688d-4edc-8dd0-c2888eadeed2
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc618510(v=AX.60)
ms:contentKeyID: 35246131
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# Walkthrough: Adding a Page to Navigation 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

When you create a page in Enterprise Portal, you will add it to the navigation to enable users to access it. This walkthrough demonstrates how to add the Tutorial\_MessagePrompt page to the Quick Launch navigation for the Sales module site in Enterprise Portal. It illustrates the following tasks:

  - Creating a Web Menu Item

  - Modifying the Quick Launch Menu

  - Viewing the Page in Enterprise Portal

## Prerequisites

To complete this walkthrough, you will need:

  - Microsoft Dynamics AX

  - Enterprise Portal

## Creating a Web Menu Item

A web menu item points to a specific page in Enterprise Portal. You must create a web menu item for each page that you will be adding to the navigation.

### To create a web menu item

1.  In the AOT, expand the **Web** node, and then expand the **Web Menu Items** node.

2.  Right-click **URLs**, and then click **New URL**.

3.  Right-click the new URL that you created in step 2, and then click **Properties**.

4.  Set the **Name** property to **MessagePromptTutorial**.

5.  Set the **Label** property to **Message Prompt Tutorial**.

6.  Specify the **URL** property, which has the following form:
    
    *Module*/Enterprise%20Portal/*PageName*.aspx
    
    The Tutorial\_MessagePrompt page is found in the main Enterprise Portal site, so it does not have a *Module* in its path. The value you must enter for the **URL** property to access the Tutorial\_MessagePrompt page is:
    
    Enterprise%20Portal/Tutorial\_MessagePrompt.aspx

7.  Right-click the new URL item, and then click **Save**.

## Modifying the Quick Launch Menu

To add menu items to the Quick Launch area for a module site, you must first determine which web menu resource is being used for the Quick Launch.

### To modify the Quick Launch menu

1.  In the AOT, expand the **Web** node, expand the **Web Modules** node, and then expand the **Home** node.

2.  Right-click the **Sales** node, and then click **Properties**.

3.  Examine the **QuickLaunch** property. It is set to **EPSalesQuickLaunch**. This is the web menu resource that defines the menu items displayed in the Quick Launch area for the Sales module site. You will add the new web menu item that you created to this web menu.

4.  In the AOT, expand the **Web** node, and then expand the **Web Menus** node.

5.  Locate and expand the **EPSalesQuickLaunch** node.

6.  Right-click the **Common** node. Click **New**, and then click **Menu item**. A new menu item will be added at the end of the list.

7.  Right-click the node for the new menu item, and then click **Properties**.

8.  Use the drop-down list for the **MenuItemName** property to select the **MessagePromptTutorial** menu item you created in the previous procedure.

9.  In the AOT, right-click the **EPSalesQuickLaunch** Web menu, and then click **Save**.

## Viewing the Page in Enterprise Portal

After you have added the menu item to the Quick Launch, you can view it in Enterprise Portal.

### To view the page in Enterprise Portal

1.  Using a web browser, open Enterprise Portal. The typical URL to access Enterprise Portal is:
    
    http://\<server\>/sites/DynamicsAx/
    
    Substitute the name of the server on which Enterprise Portal is installed.

2.  Click **Sales** on the top link bar to display the Sales module site.

3.  In the Quick Launch, examine the last item in the **Common** group. The **Message Prompt Tutorial** item should be listed.
    

    > [!TIP]
    > <P>If you do not see the new item in the list, the caches for Enterprise Portal may need to be refreshed. See <A href="troubleshooting-enterprise-portal-development.md">Troubleshooting: Enterprise Portal Development</A> for details about how to refresh the caches.</P>



4.  Click the **Message Prompt Tutorial** item to open the Tutorial\_MessagePrompt page.

## Next Steps

To learn more about navigation in Enterprise Portal, see [Enterprise Portal Site Structure and Navigation](enterprise-portal-site-structure-and-navigation.md).

## See also

[How to: Create Web Menu Items](how-to-create-web-menu-items.md)

[How to: Modify Page-level Navigation](how-to-modify-page-level-navigation.md)

