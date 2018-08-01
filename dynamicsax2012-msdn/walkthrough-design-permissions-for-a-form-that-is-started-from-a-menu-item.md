---
title: 'Walkthrough: Design Permissions for a Form that is Started from a Menu Item'
TOCTitle: 'Walkthrough: Design Permissions for a Form that is Started from a Menu Item'
ms:assetid: 379c66ad-e9cd-47b3-98cd-ba6bc8a83a19
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg844726(v=AX.60)
ms:contentKeyID: 35242056
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Walkthrough: Design Permissions for a Form that is Started from a Menu Item [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

You can use the AOT to design permissions for forms. A menu item that refers to the form can inherit which ever permissions are appropriate from the permissions that are designed on the form.

## Create a Project for Your Form

Create a private project named **FormPermissionsProject**. Your project gathers the application objects you are currently working on. For information about how to create a project, see [How to: Create a MorphX Development Project](how-to-create-a-morphx-development-project.md).

## Create a Table for Your Form

For this walkthrough you create your own table in the AOT. One reason not to use an existing system table is that it already has security roles associated to it. The related security roles will alter the permissions for your table. To examine the related security roles for a table you can select a table in **AOT** \> **Data Dictionary** \> **Tables**, and then right-click the **Add-Ins** \> **Security tools** \> **View related security roles**. Only the security role you associate to your table will display in the **Roles related to table** form.

  - Create a table named **Person** with fields named **Name**, **City**, and **Zip**. Add several records.
    
    For information on how to create a new table, see [How to: Create Tables](how-to-create-tables.md).  
    To add a new record to a table, right-click the table, click **Open** to open the **Table browser** form, and then press Ctrl+N.

## Create a Form and Design Permissions on a Form

For information on how to create a new form and add a data source, see [Walkthrough: Creating a Form by Using the AOT](walkthrough-creating-a-form-by-using-the-aot.md).

1.  Create a new form **PersonForm**.

2.  Add a data source to the form. Set the data source **Table** property to the **Person** table.

3.  In the **AOT** \> **Forms**, find the **PersonForm** form and click the **Permissions** node.

4.  In the **Properties** window set permission properties for your form. For example, leave the **ReadPermissions** property set to **Yes**, and change all other permission values to **No**.

## Create a Menu Item for Your Form

You can create a menu item by following these steps:

1.  Create the **PersonFormMenuItem** menu item for your form by completing the steps in [How to: Create Menus and Menu Items](how-to-create-menus-and-menu-items.md).

2.  Select the menu item that you created and look at its ReadPermissions and its similar permission properties, and see they are all set to **Auto**.
    
    Because the menu item points to the form, the system automatically interprets the **Auto** value of the menu item’s permissions to be the same value as the value on the form. In our example, we have specified **Auto** for the **ReadPermissions** property on the form, and **No** for all other permissions properties.

3.  Add the menu item that you created to one of the existing menus. For example, you can add the menu item to **AOT** \> **Menus** \> **Home** \> **Common** by following these steps:
    
    1.  Drag the **AOT** \> **Menus** \> **Home** node onto the project node.
    
    2.  Drag **PersonFormMenuItem** onto the **Home** \> **Common** node in the project.

## Create a Test Role and a Privilege

Create the **TestFormRole** role for an application user.

You can create a privilege for the test role by following these steps:

1.  Create a privilege **TestFormPrivilege** in the **FormPermissionsProject** project by right-clicking the **FormPermissionsProject** and navigating to **New** \> **Security** \> **Privilege**.  
    Rename the new privilege to **TestFormPrivilege**.

2.  Create an entry point that will be associated with the **PersonFormMenuItem** menu item by right-clicking the **FormPermissionsProject** project and navigating to **TestFormPrivilege** \> **Entry Points** \> **New Entry Point**.  
    Rename the new entry point to **TestFormEntryPoint**.

3.  In the **Properties** window for the **TestFormEntryPoint** entry point, set the properties to the values that are shown in the following table.
    
    <table>
    <colgroup>
    <col style="width: 50%" />
    <col style="width: 50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th><p>Property</p></th>
    <th><p>Value</p></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td><p><strong>ObjectType</strong></p></td>
    <td><p>MenuItemDisplay</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>ObjectName</strong></p></td>
    <td><p>PersonFormMenuItem</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>AccessLevel</strong></p></td>
    <td><p>Read</p></td>
    </tr>
    </tbody>
    </table>


4.  Add the **TestFormPrivilege** privilege to the **TestFormRole** role by dragging the **TestFormPrivilege** node onto the **TestFormRole** \> **Privileges** node.

## Review the Project

You have created all the items necessary for this walkthrough as shown in the following image.

![AOTSecurityFormMenuItem](images/Gg844726.AOTSecurityFormMenuItem(en-us,AX.60).jpg "AOTSecurityFormMenuItem")

**The project that you create**

## Use Your Code Permissions

To test security for this topic, you must act as a user in the role of an application user. For more information, see [How to: Test the Role-based Security Configurations under AOT Security](how-to-test-the-role-based-security-configurations-under-aot-security.md).

### ![Gg844726.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg844726.collapse_all(en-us,AX.60).gif")Correct Application Output

1.  Manually assign an application user to the **TestFormRole** by using the system administration form. For information about how to assign a user to a role, see [Assign users to security roles](https://msdn.microsoft.com/en-us/library/gg751367\(v=ax.60\)).

2.  Log on to the system as an application user and run the AX32.exe client application from the Command Prompt window.

3.  The **Workspace** window of an application user will contain the menu item **People Form** as shown in the following image.
    
    ![AOTSecurityFormMenuItemUserMenu](images/Gg844726.AOTSecurityFormMenuItemUserMenu(en-us,AX.60).jpg "AOTSecurityFormMenuItemUserMenu")
    
    **The application user menu**

4.  When you click **People Form** you will see the **People** form as shown in the following image.
    
    ![AOTSecurityFormMenuItemNormal](images/Gg844726.AOTSecurityFormMenuItemNormal(en-us,AX.60).jpg "AOTSecurityFormMenuItemNormal")
    
    **The correct application output**

5.  Close the client application that you have started from the Command Prompt window.

### ![Gg844726.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg844726.collapse_all(en-us,AX.60).gif")Application Output without the Permission for the Table

1.  In the **Properties** window for the **PersonFormMenuItem** menu item change the **ReadPermissions** property to **No**.

2.  Restart the client application from the Command Prompt window.

3.  When you click **People Form** you will see the code output to the **Infolog** as shown in the following image.
    
    ![AOTSecurityFormMenuItemError](images/Gg844726.AOTSecurityFormMenuItemError(en-us,AX.60).jpg "AOTSecurityFormMenuItemError")
    
    **The application output without the code permission for the table**
    
    From the **Infolog** error messages you can see that the application user is no longer authorized access to the **People** table.

4.  Close the client application that you have started from the Command Prompt window.

5.  In the **Properties** window for the **PersonFormMenuItem** menu item change the **ReadPermissions** property back to **Auto**.

### ![Gg844726.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg844726.collapse_all(en-us,AX.60).gif")Controlling Access to the Form through the Entry Point or the Privilege

You can remove access to the form by using one of the following methods. The application user menu will no longer contain the menu item **People Form**.

1.  Change the **PersonFormMenuItem** entry point **AccessLevel** property value to **NoAccess**.

2.  Remove the **TestFormPrivilege** privilege from the **TestFormRole** role, or set the **Enable** property of the privilege to **No**.

## See also

[Security Permissions for Securable Objects in the AOT](security-permissions-for-securable-objects-in-the-aot.md)

[Walkthrough: Creating a Form by Using the AOT](walkthrough-creating-a-form-by-using-the-aot.md)

[How to: Create Menus and Menu Items](how-to-create-menus-and-menu-items.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

