---
title: 'Walkthrough: Adding a Field to a User Control'
TOCTitle: 'Walkthrough: Adding a Field to a User Control'
ms:assetid: 6f456230-80ba-41ac-a324-a35e259808b3
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc556964(v=AX.60)
ms:contentKeyID: 35245385
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# Walkthrough: Adding a Field to a User Control [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Enterprise Portal contains numerous entity overview pages that display detailed data for specific items in Microsoft Dynamics AX. For example, the **View customer** page displays detailed information about a customer. A User Control displayed in a User Control web part is used to display the data on the page. The AxForm is the main component of the User Control used for the **View customer** page.

A common customization is adding or changing the fields that are displayed in an entity overview page. This walkthrough demonstrates how to add a field to the first group that appears on the **View customer** entity overview page. It illustrates the following tasks:

  - Determining the User Control to modify.

  - Creating an EP Web Application project.

  - Adding a User Control to the EP Web Application project.

  - Modifying a User Control.

  - Viewing the customization in Enterprise Portal.

## Prerequisites

To complete this walkthrough, you will need:

  - Microsoft Dynamics AX

  - Enterprise Portal

  - Visual Studio 2010

  - Visual Studio Tools from the Microsoft Dynamics AX installation

  - Enterprise Portal Administrator status

## Determining the User Control to Modify

Before you can modify the fields displayed on the **View customer** page, you must determine which User Control is being used for that page.

### To determine the User Control to modify

1.  Using a web browser, open Enterprise Portal. The typical URL to access Enterprise Portal is:
    
    http://\<server\>/sites/DynamicsAx/
    
    Substitute the name of the server on which Enterprise Portal is installed.

2.  Display the **All Customers** list page. Click **Sales** on the top link bar. Select one of the customers in the list, and then click **View**. The **View customer** page with customer information is displayed.

3.  In the ribbon, display the **Page** tab.

4.  Click the **Edit Page** command.

5.  Locate the **View customer** web part in the middle column. In the drop-down menu for this web part, click **Edit Web Part**. The drop-down menu is the small arrow found on the upper-right corner of the web part.

6.  In the list of properties for the web part, locate the **Managed content item** property. It is set to **CustomerOverview**, which is the User Control that is being displayed in the web part. This is the User Control that will be modified.

7.  Click **Cancel** to close the list of web part properties.

8.  Click **Stop Editing** to return to the **View customer** page. Close the page.

## Creating the EP Web Application Project

Visual Studio is used to modify User Controls for Enterprise Portal.

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

## Adding the User Control to the EP Web Application Project

You must add the User Control to the EP Web Application project so that you can modify the User Control's properties.

### To add the User Control to the EP Web Application project

1.  In the **View** menu in Visual Studio, click **Application Explorer**.

2.  In the **Application Explorer**, expand the **Web** \> **Web Files** \> **Web Controls** node.

3.  In the **Web Controls** list, locate the **CustomerOverview** control.

4.  Right-click the **CustomerOverview** control, and then click **Add to project**. The control and several related controls are added to the project.

5.  Close the **Application Explorer**.

## Modifying the User Control

Use Visual Studio to make changes to the User Control.

### To modify the User Control

1.  Locate the **CustomerOverview.ascx** component in **Solution Explorer**.

2.  Right-click the **CustomerOverview** component in **Solution Explorer**, and then click **View Designer**.
    
    After a few moments, you will see several components in the control layout. The AxDataSource component is used to access data for the customer overview page. The AxMultiSection component contains all of the expandable sections that you see in the **View customer** page. The sections contain AxGroup components, which are used to display fields.

3.  Click the **Customer** AxGroup component directly in the layout to select it. This component contains the fields that are displayed at the top of the **General** section of the **View customer** page.

4.  To modify the fields that are displayed in the group, use one of the following methods:
    
    Display the context menu at the upper-right corner of the AxGroup control in the layout. Click **Edit Fields** to display the **Bound Field Designer**.
    
    \-or-
    
    Locate the **Fields** property in the Properties list. Click the ellipsis button to display the **Bound Field Designer**.

5.  The **Selected Field** list contains the fields that appear in the group. Only the AccountNum field is included. In the **Available Fields** list, select the **OrderEntryDeadlineGroupId** field. Click **Add Field** to add this field to the list of fields that will be displayed in the group.

6.  Make sure that the **OrderEntryDeadlineGroupId** field is selected in the **Selected Field** list.

7.  In the **BoundField Properties** list, locate the **HeaderText** property. Set the value of this property to **Order entry deadline:**.

8.  Click **OK** to save the changes to the list of fields for the AxGroup.

9.  In the **File** menu, click **Save CustomerOverview.ascx** to save the changes you made to the User Control. The changes are exported automatically to the AOT. The updated User Control is also deployed to the Enterprise Portal server.

## Viewing the Customization in Enterprise Portal

After the field has been added to the User Control, you can view it in Enterprise Portal.

### To view the customization in Enterprise Portal

1.  Using a web browser, open Enterprise Portal.

2.  Click **Sales** on the top link bar. Display the **All Customers** list page. Select one of the customers in the list, and then click **View**. The **View customer** page with the customer information is displayed. You will see the customer details, including the **Order entry deadline** field that you added.

## Next Steps

To learn more about User Controls in Enterprise Portal, see [User Controls Overview](user-controls-overview.md).

## See also

[How to: Set Up Visual Studio for Enterprise Portal Development](how-to-set-up-visual-studio-for-enterprise-portal-development.md)

[How to: Create an EP Web Application Project](how-to-create-an-ep-web-application-project.md)

[How to: Modify User Controls](how-to-modify-user-controls.md)

