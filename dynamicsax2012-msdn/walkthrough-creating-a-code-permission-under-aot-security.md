---
title: 'Walkthrough: Creating a Code Permission under AOT Security'
TOCTitle: 'Walkthrough: Creating a Code Permission under AOT Security'
ms:assetid: c37f8b36-a8bb-4704-8d5c-4f8525d9c00d
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg880012(v=AX.60)
ms:contentKeyID: 35250126
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Walkthrough: Creating a Code Permission under AOT Security [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

You can use the Application Object Tree (AOT) to create code permission nodes that are located under **AOT** \> **Security**. A code permission enables a menu item to run code. When a menu item has its **ObjectType** property set to **Class**, the menu item is intended to run a method on a class.

A code permission is also necessary in some scenarios to run a service operation.

## Prerequisites

To understand this walkthrough topic, you first need to understand the following areas:

  - To implement and test security for this topic, you must act as a user in the roles of a developer, a system administrator, and an application user. For more information, see [How to: Test the Role-based Security Configurations under AOT Security](how-to-test-the-role-based-security-configurations-under-aot-security.md).

## Create a Project and a Test Class

Your project gathers the application objects you are currently working on. Your test class contains the methods that you can use to test code permissions.

1.  Create a private project named **CodePermissionsProject**.
    
    For information about how to create a project, see [How to: Create a MorphX Development Project](how-to-create-a-morphx-development-project.md).

2.  Create a class named **TestClass** in the **CodePermissionsProject** project.
    
    To create a new class, use **CodePermissionsProject** \> **New** \> **Class**. Rename the new class to **TestClass**.

3.  Create a method named main in the **TestClass** class.
    
    To create a new method, use **TestClass** \> **New** \> **Method**.
    
    Enter the following code into the code editor for the main method.
    
        static void main(Args _args)
        {
            AccountingDistribution ad;
        
            select * from ad;
            info(strFmt("The record type is %1.", ad.Type));
            TestClass::postGL();
            info('Completed the code permissions test.');
        }

4.  Create another method in the **TestClass** class.
    
    Enter the following code into the code editor for the postGL method.
    
        [SysEntryPointAttribute]
        server static void postGL()
        {
            info('The postGL method is called.');
        }
    
    The SysEntryPointAttribute attribute class is used by the system to identify methods that execute on the server tier. The system authenticates the application user who invokes these methods.

## Create a Code Permission

You can create a code permission by following these steps:

1.  Create a code permission that is named **TestCodePermission**. Create the permission in the **CodePermissionsProject** project.
    
    Create a code permission by right-clicking the **TestCodePermission** and navigating to **New** \> **Security** \> **Code Permission**. Rename the new code permission to **TestCodePermission**.

2.  Add the **AccountingDistribution** table to the **CodePermissionsProject** project by dragging the table node from **AOT** \> **Data Dictionary** \> **Tables** onto the project node.

3.  In the **Properties** window for the **AccountingDistribution** table, set the **AOSAuthorization** property to **CreateReadUpdateDelete**. Setting the **AOSAuthorization** table property to **CreateReadUpdateDelete** specifies that create, read, update, and delete data access operations must undergo user permission checking.

4.  Add the **AccountingDistribution** table to the **Tables** node of the **TestCodePermission** project.

5.  In the **Properties** window for the **AccountingDistribution** table, set the **EffectiveAccess** property to **Read**.

6.  Add the **TestClass::postGL** method to the **Server Methods** node of the **TestCodePermission** project.

7.  In the **Properties** window for the **TestClass::postGL** server method, set the following properties:
    
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
    <td><p><strong>Class</strong></p></td>
    <td><p>TestClass</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Method</strong></p></td>
    <td><p>postGL</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>EffectiveAccess</strong></p></td>
    <td><p><strong>Invoke</strong></p></td>
    </tr>
    </tbody>
    </table>


## Create a Menu Item Linked to a Code Permission

You can create a menu item by following these steps:

1.  Create the menu item **TestMenuItem** in the **CodePermissionsProject** project.
    
    Create a menu item by right-clicking the **CodePermissionsProject** and navigating to **New** \> **Menu Item** \> **Action**. Rename the new menu item to **TestMenuItem**.

2.  In the **Properties** window for the **TestMenuItem** menu item, set the properties to the values that are shown in the following table.
    
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
    <td><p><strong>Label</strong></p></td>
    <td><p>Code Permissions Test</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>ObjectType</strong></p></td>
    <td><p>Class</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Object</strong></p></td>
    <td><p>TestClass</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>LinkedPermissionType</strong></p></td>
    <td><p>CodePermission</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>LinkedPermissionObject</strong></p></td>
    <td><p>TestCodePermission</p></td>
    </tr>
    </tbody>
    </table>


3.  Add the menu item that you created to one of the existing menus. For example, you can add the menu item to **AOT** \> **Menus** \> **Home** \> **Common** by following these steps:
    
    1.  Drag the **AOT** \> **Menus** \> **Home** node onto the project node.
    
    2.  Drag **TestMenuItem** onto the **Home** \> **Common** node in the project.

## Create a Privilege for the Test Role

Create the **TestRole** role for an application user.

You can create a privilege for the test role by following these steps:

1.  Create a privilege **TestPrivilege** in the **CodePermissionsProject** project.
    
    Create a privilege by right-clicking the **CodePermissionsProject** and navigating to **New** \> **Security** \> **Privilege**. Rename the new privilege to **TestPrivilege**.

2.  Create an entry point that will be associated with the **TestMenuItem** menu item by right-clicking the **CodePermissionProject** project and navigating to **TestPrivilege** \> **Entry Points** \> **New Entry Point**. Rename the new entry point to **TestEntryPoint**.

3.  In the **Properties** window for the **TestEntryPoint** entry point, set the properties to the values that are shown in the following table.
    
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
    <td><p>MenuItemAction</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>ObjectName</strong></p></td>
    <td><p>TestMenuItem</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>AccessLevel</strong></p></td>
    <td><p>Delete</p></td>
    </tr>
    </tbody>
    </table>


4.  Add the **TestPrivilege** privilege to the **TestRole** role.
    
    Drag the **TestPrivilege** node onto the **TestRole** \> **Privileges** node.

## Review the Project

You have created all the items necessary for this walkthrough as shown in the following image.

![Code Permission](images/Gg880012.AOTCodePermission(en-us,AX.60).jpg "Code Permission")

**The project that you create**

## Use Your Code Permissions

As an application user, you can now verify that you can access your menu item and a server method. Follow these steps:

### ![Gg880012.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg880012.collapse_all(en-us,AX.60).gif")Correct Application Output

1.  Manually assign an application user to the **TestRole** by using the **System administration** form.
    
    For information about how to assign a user to a role, see [Assign users to security roles](https://msdn.microsoft.com/en-us/library/gg751367\(v=ax.60\)).

2.  Log on to the system as an application user and run the AX32.exe client application from the Command Prompt window.

3.  The **Workspace** window of an application user will contain the menu item **Code Permissions Test** as shown in the following image.
    
    ![Code Permissions Test menu item](images/Gg880012.AOTCodePermissionUserMenu(en-us,AX.60).jpg "Code Permissions Test menu item")
    
    **The application user menu**

4.  When you click **Code Permissions Test** you will see the code output to the **Infolog** as shown in the following image.
    
    ![Normal Output](images/Gg880012.AOTCodePermissionNormalOutput(en-us,AX.60).jpg "Normal Output")
    
    **The correct application output**

5.  Close the client application that you have started from the Command Prompt window.

### ![Gg880012.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg880012.collapse_all(en-us,AX.60).gif")Application Output Without the Code Permission for the Table

1.  Alter the code permission for the **AccountingDistribution** table by changing the table **EffectiveAccess** property value to **NoAccess**.

2.  Restart the client application from the Command Prompt window.

3.  When you click **Code Permissions Test** you will see the code output to the **Infolog** as shown in the following image.
    
    ![Table Access](images/Gg880012.AOTCodePermissionTableAccess(en-us,AX.60).jpg "Table Access")
    
    **The application output without the code permission for the table**
    
    From the **Infolog** error messages you can see that the application user is no longer authorized access to the **AccountingDistribution** table.

4.  Close the client application that you have started from the Command Prompt window.

5.  In the **Properties** window for the **AccountingDistribution** table set the **EffectiveAccess** property back to **Read**.

### ![Gg880012.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg880012.collapse_all(en-us,AX.60).gif")Application Output Without the Code Permission for the Method

1.  Remove the postGL method from the **TestCodePermission** code permission or, set the **EffectiveAccess** of the code permission to **NoAccess**.

2.  Restart the client application from the Command Prompt window.

3.  When you click **Code Permissions Test** you will see the code output to the **Infolog** as shown in the following image.
    
    ![Method access](images/Gg880012.AOTCodePermissionMethodAccess(en-us,AX.60).jpg "Method access")
    
    **The application output without the code permission for the method**
    
    From the **Infolog** error message you can see that the application user is no longer authorized access to the postGL method.

4.  Close the client application that you have started from the Command Prompt window.

5.  In the **Properties** window for the postGL method set the **EffectiveAccess** property back to **Invoke**.

### ![Gg880012.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg880012.collapse_all(en-us,AX.60).gif")Removing the Privilege from the Role

The application user menu will no longer contain the menu item **Code Permissions Test** if you remove the **TestPrivilege** privilege from the **TestRole** role, or if you set the **Enable** property of the privilege to **No**.

## See also

[Security Node Entities in the AOT](security-node-entities-in-the-aot.md)

[Security Code Permission Properties](security-code-permission-properties.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

