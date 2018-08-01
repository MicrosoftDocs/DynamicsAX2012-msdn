---
title: Setting Up the Tracing Tools
TOCTitle: Setting Up the Tracing Tools
ms:assetid: 439f6fad-93be-4cc5-930c-400187dd22b8
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa637570(v=AX.60)
ms:contentKeyID: 35242956
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Setting Up the Tracing Tools [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Microsoft Dynamics AX tracing tools monitor or diagnose the state of the system.

Tracing tools are provided for development and testing, and to monitor client/server traffic in production environments.

To enable tracing for development:

  - Click **Tools** \> **Options**, and then click the **SQL** tab. A check box on the top of the tab makes it easy to enable or disable a complete set of trace settings. After this box is selected, all other options on the form are made available.

## Kinds of Trace

Four different kinds of traces can be set up: **Multiple SQL statements**, **Long queries**, **Warnings**, and **Deadlocks**.

The **Long queries** trace is not enabled until a positive value is entered in the **Threshold** field. The unit of measure is milliseconds.

Traces can be directed to four output media:

  - **Message window**: Used for quick and instant display. This is typically used for simple tracing during development.

  - **Infolog**: Enables information to be accumulated and provides an interface to the SQL Diagnostics tools.

  - **Table (database)**: Used to store large amounts of trace information. If you select this option, trace data is written to the **SysTraceTableSQL** table, and can be viewed in the SQL statement trace log form.

  - **Write to file**: Used to store large amounts of trace information.

For more information about each type of trace, see [Tracing with the Tools Menu](tracing-with-the-tools-menu.md).

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

