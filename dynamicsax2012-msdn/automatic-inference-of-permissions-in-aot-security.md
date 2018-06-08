---
title: Automatic Inference of Permissions in AOT Security
TOCTitle: Automatic Inference of Permissions in AOT Security
ms:assetid: 96d9f60c-9b92-403c-ba02-11639c6d1e3a
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg841928(v=AX.60)
ms:contentKeyID: 35247708
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Automatic Inference of Permissions in AOT Security 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

This security topic describes the automatic inference engine for permissions in the AOT of Microsoft Dynamics AX. It also describes how a developer uses the outputs of automatic inference to create privileges that the administrator can assign to a role.

## Automatic Inference for a Form

When you save a form in the AOT, the system automatically discovers all the tables and other items that must be accessed by the form. Those items are listed under nodes that the system automatically adds under the MyForm \> **Permissions** node. The system automatically adds, or updates, the following nodes under the **AOT** \> **Forms** \> MyForm \> **Permissions** node:

  - **Read**

  - **Update**

  - **Create**

  - **Correct** – added only if [valid time state](valid-time-state-tables-and-date-effective-data.md) tables are involved.

  - **Delete**

### ![Gg841928.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg841928.collapse_all(en-us,AX.60).gif")Permission Sets

Each node in the preceding list contains a set of permissions. For example, suppose the **CustTable** table is used by the form. Under the **Permissions** \> **Update** node, there is a **CustTable** node. The **CustTable** node has its **EffectiveAccess** property set to **Update**. All items under the **Permissions** \> **Update** node have their **EffectiveAccess** property set to **Update**. The system has automatically inferred that the set of permissions under the **Permissions** \> **Update** node might be helpful to any developer who must use permissions to create privileges for this form.

This part of the AOT is captured in the following screen shot. The following screen shot shows that nodes under the **Permissions** \> **Delete** node have a **DefaultAccess** property value of **Delete**.

 

![Automatically inferred permissions under a form no](images/Gg841928.AOTSecurity-(en-us,AX.60).gif "Automatically inferred permissions under a form no")

**Automatically inferred permission sets under a form node in the AOT**

### ![Gg841928.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg841928.collapse_all(en-us,AX.60).gif")Hierarchy of Permissions

The permission values for the **EffectiveAccess** property represent a hierarchy. **Read** is the weakest permission, and **Delete** is the strongest. **Delete** permission includes every other permission. **Create** permission includes **Update** and **Read**. In the following ordered list of permissions, each permission includes all those that occur earlier in the list:

1.  **Read**

2.  **Update**

3.  **Create**

4.  **Correct**

5.  **Delete**

### ![Gg841928.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg841928.collapse_all(en-us,AX.60).gif")NoAccess

Suppose you do not want the **Delete** permission set to support delete operations on a particular table that is under the node **AOT** \> **Forms** \> MyForm \> **Permissions** \> **Delete** \> **Tables**. You should set the **EffectiveAccess** property to **NoAccess** on the **Delete** \> **Tables** \> MyTable node.


> [!WARNING]
> <P>If instead you delete the MyTable node, the MyTable node will be added back automatically the next time someone expands the <STRONG>Delete</STRONG> &gt; <STRONG>Tables</STRONG> node in the AOT.</P>



## Modify a Permission Set

You can modify the values of the permission properties on nodes such as **AOT** \> **Forms** \> MyForm \> **Permissions** \> **Update** \> **Tables** \> MyTable. For example, the **Update** node might be almost perfect for your needs, except one table might not need to be updatable. Read permission might be sufficient.

On the **AOT** \> **Forms** \> MyForm \> **Permissions**\> **Update** \> **Tables** \> MyTable node, you change the **EffectiveAccess** property from **Update** to **Read**. Now the **EffectiveAccess** and **DefaultAccess** properties have different values. This difference automatically changes the **SystemManaged** property from **Yes** to **No**.


> [!NOTE]
> <P>The <STRONG>ManagedBy</STRONG> field should be updated only by automation tools.</P>



### ![Gg841928.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg841928.collapse_all(en-us,AX.60).gif")Suppress a Permissions Set

You can choose which permission sets that the automatic inference engine creates. You do this by setting property values on the node **AOT** \> **Forms** \> MyForm \> **Permissions**. These properties are shown on the Properties tab in the following image.

 

![Properties that control which permission sets are](images/Gg841928.AOTSecurity-PermissionsNodeUnderMyForm(en-us,AX.60).jpg "Properties that control which permission sets are")

**Properties that control which permission sets are built by automatic inference**

## Menu Item Option to Block Permission Sets from Form

A menu item provides a mechanism to start a form. Security properties on the menu item control which sets of form permissions will be available to select when privileges are assigned to the menu item.

Each menu item has the following security properties:

  - **ReadPermissions**

  - **UpdatePermissions**

  - **CreatePermissions**

  - **CorrectPermissions**

  - **DeletePermissions**

These properties refer to the nodes under **AOT** \> **Forms** \> MyForm \> **Permissions**.

For example, the **UpdatePermissions** property refers to the node **AOT** \> **Forms** \> MyForm \> **Permissions** \> **Update**.

The available values for each of these permission properties are described in the following table:

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Property value</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Auto</strong></p></td>
<td><p>Is the default. <strong>Auto</strong> means the corresponding set of form permissions will be available to select as privileges on this menu item.</p>
<p>The privileges will be selected on the privilege node for this menu item that will be under the <strong>Entry Points</strong> node. The path of this menu item privilege node is <strong>AOT</strong> &gt; <strong>Security</strong> &gt; <strong>Privileges</strong> &gt; MyPrivilege &gt; <strong>Entry Points</strong> &gt; MyMenuItem.</p>
<p>For example, if the <strong>UpdatePermissions</strong> property is set to <strong>Auto</strong>, the permission set under the node MyForm &gt; <strong>Permissions</strong> &gt; <strong>Update</strong> will be available to select for privileges under <strong>AOT</strong> &gt; <strong>Security</strong>.</p></td>
</tr>
<tr class="even">
<td><p><strong>No</strong></p></td>
<td><p>Means the opposite of <strong>Auto</strong>. The corresponding permission set will not be available to select as a privilege on the menu item privilege node under the <strong>Entry Points</strong> node.</p></td>
</tr>
</tbody>
</table>

 

![The UpdatePermissions property of a menu item](images/Gg841928.AOTSecurity-MenuitemFormProperties(en-us,AX.60).gif "The UpdatePermissions property of a menu item")

**The UpdatePermissions property of a menu item**

## Assigning Permissions to Privileges under AOT \> Security

The node **AOT** \> **Security** \> **Privileges** \> MyPrivilege \> **Entry Points** \> MyEntryPoint must be added for the menu item that references the form. The node has an **AccessLevel** property with a drop-down list that contains some or all of the following values:

  - **NoAccess**

  - **Read**

  - **Update**

  - **Create**

  - **Correct**

  - **Delete**

For example, the drop-down list contains the **Create** value if, but only if, the **CreatePermissions** property of the menu item node under **AOT** \> **Menu Items** is set to **Auto**, and there is a **Create** node under **AOT** \> **Forms** \> MyForm \> **Permissions**.

The **AccessLevel** value determines which node under **AOT** \> **Forms** \> MyForm \> **Permissions** defines the security permissions for this privilege.

 

![The assignment of privileges from eligible permiss](images/Gg841928.AOTSecurity-PrivilegeEntrypoint(en-us,AX.60).gif "The assignment of privileges from eligible permiss")

**Selecting the permission set for the privilege**

### ![Gg841928.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg841928.collapse_all(en-us,AX.60).gif")EffectiveAccess and AccessLevel Properties Values

The properties **EffectiveAccess** and **AccessLevel** have the same drop-down list of values. However, these two properties are not similar.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Property name</p></th>
<th><p>Where exists</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>EffectiveAccess</strong></p></td>
<td><p>A property on the nodes such as <strong>AOT</strong> &gt; <strong>Forms</strong> &gt; MyForm &gt; <strong>Permissions</strong> &gt; <strong>Tables</strong> &gt; MyTable.</p></td>
<td><p>Operations that users in a security role can perform, if the role is granted a privilege or duty that contains this permission.</p></td>
</tr>
<tr class="even">
<td><p><strong>AccessLevel</strong></p></td>
<td><p>A property on nodes such as <strong>AOT</strong> &gt; <strong>Security</strong> &gt; <strong>Privileges</strong> &gt; MyPrivilege &gt; <strong>Entry Points</strong> &gt; MyEntryPoint, which is often a menu item.</p></td>
<td><p>Identifies a permission set under <strong>AOT</strong> &gt; <strong>Forms</strong> &gt; MyForm &gt; <strong>Permissions</strong>, or under similar nodes on other AOT elements other than forms.</p>
<p>Forms are one type of securable object.</p></td>
</tr>
</tbody>
</table>


## Sequence of Using Automatically Inferred Permissions

There is a sequence associated with the automatic inference of permissions. The following diagram illustrates the sequence.

![Sequence from automatic inference of permisions](images/Gg841928.SecurityAutoInferSeq0(en-us,AX.60).png "Sequence from automatic inference of permisions")

**The sequence of using automatically inferred permissions.**

Some permissions sets are described in AOT nodes under **Forms** \> YourForm \> **Permissions**. The initial descriptions are automatically inferred by the Microsoft Dynamics AX system, to save you the effort. You can edit the initial inferred values if necessary. These sets of described permissions are not yet real permissions, they are merely descriptions of possible permissions. These sets are named Read, Update, Create, Correct, and Delete.

On YourMenuItem for the form, you specify which of the described permissions sets this menu item will allow to possibly become real permissions. For example, a menu item that is named ReadTheAccount might be confusing and misleading if it allowed the **UpdatePermissions**. Read and update are different concepts.

The menu item entry point under YourPrivilege has an **AccessLevel** property. The drop-down list of values for that property contains the permissions description sets that YourMenuItem allows. Of course, other menu items could allow more permissions description sets for the form.

## See also

[Role-based Security in the AOT for Developers](role-based-security-in-the-aot-for-developers.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

