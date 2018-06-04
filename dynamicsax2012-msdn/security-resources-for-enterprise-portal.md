---
title: Security Resources for Enterprise Portal
TOCTitle: Security Resources for Enterprise Portal
ms:assetid: 25ef53c5-296a-4b1c-9eb7-fe52f0e5c2ba
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh608236(v=AX.60)
ms:contentKeyID: 39555625
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# Security Resources for Enterprise Portal 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Security in Enterprise Portal is part of the standard security implementation in Microsoft Dynamics AX. Availability of Enterprise Portal resources is controlled through configuration keys. Security resources (roles, duties, privileges) are used to control security access to Enterprise Portal resources. For general information about security, see [Role-based Security in the AOT for Developers](role-based-security-in-the-aot-for-developers.md).

## Configuration Keys

Availability of Enterprise Portal resources is controlled by configuration keys and web configuration keys. Resources like Web Menu Items and Managed Content items have the **ConfigurationKey** and the **WebConfigurationKey** properties that you can set. When the appropriate configuration keys are supplied and active in Microsoft Dynamics AX, the Enterprise Portal resources are available and can be used. For most Enterprise Portal resources, the **ConfigurationKey** and **WebConfigurationKey** properties are set to EP.

## Security Resources

Administrators use roles, duties, and privileges to control access to Enterprise Portal resources. When you create an Enterprise Portal integration, you will create Privilege resources in the AOT that contain the web menu items and managed content items that are needed to access the specific resources. You might also decide to add resources to existing Privilege resources.

Typically, you will create separate Privilege resources for Enterprise Portal. For example, the **FCMRoomView** privilege would provide read access to the Rooms form in the Microsoft Dynamics AX client. A separate privilege named **FCMEPRoomView** would provide access to the RoomDetails page in Enterprise Portal. Separate Privilege resources allow for flexibility for system administrators when they configure security.

### Privileges for Pages

To control access for pages in Enterprise Portal, you must configure an entry point for the web menu item that accesses the page, and another entry point for the managed content component of the User Control displayed on the page. It is necessary to secure both the web menu item and the managed content component so that a user cannot just add the User Control from an inaccessible page to a page that they do have access to.

### Privileges for List Pages

To control access for list pages in Enterprise Portal, you must configure entry points for the web menu items that access the list page. You must also configure entry points for the web menu items that are used for the actions in the action pane for the list page. You may also have to add items to the Permissions node to provide access to features of the list page, such as FactBoxes. Typically, this means adding tables to the Tables node to allow the data to be accessed. You will have to determine what table or tables the Parts in the FactBox area are accessing, and then add those tables to the Tables node.

### Privileges for Reports

To control access for reports in Enterprise Portal, you must configure an entry point for the web menu item that accesses the page on which the report is displayed. You will also need to grant each user the appropriate privileges in SQL Server Reporting Services to enable them to access the report.

