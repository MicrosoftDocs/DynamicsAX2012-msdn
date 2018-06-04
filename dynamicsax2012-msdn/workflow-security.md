---
title: Workflow Security
TOCTitle: Workflow Security
ms:assetid: e7dbce07-e1a0-4d08-9bd5-cb9ccc1766ff
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc641033(v=AX.60)
ms:contentKeyID: 35253224
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Workflow Security 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Security in workflow is part of the standard security implementation in Microsoft Dynamics AX. This topic describes specific workflow security considerations.

## Workflow Resources

Availability of workflow resources is controlled by configuration keys. Resources like workflow types, tasks, and approvals have the **ConfigurationKey** property that you can set. When the appropriate configuration keys are supplied and active, the workflow resources are available and can be used.

Administrators use roles, duties, and privileges to control access to workflow actions. When you create a workflow, you will typically create a privilege in security that contains the menu items and web menu items for the workflow actions. This privilege is then used by duties and roles. When users are assigned to the role that uses the duty or privilege, they will have access to the workflow actions.

For example, Microsoft Dynamics AX has the **Purchase requisition review** workflow type. Several menu items and web menu items are defined as actions for this workflow. The following security resources are used to control access to this workflow:

  - A security privilege named **PurchReqPurchaseRequisitionApprove** is created in the AOT. All of the menu items and web menu items for the workflow are added to the Entry Points node for this privilege.

  - A duty named **PurchReqPurchaseRequisitionApprove** is created that uses the **PurchReqPurchaseRequisitionApprove** privilege.

  - Roles like **VendPurchasingAgent** use the **PurchReqPurchaseRequisitionApprove** duty. Any user who is assigned to the **VendPurchasingAgent** role will have access to this workflow.

Although security controls access to workflow functionality in the application, this security access is limited to menu items. To help protect the system at a more detailed level, make sure that you set up security for table and field access. For more information, see [Role-based Security in the AOT for Developers](role-based-security-in-the-aot-for-developers.md).

Security for data flow in workflow that includes Automated Tasks, is controlled by using standard X++ security. For more information, see [X++ Security](x-security.md).

## Workflow Execution Account

The **Workflow Execution Account** (WorkflowExec) is used by the workflow runtime to execute application business logic. This account must have permissions that allow for it to access application data and execute business logic. By default, it is assigned to the **Admin** user.

To set up the workflow execution account, open **System administration** \> **Setup** \> **System service accounts**. On the **System service accounts** form, set an **Alias** and **Network domain** for the **Workflow execution account**.


> [!NOTE]
> <P>You must update the workflow execution account security settings for new objects you add that are accessed by workflow. For example, if you add a new table that will be accessed by workflow, you must grant access to that table to the workflow execution account.</P>



## See also

[Using the MorphX Security System](using-the-morphx-security-system.md)

[Record Level Security](record-level-security.md)

[Security for Microsoft Dynamics AX](security-for-microsoft-dynamics-ax.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

