---
title: 'Best Practices: Application Object Server (AOS)'
TOCTitle: 'Best Practices: Application Object Server (AOS)'
ms:assetid: d3ad30d8-9692-4f58-98bc-817af4bfe411
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc576577(v=AX.60)
ms:contentKeyID: 35251968
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Best Practices: Application Object Server (AOS) 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The Microsoft Dynamics AX Application Object Server (AOS) is a scalable application server that can execute business logic for clients. The AOS can enable multiple connections and other types of clients to access the database, conduct load balancing, and much more. This topic describes how you can optimize an application by using AOS functionality.

## General Best Practices

When developing an application, consider the following best practices:

  - Minimize the traffic between the server and the client.

  - Put user interface related logic on the client.

  - Run application logic (business logic) on the AOS.

  - Put database related logic on the database server.

  - Minimize "other tier calls" in the inner loops of your application by using tier calls at the start and end of jobs.

  - Use containers to transport multiple values in one call that collects values and returns them. For more information, see [Containers](containers.md) and [Best Practice Performance Optimizations: AOS Tuning](best-practice-performance-optimizations-aos-tuning.md).

  - Call a static method remotely instead of instantiating an object remotely and then calling a method on it.

## Application Optimization

The following list contains steps you can take to optimize your application to run on the AOS.

  - Evaluate application class and table **RunOn** property settings. For the class static methods, evaluate whether the server or client modifier should be added. For more information, see [How to: Optimize an Application for the AOS](how-to-optimize-an-application-for-the-aos.md).

  - Optimize the application for low bandwidth between client and server

## Running Code on the Server

You should run methods on the server if they do one of the following:

  - Have more than one select.

  - Select more than a few records.

  - Call methods on the server.

Every database operation passes through the AOS. If your code performs more than one operation on the database, it should run on the server.

If your code has more than one call to the server, it should run on the server.

For more information, see [Where to Place the Code](where-to-place-the-code.md).

## AOSRunOn Hint

You should add the AOSRunOn hint to class static methods set to RunOn Called from. A best practices warning is generated if the hint is missing, or if the hint does not match the RunOn property value of the method. The AOSRunOn hint is useful to determine whether the RunOn Called from value is set because you have not yet decided which tier the method should run on. For more information, see [Application Object RunOn Property Overview](application-object-runon-property-overview.md).

## Queries

The [QueryRun Class](https://msdn.microsoft.com/en-us/library/gg923354\(v=ax.60\)) object should always run from the same tier where the query is read. The QueryRun class accesses the tables defined in the data sources in the call to the [QueryRun.next Method](https://msdn.microsoft.com/en-us/library/gg923364\(v=ax.60\)) as shown in the following code example.

    queryRun.next()

When a QueryRun object is created from a query on another tier, a pack operation is implicitly performed. This is invisible to the user, except if the query contains, for example, links to buffers outside the query itself. These references are not valid on another tier and an error is generated.

Use the [QueryRun.newObject Method](https://msdn.microsoft.com/en-us/library/gg923363\(v=ax.60\)) to create a new QueryRun object as shown in the following code example.

    myNewQueryRun = myOldQueryRun.newObject(query);

The myNewQueryRun instance is a new QueryRun object that is created on the same tier as myOldQueryRun object. The arguments for the newObject method are the same as the QueryRun object.

## Client/Server Neutral Functions

By using client/server neutral functions where applicable, you can increase performance when you use the:

  - [curExt Function](https://msdn.microsoft.com/en-us/library/aa887473\(v=ax.60\)) instead of the appl.company().ext().

  - [RunbaseProgress Class](https://msdn.microsoft.com/en-us/library/gg823022\(v=ax.60\)).

Calling client based objects from the server decreases application performance and should be avoided.

When a \<record\> .datasource method on a client object is called from the server, the method returns an object and must access the client whether the [FormDataSource Class](https://msdn.microsoft.com/en-us/library/gg892246\(v=ax.60\)) exists on the client. When the \<record\> .datasource method on a non-connected server object is called from the server, the client does not have to be accessed.

## See also

[AOS Security](aos-security.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

