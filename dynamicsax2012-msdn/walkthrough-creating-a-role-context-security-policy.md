---
title: 'Walkthrough: Creating a Role Context Security Policy'
TOCTitle: 'Walkthrough: Creating a Role Context Security Policy'
ms:assetid: 45ad7c0f-3d86-46e9-9001-816679b37738
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh300643(v=AX.60)
ms:contentKeyID: 36595193
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Walkthrough: Creating a Role Context Security Policy [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

In this topic you modify a policy to apply it to security roles.

## Prerequisites

This topic continues a sequence of topics. This topic uses AOT elements that you create by completing the preceding topics. For this topic, you first must complete the preceding topics listed next:

1.  In [Walkthrough: Creating a Simple Default Security Policy](walkthrough-creating-a-simple-default-security-policy.md) you created and verified a simple default security policy.

2.  Then in [Walkthrough: Constraining Access to Table Data by Using Security Policies](walkthrough-constraining-access-to-table-data-by-using-security-policies.md) you constrained tables or views by enforcing a security policy on related tables.

## Change the Security Policy to Specify a Security Role

1.  Change the **ContextType** property on the policy node **MajorCustomersPolicy** to **RoleName**.

2.  Set the **RoleName** property on the policy node to **TradeSalesManager**.
    
    The following figure shows the **MajorCustomersPolicy** security policy property values.
    
    ![AOTSecurityPolicyRole](images/Hh300643.AOTSecurityPolicyRole(en-us,AX.60).jpg "AOTSecurityPolicyRole")
    
    **The security policy property values**

## Verify that the Security Policy is Enforced

As an application user, you can now verify that the new security policy is enforced by the system.

1.  Manually assign an application user to the **Sales manager** role by using the System administration form. For information about how to assign a user to a role, see [Assign users to security roles](https://msdn.microsoft.com/en-us/library/gg751367\(v=ax.60\)).

2.  Log on to the system as an application user and run the AX32.exe client application from the Command Prompt window.

3.  Switch to company **Contoso Entertainment Systems (West) (CEU)**.

4.  Switch to module **Accounts Receivable** and open **Setup** \> **Customers** \> **Customer groups**

5.  Verify that the application user can only view the **Major customers** customer group, as shown in the following image.
    
    ![AOTSecurityPolicyOutput](images/Hh300643.AOTSecurityPolicyOutput(en-us,AX.60).jpg "AOTSecurityPolicyOutput")
    
    **The customer group that the application user can view**

## See also

[Security Policies Properties](security-policies-properties.md)

[Walkthrough: Constraining Access to Table Data by Using Security Policies](walkthrough-constraining-access-to-table-data-by-using-security-policies.md)

[Walkthrough: Creating a Role Context Security Policy](walkthrough-creating-a-role-context-security-policy.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

