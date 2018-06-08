---
title: 'How to: Substitute Primitive Parameter Types Between the CLR and X++'
TOCTitle: 'How to: Substitute Primitive Parameter Types Between the CLR and X++'
ms:assetid: 4a8d388a-8cbe-4457-8997-8174f5bac08d
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc598473(v=AX.60)
ms:contentKeyID: 35243237
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Substitute Primitive Parameter Types Between the CLR and X++ 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

In Microsoft Dynamics AX, an X++ str type can be passed in a call to a .NET Framework method or X++ method that requires a System.String parameter as its input. However, substitutions in the other direction are not supported. An X++ method that requires an str parameter does not accept a System.String.

The same rule applies to the other X++ primitive types and their [.NET Framework counterparts](how-to-marshal-between-x-and-clr-primitive-types.md). Therefore an X++ int parameter can be passed to a method that takes a System.Int32. But a System.Int32 cannot be passed into a method that takes an X++ int.

It makes no difference whether the method that takes the parameter is a .NET Framework method or an X++ method.

## See also

[.NET Interop from X++](net-interop-from-x.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

