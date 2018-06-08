---
title: AOS Overview
TOCTitle: AOS Overview
ms:assetid: 8ff82a61-1214-4a04-8d82-1cc1c096fe55
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa660629(v=AX.60)
ms:contentKeyID: 35247405
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# AOS Overview 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

In Microsoft Dynamics AX, there is a 3-tier infrastructure with a database server, an application object server (AOS), and a client. The database server contains the table data. The AOS is used to execute application objects, such as queries and classes. Application objects in the user interface, such as forms and reports, run on the client computer. This topic describes how to develop an application using the different tiers and how record buffers are related to the tiers.

The following illustration shows the three-tier architecture.  

![Three Tier Architecture Diagram](images/Aa660629.dvg_3_tier_architecture(en-us,AX.60).gif "Three Tier Architecture Diagram")

## Separating Application Objects into Tiers

When you separate the application data from the application objects, it is easier to distribute upgrade versions of your application. This is because you can distribute forms, queries, classes, and reports that are based on the same set of underlying tables without affecting application data. In addition, separating data from other application objects can reduce network load.

You can use the AOS for sharing objects and information as an effective tool to increase performance. Microsoft Dynamics AX and SQL server databases can be used together to provide powerful programming languages to validate data and enforce business rules. For more information, see [Best Practices: Application Object Server (AOS)](best-practices-application-object-server-aos.md) and [How to: Optimize an Application for the AOS](how-to-optimize-an-application-for-the-aos.md).

## Multiple AOS Computers

When you start the program AX32.exe –development, the MorphX development workspace window opens. A session is created to connect this client program to an AOS. This connection uses the standard Remote Procedure Call (RPC) protocol. This session is kept open and is used each time you open another Application Object Tree (AOT).

More sessions are needed as more client programs connect to the AOS tier. Every session adds to the workload on the AOS tier. The workload on the AOS tier can be shared among multiple instances of the AOS. These AOS instances can be distributed among one or more computers. The system controls which AOS each new client session connects to. The system balances the workload among AOS instances to improve performance.

### ![Aa660629.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa660629.collapse_all(en-us,AX.60).gif")Session Pool for Services

Another session is needed when the client issues a service call. Services are stateless, which means the session is no longer needed after the service call returns to the caller. After the call returns, the system assigns the session back to a session pool. Future service calls that are received by the AOS can reuse a session from the pool. Different sessions might be assigned to several service calls made by one client. The reuse of sessions improves performance by avoiding the overhead of creating a new session for each service call.

For more information, see [Locating the WSDL for Services](https://msdn.microsoft.com/en-us/library/gg843514\(v=ax.60\)).

## Record Buffers

Record buffers are automatically replicated between the application object server and the client as needed. As buffers are replicated, calls between the application object server and the client increase. For example, consider the following scenario.

1.  A record is selected on the AOS.

2.  A table instance method that has been set to Client is called.

3.  The buffer is replicated and sent to the client.

4.  The client reads and then modifies the buffer.

5.  The buffer is replicated and sent to the server.

The buffer is replicated only if needed, as in the preceding example. If the value of the buffer was unchanged, the buffer would not be replicated on the AOS.

Avoid calling client based objects from the server as this will decrease application performance. This is because when a \<record\> .datasource method on a client object is called from the server, the method returns an object and must access the client even if the [FormDataSource Class](https://msdn.microsoft.com/en-us/library/gg892246\(v=ax.60\)) object does not exist on the client. For more information, see [Best Practices: Application Object Server (AOS)](best-practices-application-object-server-aos.md).

## See also

[Best Practices: Application Object Server (AOS)](best-practices-application-object-server-aos.md)

[How to: Optimize an Application for the AOS](how-to-optimize-an-application-for-the-aos.md)

[AOS Security](aos-security.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

