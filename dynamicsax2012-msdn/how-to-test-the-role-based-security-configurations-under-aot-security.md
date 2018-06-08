---
title: 'How to: Test the Role-based Security Configurations under AOT Security'
TOCTitle: 'How to: Test the Role-based Security Configurations under AOT Security'
ms:assetid: 4480f84e-a7d8-4628-996b-0e910bad4387
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg845089(v=AX.60)
ms:contentKeyID: 35242959
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Test the Role-based Security Configurations under AOT Security 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

This topic explains how you can test the security configurations that are specified under the **Security** node in the AOT.

The user who installs the product is part of the **SYSADMIN** role. Users in the **SYSADMIN** role can access all tables and other resources regardless of the security settings. Therefore these users cannot test the security configurations. To test with limited permissions you will have to add application users.

## Roles for Testing

To implement and test security, you must act as a user in the roles of a developer, a system administrator, and an application user. The tasks for each user during testing are described in the following table.

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
<td><p>The developer has no tasks to perform during testing, unless an error is found. The developer configures the desired security before the test phase starts.</p></td>
</tr>
<tr class="even">
<td><p>System administrator</p></td>
<td><p>During testing the system administrator assigns an application user to the test roles.</p></td>
</tr>
<tr class="odd">
<td><p>Application user</p></td>
<td><p>The application user is a user who has limited permissions for accessing securable objects, such as tables, forms, and menu items.</p></td>
</tr>
</tbody>
</table>


## Use the System as an Application User

As a system administrator, you must create user accounts to use for testing. Before you can add a user to the list of Microsoft Dynamics AX users, the user must be listed in Active Directory in Microsoft Windows. For more information, see [Work with users from Active Directory](https://msdn.microsoft.com/en-us/library/aa497043\(v=ax.60\)).

After making sure that an application user exists in Active Directory in Microsoft Windows, you must add an application user to Microsoft Dynamics AX. For more information, see [Create new users in Microsoft Dynamics AX](https://msdn.microsoft.com/en-us/library/aa548139\(v=ax.60\)).

After adding the application user to Microsoft Dynamics AX, you must assign it to the application user test role.

The following steps describe how you can run the Microsoft Dynamics AX client as an application user.

1.  Open a Command Prompt window on the computer where you installed your Microsoft Dynamics AX system.

2.  Use the runas command to allow an application user to run the AX32.exe client application with permissions that differ from those of the current Windows user. Type the following code into the Command Prompt window, and then press the Enter key:
    
    runas /user:\<ApplicationUserDomain\>\\\<ApplicationUser\> Cmd.exe
    
    Execution of the runas code line opens a new Command Prompt window. The new window has the limited security permissions of the application user.

3.  When you are prompted, type the password of the application user.

4.  In the new window type Ax32.exe to run the client as the application user. Ax32.exe client program should be in the command path of your test system.

## See also

[Security Permissions for Securable Objects in the AOT](security-permissions-for-securable-objects-in-the-aot.md)

[Create new users in Microsoft Dynamics AX](https://msdn.microsoft.com/en-us/library/aa548139\(v=ax.60\))

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

