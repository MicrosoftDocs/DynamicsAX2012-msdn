---
title: 'Walkthrough: Quickly Creating and Deploying a User Control'
TOCTitle: 'Walkthrough: Quickly Creating and Deploying a User Control'
ms:assetid: 8d0c4398-02f9-479a-af6a-ad73b4064234
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh745329(v=AX.60)
ms:contentKeyID: 42607680
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# Walkthrough: Quickly Creating and Deploying a User Control [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

When you develop User Controls for use in Enterprise Portal, you will want to see results quickly. That can help you determine whether your development activities are on the appropriate track. This walkthrough demonstrates how to use the features in Microsoft Dynamics AX that help you quickly create and deploy User Controls to Enterprise Portal. These features are especially helpful when you are prototyping an integration for Enterprise Portal. The walkthrough illustrates the following tasks:

  - Creating an EP Web Application project.

  - Creating a User Control.

  - Deploying the User Control.

  - Viewing the User Control in Enterprise Portal.

## Prerequisites

To complete this walkthrough, you will need:

  - Microsoft Dynamics AX

  - Enterprise Portal

  - Visual Studio 2010

  - Visual Studio Tools from the Microsoft Dynamics AX installation

  - Enterprise Portal Administrator status

## Creating the EP Web Application Project

Visual Studio is used to create User Controls for Enterprise Portal.

### To create the EP Web Application project

1.  Start Visual Studio. If User Account Control (UAC) is active, make sure you start Visual Studio with administrative privileges. To do this, right-click the shortcut for Visual Studio and then click **Run as administrator**.

2.  In the **File** menu, click **New**, and then click **Project**.

3.  In the **New Project** window, select **.NET Framework 3.5** as the framework version to use.
    

    > [!IMPORTANT]
    > <P>For this release of Microsoft Dynamics AX, the EP Web Application project must target the .NET Framework 3.5 to work correctly.</P>



4.  In the **Installed Templates** list, select **Microsoft Dynamics AX**. If you do not see this project template, make sure that you have Visual Studio Tools for Microsoft Dynamics AX installed.

5.  Choose the EP Web Application template.

6.  Specify a name for the project, and the location of the folder where you want to store the files for the project.

7.  Click **OK** to create the project.

## Creating a User Control

For this walkthrough, you will create a User Control that displays a simple list of customers.

### To create a User Control

1.  In Visual Studio, use Solution Explorer to select the project you created.

2.  In the **Project** menu, click **Add New Item**.

3.  In the **Add New Item** window, expand the **Visual C\#** group of installed templates.

4.  Click **Microsoft Dynamics AX**, and then click the **EP User Control** template.

5.  For the User Control name, type QuickCustomerList.ascx.

6.  Click **Add**. The new User Control is added to the project.

7.  In Solution Explorer, right-click QuickCustomerList.ascx and then click **View Designer**.

8.  In the **Toolbox**, expand the **Dynamics AX** group. In that group, drag the **AxDataSource** component to the layout for the QuickCustomerList.

9.  The context menu for the AxDataSource component will be displayed. Set the **DataSet Name** to CustomerList. This indicates the data set that will be used to retrieve data for the User Control.

10. In the **Toolbox**, expand the **Dynamics AX** group. In that group, drag the **AxGridView** component to the layout for the QuickCustomerList.

11. The context menu for the AxGridView component will be displayed. Set the **Choose Data Source** value for the grid to AxDataSource1. This indicates that the grid will access data from the AxDataSource component that you had added to the User Control layout.

12. In the context menu for the AxGridView component, click **Edit Columns**. The **Bound Field Designer** appears.

13. In the **Bound Field Designer**, use the **Available Fields** list to locate the name\*\* field. Select this field, and then click **Add Field**.

14. Click **OK** to close the **Bound Field Designer**.

15. In the **File** menu, click **Save All**.

## Deploying the User Control

After the User Control has been created and saved, you can deploy it to Enterprise Portal to verify its functionality. Microsoft Dynamics AX provides functionality to speed this process when you are quickly prototyping User Controls.

### To deploy the User Control

1.  Open the Microsoft Dynamics AX client with administrative privileges. To do this, you must right-click on the icon for Microsoft Dynamics AX and then click **Run as administrator**.

2.  Open the Development Workspace.

3.  Display the AOT.

4.  In the AOT, expand the **Web** \> **Web Content** \> **Managed** node. This node contains all of the User Controls that have been defined for Enterprise Portal.

5.  In the list of managed components, locate the QuickCustomerList node. This is the managed content node for the User Control that you just created.

6.  Right-click the QuickCustomerList node, and then click **Deploy to EP**.

7.  The **Deploy to EP** dialog box is displayed. Set the **Web module lookup** to Home\\Sales to indicate that the new resources will be used in the Sales site for Enterprise Portal. Click **OK**.

8.  Microsoft Dynamics AX creates a SharePoint page named QuickCustomerList that is located in the Sales site. This page contains the customer list User Control that you created. Microsoft Dynamics AX also creates a web menu item named QuickCustomerList that points to the new page. Click **Close** to close the **Infolog**.

## Viewing the User Control in Enterprise Portal

After the page that contains the User Control has been created, you can view the page in Enterprise Portal.

### To view the User Control in Enterprise Portal

1.  Using a web browser, open Enterprise Portal. The typical URL to access Enterprise Portal is:
    
    http://\<server\>/sites/DynamicsAx/
    
    Substitute the name of the server on which Enterprise Portal is installed.

2.  Click **Sales** on the top link bar to display the Sales module site. This is the site that you deployed the new page to.

3.  In the **Site Actions** menu, click **View All Site Content**.

4.  In the **Document Libraries** section, click **Enterprise Portal**. This is the document library that pages for the Sales site are stored in.

5.  Locate the QuickCustomerList page in the list of pages for the Sales site. You will have to use the arrows at the bottom of the page to browse to see the additional pages in the site.

6.  Click the link for the QuickCustomerList page to display it in Enterprise Portal. After a few moments, you should see a page that contains the User Control you created, displaying a list of the customers in the current company.

## Next Steps

Recall that a web menu item was created when you deployed the User Control. Typically, you would add this web menu item to the navigation for Enterprise Portal, and then access the new page through standard Enterprise Portal navigation. See [Page-level Navigation Overview](page-level-navigation-overview.md) or [Walkthrough: Adding a Page to Navigation](walkthrough-adding-a-page-to-navigation.md) for more information about how to add the web menu item to the navigation.

## See also

[How to: Create an EP Web Application Project](how-to-create-an-ep-web-application-project.md)

[How to: Create User Controls](how-to-create-user-controls.md)

[Designing User Controls](designing-user-controls.md)

[How to: Create Pages](how-to-create-pages.md)

[How to: Add Web Parts](how-to-add-web-parts.md)

