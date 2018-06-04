---
title: 'Walkthrough: Using Roles and Privileges to Control Access to Forms'
TOCTitle: 'Walkthrough: Using Roles and Privileges to Control Access to Forms'
ms:assetid: 4b230cc7-18ec-481d-8791-06e866f5b663
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg840278(v=AX.60)
ms:contentKeyID: 35243277
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Walkthrough: Using Roles and Privileges to Control Access to Forms 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

You can use the Application Object Tree (AOT) to create roles and privileges to control access to forms.

## Setup

In implementing this walkthrough you must act as a developer, a system administrator, and an application user as described in the following table.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Role</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Developer</p></td>
<td><p>The developer does the following:</p>
<ul>
<li><p>Creates a form and a menu item for a form.</p></li>
<li><p>Creates a privilege and an entry point.</p></li>
<li><p>Creates a test role for the application user.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>System administrator</p></td>
<td><p>The system administrator assigns an application user to the test role.</p></td>
</tr>
<tr class="odd">
<td><p>Application user</p></td>
<td><p>The application user does the following:</p>
<ul>
<li><p>Signs on into the system as an application user.</p></li>
<li><p>Opens the form.</p></li>
</ul></td>
</tr>
</tbody>
</table>


## Create a Form and a Menu Item

You can create a form and a menu item by following these steps:

1.  Under **AOT** \> **Forms**, create a form that is named **MyNewForm**.
    
    For information on how to create a form, see [Walkthrough: Creating a Form by Using the AOT](walkthrough-creating-a-form-by-using-the-aot.md).

2.  Under **AOT** \> **Menu Items**, create a menu item named **MyMenuItem** for this form.
    
    For information on how to create a menu item, see [How to: Create Menus and Menu Items](how-to-create-menus-and-menu-items.md).

3.  Add the menu item you created to one of the existing **Menus**. For example, you can add it to **AOT** \> **Menus** \> **Home** \> **Common**.
    
    The following figure shows the form and the menu item that you create in this walkthrough.
    
    ![The form and menu item that you create.](images/Gg840278.AOTSecurityFormAccess(en-us,AX.60).jpg "The form and menu item that you create.")
    
    **The form and menu item that you create.**

## Create a Privilege and an Entry Point

You can create a privilege and an entry point for **MyMenuItem** by following these steps:

1.  Create a privilege that is named **MyNewPrivilege**.

2.  Expand **AOT** \> **Security** \> **Privileges** \> **MyNewPrivilege**.

3.  Add an entry point that is named **MyNewEntryPoint**. You do this by right-clicking the **Entry Points** node, and then clicking **New Entry Point**.

4.  In the **Properties** window for the new entry point, do the following:
    
    1.  Set the **Name** property to **MyNewEntryPoint**.
    
    2.  Make the **ObjectType** of the entry point be **MenuItemDisplay**.
    
    3.  Make the **ObjectName** of the entry point be **MyMenuItem**.
    
    4.  Set the **AccessLevel** of the entry point to **Read**.

## Create a Test Role

To properly test your form as an application user, you must create a test role. You can create a test role by following these steps:

1.  Create a test role for an application user that is named **TestRole**.

2.  Expand **AOT** \> **Security** \> **Roles** \> **TestRole** \> **Privileges**.

3.  Add **MyNewPrivilege** privilege to the **Privileges** node of **TestRole**.
    
    The following figure shows a test role with a privilege that you create in this walkthrough.
    
    ![A test role with a privilege](images/Gg840278.AOTSecurityFormAccess2(en-us,AX.60).jpg "A test role with a privilege")
    
    **The test role with a privilege that you create.**

## Test Your Form

At this point in this walkthrough you have created your form, the menu item for your form, and the test role. Now you are ready to test the access to your form for an application user.

You can test your form by following these steps:

1.  Manually assign an application user to the **TestRole** by using the **System administration** form.
    
    For information on how to assign a user to a role, see [Assign users to security roles](https://msdn.microsoft.com/en-us/library/gg751367\(v=ax.60\)).

2.  Log on the system as an application user.

3.  The **Workspace** window of an application user will contain the menu item **MyMenuItem**.

4.  You should be able to open **MyNewForm** by clicking on **MyMenuItem**.

5.  Log off the system as an application user.

6.  Manually remove **TestRole** from an application user using the **System administration** form.

7.  Log on the system as an application user again.

8.  The **Workspace** window of an application user will no longer contain the menu item **MyMenuItem**.

## See also

[Security Permissions for Securable Objects in the AOT](security-permissions-for-securable-objects-in-the-aot.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

