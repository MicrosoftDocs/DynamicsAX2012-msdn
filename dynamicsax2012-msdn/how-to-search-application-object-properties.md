---
title: 'How to: Search Application Object Properties'
TOCTitle: 'How to: Search Application Object Properties'
ms:assetid: 920913fe-702e-4cc9-b6d3-8944ab97beba
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa661186(v=AX.60)
ms:contentKeyID: 35247444
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Search Application Object Properties 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

In Microsoft Dynamics AX, you can use the **Find** dialog box to search for Application Object Tree (AOT) properties and property values. This topic describes how to search for properties in the AOT.

### To find any property name or value

1.  In the AOT, right-click the node or application object to search, and the click **Find**. The **Find** dialog box opens.

2.  On the **Name & Location** tab, set the **Search** field to **All nodes**.

3.  In the **Containing text** field, enter the name of the property or property value to find, and then click **Find now**. All property names and values that contain the text you entered are shown in the output window for the selected node in the AOT.

For example, in the AOT, if you search the **Workflow** node, and enter Module in the **Containing text** field, all application objects that have a property name or value equal to, or that contains the text Module are displayed.

### To find property names with a specific value

1.  In the AOT, right-click the node or application object to search, and the click **Find**. The **Find** dialog box opens.

2.  On the **Name & Location** tab, set the **Search** field to **All nodes**.

3.  In the **Containing text** field, enter a property name and value in the following format: PropertyName: \*\#PropertyValue, and then click **Find now**. All property names that contain the specified value are shown in the output window for the selected node in the AOT.

For example, in the AOT, if you search the **Workflow** node, and enter Module: \*\#Vendor in the **Containing text** field, only application objects that have a property named **Module** where the value is set to **Vendor** are displayed.

## See also

[Application Object Properties](application-object-properties.md)

[Properties of AOT Elements](https://msdn.microsoft.com/en-us/library/gg731856\(v=ax.60\))

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

