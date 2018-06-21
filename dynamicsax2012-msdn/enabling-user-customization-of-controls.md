---
title: Enabling User Customization of Controls
TOCTitle: Enabling User Customization of Controls
ms:assetid: 93a3478a-87f4-4eba-ae33-38132ca6c594
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa842587(v=AX.60)
ms:contentKeyID: 35247571
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Enabling User Customization of Controls [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Customizing controls is the second-lowest level that can be set for [User personalization of forms](user-personalization-of-forms.md). This level requires that you set the AllowUserSetup property on the form control to Restricted, and the AllowAdd property on the form data source field to No.

This personalization level allows users to change the behavior of individual controls, but not to move them or add new controls.

Users can define personal values for the following properties:

  - Enabled

  - Visible

  - Skip

  - Width

  - Label

These values can be adjusted from the **Setup** form (available in the shortcut menu for open forms). The Visible property can also be set by using the **Hide** option on the shortcut menu. To change the width of grid columns, drag the column border in the form.

## See also

[Form Control Properties](form-control-properties.md)

[Form Data Source Field Properties](form-data-source-field-properties.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

