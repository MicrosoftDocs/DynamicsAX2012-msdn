---
title: .NET Business Connector Overview
TOCTitle: .NET Business Connector Overview
ms:assetid: 8bc3c5f1-1c69-4035-aa75-090da361dc3d
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa659581(v=AX.60)
ms:contentKeyID: 35246352
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# .NET Business Connector Overview 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The topics in this section provide information about the Microsoft Dynamics AX .NET Business Connector.

.NET Business Connector is a component of the Microsoft Dynamics AX development environment. .NET Business Connector enables you to build software applications that integrate with Microsoft Dynamics AX. You can access data or start business logic. The advantage of using .NET Business Connector over other types of integration is that you use the same X++ code and business logic available to clients. You will also be able to use the Microsoft Dynamics AX security model. For more information about security, see [Security and .NET Business Connector Applications](security-and-net-business-connector-applications.md).

Use the .NET Business Connector to interpret and execute code. It provides a run-time environment for interacting with elements in the Application Object Tree (AOT). The .NET Business Connector enables applications to interact with Application Object Server (AOS) instances by providing a set of .NET managed classes. These classes enable access to X++ classes in Microsoft Dynamics AX.

The .NET Business Connector can be installed as a stand-alone component. It can also be used to develop third-party applications that integrate with Microsoft Dynamics AX.

To support integration with Microsoft Windows SharePoint Services and to enhance product security, the .NET Business Connector requires Windows integrated authentication.

## Related Features

Microsoft Dynamics AX has other features that are related to .NET Business Connector. The following sections introduce Application Integration Framework (AIF), .NET interop from X++, and .NET interop to X++.

### ![Aa659581.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa659581.collapse_all(en-us,AX.60).gif")Application Integration Framework

Application Integration Framework (AIF) is the infrastructure within Microsoft Dynamics AX that is the long term strategy to expose business logic or exchange data with other systems. For more information, see [Application integration](https://msdn.microsoft.com/en-us/library/dd362007\(v=ax.60\)).

### ![Aa659581.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa659581.collapse_all(en-us,AX.60).gif").NET Interop from X++

The .NET interop from X++ feature enables you to call .NET Framework managed methods from your X++ code. For more information about this form of interoperation, see [.NET Interop from X++](net-interop-from-x.md). By contrast, the .NET Business Connector enables you to call X++ methods from your .NET managed code (such as from C\#).

### ![Aa659581.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa659581.collapse_all(en-us,AX.60).gif").NET Interop to X++

There are different technologies for interoperation from .NET Framework code to X++ code:

  - .NET Business Connector

  - [Proxy classes](proxy-classes-for-net-interop-to-x.md), written in C\# or Visual Basic by Microsoft Visual Studio, which encapsulate an X++ class or table

## In This Section

This section contains the following topics:

[Walkthrough: Integrate an Application with Microsoft Dynamics AX Using .NET Business Connector](walkthrough-integrate-an-application-with-microsoft-dynamics-ax-using-net-business-connector.md)

[How to: Create Data Using .NET Business Connector](how-to-create-data-using-net-business-connector.md)

[How to: Read Data Using .NET Business Connector](how-to-read-data-using-net-business-connector.md)

[How to: Update Data Using .NET Business Connector](how-to-update-data-using-net-business-connector.md)

[How to: Delete Data Using .NET Business Connector](how-to-delete-data-using-net-business-connector.md)

[How to: Call Business Logic Using .NET Business Connector](how-to-call-business-logic-using-net-business-connector.md)

[How to: Debug X++ Code Running in .NET Business Connector](how-to-debug-x-code-running-in-net-business-connector.md)

[How to: Connect to Microsoft Dynamics AX Using the LogonAs Method](how-to-connect-to-microsoft-dynamics-ax-using-the-logonas-method.md)

[Security and .NET Business Connector Applications](security-and-net-business-connector-applications.md)

## See also

[Integration with Microsoft Dynamics AX](integration-with-microsoft-dynamics-ax.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

