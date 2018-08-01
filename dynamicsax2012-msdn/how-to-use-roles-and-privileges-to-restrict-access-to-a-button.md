---
title: 'How to: Use Roles and Privileges to Restrict Access to a Button'
TOCTitle: 'How to: Use Roles and Privileges to Restrict Access to a Button'
ms:assetid: d00be82a-e2ed-4bdd-989b-5a4d1f96bfda
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg881160(v=AX.60)
ms:contentKeyID: 35251805
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Use Roles and Privileges to Restrict Access to a Button [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

You can use the **Security** section of the AOT to restrict access to specific controls on a form. When a user has access to a form, the default is that the user has access to all the controls on the form. You can override the default by adding permissions nodes for individual controls.

For example, you can set the **NeededPermission** property on a button to the value **Manual** to start the process of restricting access to the button control.

## Prerequisites

You need to understand the following concepts before you can understand this topic:

  - How to create a [form](walkthrough-creating-a-form-by-using-the-aot.md) with a button control on it.

  - How to create a [menu item](how-to-create-menus-and-menu-items.md) for your form.

  - How to create a security privilege with an [entry point](walkthrough-using-roles-and-privileges-to-control-access-to-forms.md) node underneath.

This topic assumes you already have a form, and a node for a corresponding menu item under **AOT** \> **Security** \> **Privileges** \> YourPrivilege \> **Entry Points**. For more information, see [Walkthrough: Design Permissions for a Form that is Started from a Menu Item](walkthrough-design-permissions-for-a-form-that-is-started-from-a-menu-item.md).

## Restricting Access to a Button

By following these steps you can restrict access to the button control on the form.

1.  In the AOT, highlight the button control node at **Forms** \> YourForm \> **Designs** \> **Design** \> YourButton.

2.  In the **Properties** window for your button control, set the **NeededPermission** property to **Manual**.  
    This enables you to drag the button node in the next step.

3.  Under the AOT node **Forms** \> YourForm \> **Permissions** \> **Read** \> **Controls**, add YourButton control. Do this by dragging the button node to this **Controls** node.

4.  In the **Properties** window for the new permission for YourButton control, set the **EffectiveAccess** property to **Read**.

## Testing the Restricted Access

In this section you test the security configuration for your control. For more information about the steps in this section, see [How to: Test the Role-based Security Configurations under AOT Security](how-to-test-the-role-based-security-configurations-under-aot-security.md).

You can test access to your control by following these steps:

1.  Manually assign an application user to YourTestRole using the **System administration** form.

2.  Sign on into the system as an application user.

3.  The **Workspace** window of an application user will contain your menu item.

4.  You should be able to open your form by clicking on your menu item. Notice that the button control appears on the form and you can operate the button.

5.  Sign off from the system as an application user.

6.  Manually remove YourTestRole from an application user using the **System administration** form.

7.  Sign on into the system as an application user again.

8.  When you open your form again you will notice that your button control no longer appears on the form.

## See also

[Security Permissions for Securable Objects in the AOT](security-permissions-for-securable-objects-in-the-aot.md)

[Walkthrough: Creating a Form by Using the AOT](walkthrough-creating-a-form-by-using-the-aot.md)

[How to: Create Menus and Menu Items](how-to-create-menus-and-menu-items.md)

[Assign users to security roles](https://msdn.microsoft.com/en-us/library/gg751367\(v=ax.60\))

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

