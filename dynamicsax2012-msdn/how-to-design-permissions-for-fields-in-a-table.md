---
title: 'How to: Design Permissions for Fields in a Table'
TOCTitle: 'How to: Design Permissions for Fields in a Table'
ms:assetid: 7dc11486-5cb6-4270-b986-8e8cb058645f
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh272122(v=AX.60)
ms:contentKeyID: 36536819
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Design Permissions for Fields in a Table 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

You can use the AOT to design permissions for the fields in a table. By changing the **EffectiveAccess** property in permissions for each of the fields you can control the application user access to those fields. For example, you can control whether the application user can view or edit some of the fields on a form based on the security role assigned to the application user.

## Prerequisites

To understand this walkthrough topic, you first need to understand the following areas:

  - [Walkthrough: Design Permissions for a Form that is Started from a Menu Item](walkthrough-design-permissions-for-a-form-that-is-started-from-a-menu-item.md)   
    You must understand how to add a menu item under **AOT** \> **Security** \> **Privileges** \> YourPrivilege \> **Entry Points**.

  - [Automatic Inference of Permissions in AOT Security](automatic-inference-of-permissions-in-aot-security.md)   
    When you set security property values under **AOT** \> **Security** \> **Privilege**, you need to understand what those values refer to elsewhere in the AOT.

## Preliminary Environment

This topic assumes that several AOT items already exist, or that you can imagine them. The items are as follows:

  - Table – **Person** table, with fields **City**, **Name**, and **Zip**.

  - Form – **FieldsForm** form.

  - Data source – **Person** table as the data source for **FieldsForm** form.

  - Menu – **Home** \> **Common** menu, which might already exist.

  - Menu Item – **FieldsMenuItem** menu item, with its **ObjectType** property set to **Form**, and its **Object** property set to **FieldsForm**.

  - Security \> Privilege – **TestFieldPrivilege** privilege.

  - Privilege \> TestFieldPrivilege \> Entry Point – **FieldsMenuItem**, with its **ObjectType** property set to **MenuItemDisplay**.  
    You can test with different values for the **AccessLevel** property, but start with **Update**.

The following image displays a project that contains almost everything in the preceding list. In the next section you create the node **AOT** \> **Security** \> **Privileges** \> **Permissions** \> **Tables** \> **Person**, and the field nodes under it.

![AOTSecurityFieldsPermProject](images/Hh272122.AOTSecurityFieldsPermProject(en-us,AX.60).jpg "AOTSecurityFieldsPermProject")

**The project that you create**

## Create Field Permissions

You can create field permissions for **TestFieldPrivilege** by following these steps:

1.    
    Add the **Person** table to the **TestFieldPrivilege** privilege. Do this by dragging the node  
     **AOT** \> **Data Dictionary** \> **Tables** \> **Person**   
    onto the node at  
     **AOT** \> **Security** \> **Privileges** \> **TestFormPrivilege** \> **Permissions** \> **Tables**.
    

    > [!TIP]
    > <P>Drag operations are easier when you have two AOT windows open. You can drag from one AOT to the other.</P>



2.  On the new **Person** node, set the **EffectiveAccess** property to **Update**.

3.  At **Data Dictionary** \> **Tables** \> **Person** \> **Fields**, highlight all fields and drag them onto the **TestFieldPrivilege** \> **Permissions** \> **Tables** \> **Person** node.

4.  Set the **EffectiveAccess** property for each new field node as follows:
    
      - City – Update
    
      - Name – Read
    
      - Zip – NoAccess

## Next Steps

You can test your security settings by starting the Microsoft Dynamics AX client as a user other than the system administrator. For more information, see [How to: Test the Role-based Security Configurations under AOT Security](how-to-test-the-role-based-security-configurations-under-aot-security.md).

## See also

[Security Permissions Properties for a Form](security-permissions-properties-for-a-form.md)

[How to: Test the Role-based Security Configurations under AOT Security](how-to-test-the-role-based-security-configurations-under-aot-security.md)

[How to: Create a MorphX Development Project](how-to-create-a-morphx-development-project.md)

[Walkthrough: Creating a Form by Using the AOT](walkthrough-creating-a-form-by-using-the-aot.md)

[Walkthrough: Using Roles and Privileges to Control Access to Forms](walkthrough-using-roles-and-privileges-to-control-access-to-forms.md)

[How to: Create Tables](how-to-create-tables.md)

[Assign users to security roles](https://msdn.microsoft.com/en-us/library/gg751367\(v=ax.60\))

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

