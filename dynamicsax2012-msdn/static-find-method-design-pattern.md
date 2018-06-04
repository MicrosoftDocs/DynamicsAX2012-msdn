---
title: static find Method Design Pattern
TOCTitle: static find Method
ms:assetid: e346590b-cf51-4f91-a72f-3381c429d177
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa879893(v=AX.60)
ms:contentKeyID: 35253141
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# static find Method Design Pattern 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Each table with a key should have a static find method. The method is used to find a record that fulfills the specified key.

The find method must:

  - Be static because it is used to find a record among all the objects of the table class.

  - Return an object of the type of the table (or null if not found).

  - Be named find.

  - Have a parameter of the same type as the key of the table or a list of parameters if the key consists of more than one field. If there is a list of parameters, they must be in the same order that the key fields are listed in the index that supports the key of the table.

  - Have a Boolean parameter with a default value of false. If true, the record should be selected for update.

  - Have an optional parameter to enable the default Concurrency Model behavior specified on the table to overruled. The default value for the parameter should be ConcurrencyModel::Auto.

  - Make the most effective select operation for the single record from the table and return it. Use an index that matches the required field, and use the firstOnly keyword (see the following example).

  - Run on both the client and the server. This is the default behavior. You can also make it explicit by putting "client server" in the declaration, but do not specify a single tier in the declaration (either the client or the server).

The method must be used whenever a record is selected by its key from the database.


> [!NOTE]
> <P>Declare find methods as public. If you do not, a best practices warning appears if the method is not used in the application. (The warning suggests that you declare the method as private because this is the most restrictive level of access.)</P>



## See also

[Microsoft Dynamics AX Design Patterns](microsoft-dynamics-ax-design-patterns.md)

[Optimistic Concurrency Control](optimistic-concurrency-control.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

