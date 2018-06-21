---
title: AOSAuthorization Property on Tables
TOCTitle: AOSAuthorization Property on Tables
ms:assetid: d8636a4b-4053-4cff-99a5-190ace30080a
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Bb278259(v=AX.60)
ms:contentKeyID: 35252066
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# AOSAuthorization Property on Tables [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The AOSAuthorization table property enables you to specify which data access operations must undergo user permission checking.

## Data Access Operations

The four fundamental data access operations are create, read, update, and delete. These operations are represented in combinations by the following AOSAuthorization enumeration values:

  - None

  - CreateDelete

  - UpdateDelete

  - CreateUpdateDelete

  - CreateReadUpdateDelete

No permission checking is done when the AOSAuthorization property is set to None.

Suppose AOSAuthorization is set to CreateDelete on a given table. In this case, create and delete operations would be allowed to execute only if the Application Object Server (AOS) can confirm that the user has the appropriate permissions. Update and read operations would execute without checking user permissions, because they are not mentioned in the chosen AOSAuthorization value.

An exception is thrown when permission checking finds that the user lacks the necessary permission.

## Default AOSAuthorization Value

When a new table is created, its AOSAuthorization value is set to None.

## Views

The AOSAuthorization property also applies to views.

Performing data access operations on a view will cause permission checking for that view. There will be no underlying permission checking on any table referenced by that view.

For example, suppose view Vew2 reads data from table Tab3. You have no read permission to either Vew2 or Tab3. The AOSAuthorization value on Vew2 is None, but on Tab3 it is CreateReadUpdateDelete. When you try to read from Vew2 the outcome will be a successful retrieval of data.

## Table Methods

The permission checking is performed by the AOS. The AOS is called to perform this checking by the following table methods:

  - aosValidateDelete

  - aosValidateInsert

  - aosValidateRead

  - aosValidateUpdate

These methods are invoked once per affected table row. Therefore in some cases they may have a significant impact on performance.

No permission validation occurs when the AOSAuthorization property is set to None. In these cases the method skipAOSValidation is used instead. This executes only one time for the entire operation, which reduces the risk of slow performance.

For more information about these table methods, see [Table Methods](https://msdn.microsoft.com/en-us/library/aa625830\(v=ax.60\)).

## Example

Notice the calls to methods assert and skipAosValidation. Between these two methods the call to assert does need to occur first.

    server static void JobPermAssertSkip(Args _args)
    {
        AssetTable tabAt;
        SkipAOSValidationPermission perm;
        ;
        ttsbegin;
        perm = new SkipAOSValidationPermission();
        perm.assert();
        tabAt.skipAosValidation(true);
        update_recordset tabAt
            setting MaintenanceInfo3 = "Useful information."
            where tabAt.AssetId == "goodvalue";
        ttscommit;
    }

## Logging

Log entries related to table permissions are written when an exception is thrown due to permission checking finding that the user lacks the necessary permission.

## Checked Mode

When executing a secured server method or service operation in checked mode the **AOSAuthorization** property is always ignored and permissions are checked for all operations on all tables within the method.

## See also

[AOSAuthorization Enumeration](https://msdn.microsoft.com/en-us/library/gg882028\(v=ax.60\))

[Table Methods](https://msdn.microsoft.com/en-us/library/aa625830\(v=ax.60\))

[Table Properties](https://msdn.microsoft.com/en-us/library/aa871620\(v=ax.60\))

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

