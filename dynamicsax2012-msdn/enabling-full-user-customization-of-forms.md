---
title: Enabling Full User Customization of Forms
TOCTitle: Enabling Full User Customization of Forms
ms:assetid: b7dd7aaf-851f-454e-986a-911a639389a7
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa859579(v=AX.60)
ms:contentKeyID: 35249848
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Enabling Full User Customization of Forms 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Enabling full user customization of forms is the highest level that can be set for [user personalization of forms](user-personalization-of-forms.md). This level requires that you set the AllowUserSetup property on the form control and set the AllowAdd property on the form data source field to Yes.

Users can customize the layout and add new fields from the **Setup** form (available in the shortcut menu for open forms).

To support this level of personalization, you must move all code to the data source fields. If a control is added to a form by a user, no code is attached and the properties are the default values for that type of control and data.

By default, only fields that are already present in the form can be added; however, this can be changed at design-time.


> [!NOTE]
> <P>Only data fields can be added. The user cannot add unbound controls or controls bound to display methods.</P>



## See also

[Form Control Properties](form-control-properties.md)

[Form Data Source Field Properties](form-data-source-field-properties.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

