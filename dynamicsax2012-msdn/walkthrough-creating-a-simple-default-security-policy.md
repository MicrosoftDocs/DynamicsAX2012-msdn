---
title: 'Walkthrough: Creating a Simple Default Security Policy'
TOCTitle: 'Walkthrough: Creating a Simple Default Security Policy'
ms:assetid: 78c99b29-36e7-4c99-a163-5ea9314e0122
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh272121(v=AX.60)
ms:contentKeyID: 36536818
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Walkthrough: Creating a Simple Default Security Policy 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

A security policy reduces the range of table records that users in roles are allowed to access. In the AOT, you create a security policy by first creating a query that has a range. Next you create the policy and set its **Query** property to the new query. Roles and users that are associated to the policy can see only the subset of table records that are included by the range.

In this topic you create a security policy on the **CustGroup** table.

## Prerequisites

To complete the final steps in this topic, you must understand how to test security. Robust testing requires you to be a user in the following different user roles at different stages:

  - Developer

  - System administrator

  - Application user

For more information, see [How to: Test the Role-based Security Configurations under AOT Security](how-to-test-the-role-based-security-configurations-under-aot-security.md).

## Create a Project for Your Form

It is convenient to create a project to collect the AOT elements that you create for this topic.

1.  Create a project named **SecurityPolicy**. The project can be either private or shared. For information about how to create a project, see [How to: Create a MorphX Development Project](how-to-create-a-morphx-development-project.md).

2.  In the **Projects** window, right-click your project, and then click **Open**. This opens your project in its own window. You can close the **Projects** window.

## Inspect the Data You Want to Secure

The following steps are based on the test data that is named **Contoso Entertainment Systems (West)(CEU)**. It is not necessary for you to have this particular set of test data. As you follow the steps, you can perform analogous actions with your test data set.

1.  Open the Microsoft Dynamics AX client and switch to company **Contoso Entertainment Systems (West) (CEU)**.

2.  Switch to module **Accounts Receivable** and open **Setup** \> **Customers** \> **Customer groups**

3.  Verify that the **Major customers** customer group has an **ID** value of 20, as shown in the following image. You will create a policy so that an application user can only work with data for this customer group.
    
    ![AOTSecurityPolicyCustomerGroups](images/Hh272121.AOTSecurityPolicyCustomerGroups(en-us,AX.60).jpg "AOTSecurityPolicyCustomerGroups")
    
    **The customer group that you work with**

## Create a Query for Your Security Policy

Each security policy relies on a query. The ranges of the query are a primary element of the security policy.

You can create a new policy query by following these steps:

1.  Create a policy query by right-clicking the **SecurityPolicy** project, and then navigating to **New** \> **Query**. Rename the new query to **MajorCustomersPolicyQuery**.

2.  Locate **Data Sources** under the **SecurityPolicy** \> **MajorCustomersPolicyQuery** node. Add a new data source.

3.  In the **Properties** window for the new data source, set the **Name** property to **CustGroup\_1**, and the **Table** property to **CustGroup**.

4.  Right click the **Ranges** node and select **New Range**.

5.  In the **Properties** window for the new range, set the **Field** property to **CustGroup**, and the **Value** property to 20.

6.  Locate **Fields** under the **MajorCustomersPolicyQuery** \> **Data Sources** \> **CustGroup\_1** node.

7.  In the **Properties** window for **Fields**, set the **Dynamic** property to **Yes**. The **Yes** value indicates that all fields are queried.

## Create a Security Policy

You can create a security policy by following these steps:

1.  Create a security policy query by right-clicking the **SecurityPolicy** project, and then navigating to **New** \> **Security** \> **Security Policy**. Rename the new security policy to **MajorCustomersPolicy**.

2.  In the **Properties** window for **MajorCustomersPolicy**, set the following properties:
    
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
    <td><p><strong>Name</strong></p></td>
    <td><p>MajorCustomersPolicy</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Label</strong></p></td>
    <td><p>Restrict data to major customers</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>PrimaryTable</strong></p></td>
    <td><p>CustGroup</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Query</strong></p></td>
    <td><p>MajorCustomersPolicyQuery</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>PolicyGroup</strong></p></td>
    <td><p>Customer group based policy</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>ConstrainedTable</strong></p></td>
    <td><p>Yes</p></td>
    </tr>
    <tr class="odd">
    <td><p><strong>Enabled</strong></p></td>
    <td><p>Yes</p></td>
    </tr>
    <tr class="even">
    <td><p><strong>Operation</strong></p></td>
    <td><p>All operations</p></td>
    </tr>
    </tbody>
    </table>


3.  Save and compile the security policy.

The security policy is now ready for deployment and testing. Note that the **ContextType** property is currently set to the value **ContextString**, but the **ContextString** property is empty. This combination implies that when it is enabled, this security policy will always be applicable for all users.

## Review the Project

You have created all the items necessary for this walkthrough as shown in the following image.

![AOTSecurityPolicyProject](images/Hh272121.AOTSecurityPolicyProject(en-us,AX.60).jpg "AOTSecurityPolicyProject")

**The project that you create**

## Verify that the Security Policy is Enforced

As an application user, you can now verify that the security policy that you have created is enforced by the system.

1.  Assign an application user to the **Sales manager** role. The form for this in the System administration module, at **System administration** \> **Setup** \> **Security** \> **Assign users to roles**.  
    For more information, see [Assign users to security roles](https://msdn.microsoft.com/en-us/library/gg751367\(v=ax.60\)).

2.  Log on to the system as an application user. Then run the AX32.exe client application from a command prompt window.

3.  Switch to company **Contoso Entertainment Systems (West) (CEU)**.

4.  Switch to module **Accounts Receivable** and open **Setup** \> **Customers** \> **Customer groups**

5.  Verify that the application user can view only the **Major customers** customer group, as shown in the following image.
    
    ![AOTSecurityPolicyOutput](images/Hh300643.AOTSecurityPolicyOutput(en-us,AX.60).jpg "AOTSecurityPolicyOutput")
    
    **The customer group that the application user can view**

6.  Try to insert a record and verify that the application user cannot add any other customer group.  
    When you try to insert a record you will see the code output to the **Infolog** window as shown in the following image.
    
    ![AOTSecurityPolicyError](images/Hh272121.AOTSecurityPolicyError(en-us,AX.60).jpg "AOTSecurityPolicyError")
    
    **The system error output caused by the enforced security policy**

## Next Steps

  - You can extend the security policy to constrain tables or views that contain related data. For more information, [Walkthrough: Constraining Access to Table Data by Using Security Policies](walkthrough-constraining-access-to-table-data-by-using-security-policies.md).

  - You can develop a context-sensitive security policy as described in [Walkthrough: Creating a Role Context Security Policy](walkthrough-creating-a-role-context-security-policy.md).

## See also

[Security Policies Properties](security-policies-properties.md)

[Walkthrough: Constraining Access to Table Data by Using Security Policies](walkthrough-constraining-access-to-table-data-by-using-security-policies.md)

[Walkthrough: Creating a Role Context Security Policy](walkthrough-creating-a-role-context-security-policy.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

