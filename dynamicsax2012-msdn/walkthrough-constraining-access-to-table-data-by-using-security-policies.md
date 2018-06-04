---
title: 'Walkthrough: Constraining Access to Table Data by Using Security Policies'
TOCTitle: 'Walkthrough: Constraining Access to Table Data by Using Security Policies'
ms:assetid: a4bb1020-5e89-4caa-a2c1-e0944d185bdd
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh300645(v=AX.60)
ms:contentKeyID: 36595195
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Walkthrough: Constraining Access to Table Data by Using Security Policies 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

In this topic you enhance a pre-existing security policy to reduce the range of data records that roles and users can access in the **CustTable** table and the **SalesTable** table. You do this by adding the two tables under the **Constrained Tables** node of the pre-existing policy.

The security policy already exists for the **CustGroup** table. The pre-existing security policy is named **MajorCustomersPolicy**. The **PrimaryTable** property of the policy names the **CustGroup** table.

Foreign key relations are used by the policy to determine which data records the users are authorized to access on the constrained tables. The **CustGroup** table is a parent of the **CustTable** table, which has a foreign key field that references the primary key of the **CustGroup** table. And the **CustTable** table is a parent of the **SalesTable** table.

## Prerequisites

This topic continues a sequence of topics. The present topic uses AOT elements that you create by first completing the topic [Walkthrough: Creating a Simple Default Security Policy](walkthrough-creating-a-simple-default-security-policy.md). In that topic you created a simple security policy named **MajorCustomersPolicy**.

## Add to the List of Constrained Tables on the Policy

You can add tables to the list under the **Constrained Tables** node of a security policy. The policy denies access to some data records in the constrained tables. The particular records that are denied are determined by the foreign key relationships among the tables in the policy. A record on a constrained table can be accessed only if the foreign key value in the record matches the primary key value of a record that can be accessed in the primary table of the policy.

You can add the **CustTable** table as a constrained table by following these steps:

1.  Right-click the **Constrained Tables** node on policy **MajorCustomersPolicy**, and then click **New** \> **Add table by relation**.

2.  Set the **Table** property to **CustTable**.

3.  Set the property **TableRelation** to **CustGroup**.

## Chains of Constrained Tables in a Policy

In this section you constrain the **SalesTable** table. You constrain it by associating it to the constrained **CustTable** table that you added in the previous section. The **SalesTable** table is related to the **CustGroup** table indirectly through the **CustTable** table.

You constrain the **SalesTable** table by following these steps:

1.  Right-click the node **MajorCustomersPolicy** \> **Constrained Tables** \> **CustTable**, and then select **New** \> **Add table by relation**.

2.  Set the **Table** property to **SalesTable**.

3.  Set the **TableRelation** property to **OrderCustomer**.

## Constrain Views by the Policy

There are no named relations between a view and a table, the way there are between two tables where a formal foreign key is defined. However, in a security policy under its **Constrained Tables** node, you can define a relation between a view and one of the tables that the view references. You do this by setting the **Value** property of the view to a value that has the following format: (Table.FieldName=View.FieldName). You can also enter multiple field relations in the following format: ((Table.Field1=View.Field1) && (Table.Field2=View.Field2)).

In the following steps you enhance the security policy to constrain access to data from a view:

1.  Right-click the  
     **MajorCustomersPolicy** \> **Constrained Tables** \> **CustTable**   
    node and select  
     **New** \> **Add table or view by free form expression**.

2.  Set the **Value** property of the view to (smmCustomerView.Party = CustTable.Party).

## Verify that the Security Policy is Enforced on Related Tables and Views

As an application user, you can now verify that the security policy that you have created is enforced by the system.

1.  Manually assign an application user to the **Sales manager** role by using the System administration form. For information about how to assign a user to a role, see [Assign users to security roles](https://msdn.microsoft.com/en-us/library/gg751367\(v=ax.60\)).

2.  Log on to the system as an application user and run the AX32.exe client application from the Command Prompt window.

3.  Switch to company **Contoso Entertainment Systems (West) (CEU)**.

4.  Switch to the module **Accounts Receivable** and open **Common** \> **Customers** \> **All Customers**. Verify that only customers in customer group **20** are shown.  
    To confirm you can personalize the form and add the **Customer.CustomerGroup** field to the form.

5.  Verify that the application user can only view the **Major customers** customer group, as shown in the following image.
    
    ![AOTSecurityPolicyConstrTableCusts](images/Hh300645.AOTSecurityPolicyConstrTableCusts(en-us,AX.60).jpg "AOTSecurityPolicyConstrTableCusts")
    
    **The customer group that the application user can view**

6.  Switch to the module **Sales and marketing** and open **Common** \> **Sales orders** \> **All sales orders**.

7.  Verify you can only see the sales orders for customers of the **Major customers** group.
    
    ![AOTSecurityPolicyConstrTableOrders](images/Hh300645.AOTSecurityPolicyConstrTableOrders(en-us,AX.60).jpg "AOTSecurityPolicyConstrTableOrders")
    
    **The sales orders that the application user can view**

## Next Steps

Next you can associate the security policy to a role. The following properties on the security policy are involved:

1.  ContextType

2.  ContextString

3.  RoleName

For more information, see [Walkthrough: Creating a Role Context Security Policy](walkthrough-creating-a-role-context-security-policy.md).

## See also

[Security Policies Properties](security-policies-properties.md)

[Walkthrough: Creating a Role Context Security Policy](walkthrough-creating-a-role-context-security-policy.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

