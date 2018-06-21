---
title: Application Object Properties
TOCTitle: Application Object Properties
ms:assetid: 3d623951-8d6d-48cb-ad05-40ad1fb13632
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa593880(v=AX.60)
ms:contentKeyID: 35242935
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Application Object Properties [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Every Microsoft Dynamics AX application object in the Application Object Tree (AOT) has a set of properties. To view and modify property values, right-click an application object, and then select **Properties** to open the **Properties** sheet. This topic describes the **Properties** sheet and how to modify property values. For descriptions of individual properties, see [Properties of AOT Elements](https://msdn.microsoft.com/en-us/library/gg731856\(v=ax.60\)).

By default, the sorting order of properties displayed in the **Properties** sheet is determined by their relationship. Similar properties are positioned together. To sort properties alphabetically:

1.  Click **Tools** \> **Options**.

2.  On the **Options** form, select **Development** \> **Property sheet** \> **Sort alphabetically**.

3.  Click **Apply**.


> [!TIP]
> <P>By default, the <STRONG>Properties</STRONG> sheet is docked on the right side of the Development Workspace. To change docking location or options, right-click the <STRONG>Properties</STRONG> sheet title bar, and then select another option on the shortcut menu.</P>



## Modifying Properties

Most property settings can be modified. Read-only property settings are unavailable. To modify a property in the **Properties** sheet, select a property, and then enter a new value or select a new value from the drop-down list. Many properties have default values. When you change a default property value, the property name and value is bold in the **Properties** sheet.

You can modify the common properties of multiple application objects at the same time. If a common property value is different for the selected application objects, the property value is blank.

You can also modify property values by using X++ code using the [::setProperty](https://msdn.microsoft.com/en-us/library/gg802857\(v=ax.60\)) method.

## Properties Sheet Colors

The property editor uses the following colors:

  - Pale red – Indicates that the property value is the name of the application object when referred to by X++ code. For example, the **Name** property value of a form or table.

  - Pale yellow – Identifies property values that should be labels.

## See also

[Best Practices for Application Objects](best-practices-for-application-objects.md)

[Properties of AOT Elements](https://msdn.microsoft.com/en-us/library/gg731856\(v=ax.60\))

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

