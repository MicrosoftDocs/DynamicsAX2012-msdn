---
title: 'How to: Create a New Purpose'
TOCTitle: 'How to: Create a New Purpose'
ms:assetid: edf8c448-4373-4f98-8861-98fdbd61ac06
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg989800(v=AX.60)
ms:contentKeyID: 35405157
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Create a New Purpose [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

You can extend the Microsoft Dynamics AX organization model to create a custom purpose. A purpose defines how the organization hierarchy is used in application scenarios. For example, you can assign a hierarchy to a purpose, such as the **Expenditure internal control** purpose, to define policies for expense reports. The override and defaulting rules for policies on expense reports are based on the hierarchies that have the purpose of **Expenditure internal control**.

An organization can belong to several hierarchies. By assigning a hierarchy to a purpose you identify to the system how to find the correct hierarchy for applying policies.

In this topic you create a purpose named **MyPurpose**.

## Create a New Base Enumerated Value

You create a new base enumerated value for your custom purpose by following these steps:

1.  Create a project named **CustomPurpose**. The project can be either private or shared.
    
    For information about how to create a project, see [How to: Create a MorphX Development Project](how-to-create-a-morphx-development-project.md).

2.  Drag the **AOT** \> **Data Dictionary** \> **Base Enums** \> **HierarchyPurpose** node onto the project node.

3.  Add an element named **MyPurpose** to the **HierarchyPurpose** enum. Under your project node right-click **HierarchyPurpose**, and then click **New Element**. In the **Properties** window, set the following properties:
    
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
    <td><p>Name</p></td>
    <td><p>MyPurpose</p></td>
    </tr>
    <tr class="even">
    <td><p>Label</p></td>
    <td><p>My purpose</p></td>
    </tr>
    </tbody>
    </table>


## Create a Method for a New Purpose

In this section you will create a method named **addMyPurpose** that resembles methods created for other types of purposes. For example, the **addSecurityPurpose** method was created for the security purpose.

1.  Locate **OMHierarchyPurposeTableClass** in the **AOT** \> **Classes** node.

2.  Drag the **AOT** \> **Classes** \> **OMHierarchyPurposeTableClass** node onto the project node.

3.  Duplicate the **addSecurityPurpose** method by right-clicking the **addSecurityPurpose** node, and then clicking **Duplicate**. The AOT will create the **CopyOfaddSecurityPurpose** node.

4.  Replace the code for the **CopyOfaddSecurityPurpose** method with the following code. This renames the method.
    
        private static void addMyPurpose()
        {
            OMHierPurposeOrgTypeMap omHPOTP;
        
            select RecId from omHPOTP
                where omHPOTP.HierarchyPurpose == HierarchyPurpose::MyPurpose;
        
            if (omHPOTP.RecId <= 0)
            {
                omHPOTP.clear();
                omHPOTP.HierarchyPurpose = HierarchyPurpose::MyPurpose;
                omHPOTP.OperatingUnitType = OMOperatingUnitType::OMAnyOU;
                omHPOTP.IsLegalEntityAllowed = NoYes::No;
                omHPOTP.write();
        
                omHPOTP.clear();
                omHPOTP.HierarchyPurpose = HierarchyPurpose::MyPurpose;
                omHPOTP.OperatingUnitType = 0;
                omHPOTP.IsLegalEntityAllowed = NoYes::Yes;
                omHPOTP.write();
        
            }
        }
    
    The preceding code is similar to the code in most of the methods on the **OMHierarchyPurposeTableClass** class. The code was changed in only the places where the HierarchyPurpose enum values are referenced. In the code you can see three occurrences of HierarchyPurpose::MyPurpose.

5.  In the **OMHierarchyPurposeTableClass** class, update the **populateHierarchyPurposeTable** method to call the new method that you created. The following line of code should be added.
    
     
    
    OMHierarchyPurposeTableClass::addMyPurpose();
    
     
    
    The following code shows your modification to the **populateHierarchyPurposeTable** method, near the end of the method.
    
        public static void populateHierarchyPurposeTable()
        {
            OMHierPurposeOrgTypeMap omHPOTP;
        
            if (omHPOTP.RecId <= 0)
            {
                ttsbegin;
                OMHierarchyPurposeTableClass::AddOrganizationChartPurpose();
                OMHierarchyPurposeTableClass::AddInvoiceControlPurpose();
                OMHierarchyPurposeTableClass::AddExpenseControlPurpose();
                OMHierarchyPurposeTableClass::AddPurchaseControlPurpose();
                OMHierarchyPurposeTableClass::AddSigningLimitsPurpose();
                OMHierarchyPurposeTableClass::AddAuditInternalControlPurpose();
                OMHierarchyPurposeTableClass::AddCentralizedPaymentPurpose();
                OMHierarchyPurposeTableClass::addSecurityPurpose();
                    // We add the following line.
                OMHierarchyPurposeTableClass::addMyPurpose();
                ttscommit;
            }
        }

## Review the Project

Now you have created all the items essential for this scenario, as shown in the following image.

![AOTOrgMCustPurposeProj](images/Gg989800.AOTOrgMCustPurposeProj(en-us,AX.60).jpg "AOTOrgMCustPurposeProj")

**The project that you have created**

## Use Your New Purpose Type

1.  In the **Workspace** window of your Microsoft Dynamics AX client, select **DAT** \> **Organization administration** \> **Area page** \> **Setup** \> **Organization** \> **Organization hierarchy purposes**. For information about how to use the **Organization hierarchy purposes** form, see [Create or modify an organization hierarchy](https://msdn.microsoft.com/en-us/library/hh227463\(v=ax.60\)).
    
    The form displays as shown in the following image.
    
    ![AOTOrgMCustPurposeAssignHier](images/Gg989800.AOTOrgMCustPurposeAssignHier(en-us,AX.60).jpg "AOTOrgMCustPurposeAssignHier")
    
    **The new purpose that you create**

2.  By using the toolbar on this form you can assign, remove, and view hierarchies for your new purpose.

## See also

[Extending the Organization Model](extending-the-organization-model.md)

[What's new: Company and organization framework](https://msdn.microsoft.com/en-us/library/dn507119\(v=ax.60\))

[Create or modify an organization hierarchy](https://msdn.microsoft.com/en-us/library/hh227463\(v=ax.60\))

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

