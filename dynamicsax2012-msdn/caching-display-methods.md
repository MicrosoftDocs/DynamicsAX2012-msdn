---
title: Caching display Methods
TOCTitle: Caching display Methods
ms:assetid: 104c832c-98a9-46e2-a720-8a7282c71b31
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa596691(v=AX.60)
ms:contentKeyID: 35240532
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Caching display Methods [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The performance of display methods can be improved by caching them if they are calculated on Application Object Server (AOS). Caching display methods can also improve performance when records are transferred from the server to the client.

The value of all cached methods is set when data is fetched from the back-end database. In addition, the value is refreshed when the reread method is called on the form data source.

## Add a display Method to the Cache

1.  Locate the form that the method is used on.

2.  Expand the **Data Sources** node.

3.  Right-click the data source that the method is associated with, and then select **Override Method** \> **init**.

4.  Call the [FormDataSource.cacheAddMethod](https://msdn.microsoft.com/en-us/library/gg857757\(v=ax.60\)) method after the call to super() in the init method.
    
    The first parameter for cacheAddMethod determines the name of the method to be cached. The second parameter (set to true by default) determines whether the value of the display method is updated when a record is written to the database.

## See also

[Using the display Method Modifier](using-the-display-method-modifier.md)

[Methods on a Form Data Source](methods-on-a-form-data-source.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

