---
title: 'How to: Use Associated Forms Permissions'
TOCTitle: 'How to: Use Associated Forms Permissions'
ms:assetid: a470568b-1f4c-4fe3-ac99-f285d99a4421
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg846643(v=AX.60)
ms:contentKeyID: 35248382
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Use Associated Forms Permissions 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Suppose YourParentForm form has a button that opens YourAssociatedForm form. In such cases, permissions should be added so that YourAssociatedForm is accessible by users of YourParentForm. You can accomplish this by referencing YourAssociatedForm with a node that you add under  
 **AOT** \> **Forms** \> YourParentForm \> **Permissions** \> **Read** \> **Associated Forms**.

## Add X++ Code to Open the Associated Form

You can add a button to the YourParentForm form that uses X++ code to open the YourAssociatedForm form. The following code example shows how to open a form when the button is clicked.

    void clicked()
    {
        FormRun formRun;
        Args args;
        args = new Args("YourAssociatedForm");
        formRun = classFactory::formRunClassOnClient(args);
        formRun.run();
        formRun.wait();
    
        super();
    }

For information about how to add a button to a form, see [Walkthrough: Creating a Form by Using the AOT](walkthrough-creating-a-form-by-using-the-aot.md).

## Add a Node under Associated Forms

In this section, you use the AOT to add a node in the permissions section of YourParentForm form that specifies permissions for the YourAssociatedForm form The following steps show how to add the associated form:

1.  Expand **AOT** \> **Forms** \> YourParentForm \> **Permissions** \> **Read** \> **Associated Forms**.

2.  Right-click the **Associated Forms** node, and then click **New associated form**.

3.  In the **Properties** window for new associated form node, set the **Form** property to YourAssociatedForm.

4.  Set the **AccessLevel** property to **Read**.

## Next Steps

You can specify only potential permissions under  
 **AOT** \> **Forms** \> YourParentForm \> **Permissions**.  
To create actual permissions that can be associated to a role, you must reference the potential permissions under  
 **AOT** \> **Security** \> **Privileges**.

For more information, see [Automatic Inference of Permissions in AOT Security](automatic-inference-of-permissions-in-aot-security.md).

## See also

[Security Permissions Properties for a Form](security-permissions-properties-for-a-form.md)

[Assign users to security roles](https://msdn.microsoft.com/en-us/library/gg751367\(v=ax.60\))

[How to: Create Menus and Menu Items](how-to-create-menus-and-menu-items.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

