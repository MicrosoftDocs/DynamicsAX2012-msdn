---
title: 'How to: Create and Apply a Configuration Key'
TOCTitle: 'How to: Create and Apply a Configuration Key'
ms:assetid: fde092c7-b117-46e5-97ac-4699e02f352f
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa893167(v=AX.60)
ms:contentKeyID: 35254210
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Create and Apply a Configuration Key [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Configuration keys allow administrators to enable or disable features in the application for all users. Disabling an unneeded feature helps to minimize the attack surface against potential attacks.

The configuration keys are listed in the Application Object Tree (AOT) under **Data Dictionary** \> **Configuration Keys**.

## Apply a Configuration Key to an AOT Element

Many types of AOT elements are controlled by a configuration key. These elements have a property that is named **ConfigurationKey**. If the property value is empty, the element is not controlled by a configuration key.

To apply a configuration key, set the **ConfigurationKey** property of the element to the name of a configuration key.

The following AOT element types are among those that can be controlled by configuration keys:

  - Enumerations

  - Extended data types

  - Fields

  - Form controls

  - Indexes

  - Menu items

  - Menus

  - Report controls

  - Tables

  - Views

A run of the cross-reference feature enables you to see all the AOT elements that are controlled by a particular configuration key. For more information, see [Cross-reference Tool](cross-reference-tool.md).

## Create a Configuration Key

To create a configuration key:

1.  Expand the **Data Dictionary** node in the AOT.

2.  Right-click the **Configuration Keys** node, and then select **New Configuration Key**.

3.  Right-click the configuration key object, and then click **Properties**.

4.  Rename the configuration key by modifying the **Name** property.

5.  Right-click the object, and then click **Create** on the shortcut menu.

6.  Right-click the object, and then click **Save** on the shortcut menu.

7.  Right-click the object again, and then click **Check In**. This opens the [Check in form](how-to-check-elements-into-the-version-control-system.md).

For more information about adding new objects to the AOT see: [How to: Add Elements to the Version Control System](how-to-add-elements-to-the-version-control-system.md)

## See also

[Using the MorphX Security System](using-the-morphx-security-system.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

