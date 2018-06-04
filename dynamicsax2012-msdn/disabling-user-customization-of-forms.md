---
title: Disabling User Customization of Forms
TOCTitle: Disabling User Customization of Forms
ms:assetid: 847e97c1-d9de-4752-b1a9-967f405e195b
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa676961(v=AX.60)
ms:contentKeyID: 35246165
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Disabling User Customization of Forms 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Disabling user customization is the lowest level that can be set for [User Personalization of Forms](user-personalization-of-forms.md). This level requires that you set the AllowUserSetup property on the form control, and set the AllowAdd property on the form data source field to No.

In this mode, only the size and position of the form can be changed. Users cannot change properties on the individual controls.

Because the position and size of the form is saved (the size is saved if the SaveSize property is set to Yes), there is an entry for this form in the SysLastValue table. No personalization is allowed.

This personalization level is relevant in forms that have a fixed size and whose control positions are important. Examples are wizard forms and forms used for touch-sensitive screens. Use of this personalization level also ensures that users cannot hide information in a particular form.


> [!NOTE]
> <P>If you use the AllowUserSetup and AllowAdd properties to prevent user customizations, it affects all users of the form. If customization should be set at run time on a per-user group basis, use the SecurityKey property on the menu item for the form or on individual form controls.</P>



## See also

[Form Control Properties](form-control-properties.md)

[Form Data Source Field Properties](form-data-source-field-properties.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

