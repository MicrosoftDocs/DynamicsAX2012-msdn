---
title: X++ Language Programming Guide
TOCTitle: X++ Language Programming Guide
ms:assetid: c802a799-5993-4935-9275-4d7f4216264f
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa867122(v=AX.60)
ms:contentKeyID: 35251188
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# X++ Language Programming Guide 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

X++ is an object-oriented language with similarities to C\#. X++ is part of the MorphX development platform that you use to construct accounting and business management systems.

The memory management model of X++ is simple. Objects are created with a new operator. There are no explicit programmer-defined pointer data types, and there is no pointer arithmetic.

X++ provides system classes for a broad range of system programming areas, a few of which are as follows:

  - File input and output.

  - Reflection on classes and tables.

  - Manipulation of user interface items such as forms and reports.

  - Dynamic array support.

  - Collections of objects.

  - XML building and parsing.

In addition to its system classes, Microsoft Dynamics AX also provides application classes for managing many types of business processes. For reference information about the system and application classes in Microsoft Dynamics AX, see [Classes](https://msdn.microsoft.com/en-us/library/aa660868\(v=ax.60\)).

X++ programmers can access the relational tables in Microsoft Dynamics AX. X++ includes keywords that match most of the keywords in standard SQL. For information about X++ SQL keywords, see [Data Selection and Manipulation](data-selection-and-manipulation.md) and the table of contents underneath it. For reference information about the tables in Microsoft Dynamics AX, see [Tables](https://msdn.microsoft.com/en-us/library/cc652476\(v=ax.60\)).

X++ code is checked for syntax errors during compile time. The compile process also performs best practice checks. Violations of best practices can generate compiler messages. For more information, see [Best Practices for Microsoft Dynamics AX Development](best-practices-for-microsoft-dynamics-ax-development.md).

The X++ runtime execution engines have automatic mechanisms to discard objects that are no longer referenced, so that their memory space can be reused.

Microsoft Dynamics AX supports interoperability between classes written in X++ and in C\# (or other .NET Framework languages). For more information, see [.NET Interop from X++](net-interop-from-x.md) and [Proxy Classes for .NET Interop to X++](proxy-classes-for-net-interop-to-x.md).

## In This Section

[Variables and Data Types](variables-and-data-types.md)

[Statements and Loops](statements-and-loops.md)

[Operators](operators.md)

[Data Selection and Manipulation](data-selection-and-manipulation.md)

[Attributes on X++ Types and Methods](attributes-on-x-types-and-methods.md)

[Classes and Methods](classes-and-methods.md)

[Event Terminology and Keywords](event-terminology-and-keywords.md)

[X++, C\# Comparisons](x-csharp-comparisons.md)

[Functions and Macros](functions-and-macros.md)

[X++ Syntax](x-syntax.md)

[X++ Compiled to .NET CIL](x-compiled-to-net-cil.md)

[X++ Scenarios that are Not Supported in CIL](x-scenarios-that-are-not-supported-in-cil.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

