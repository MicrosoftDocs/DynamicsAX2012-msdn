---
title: Proxies and Exception Mapping
TOCTitle: Proxies and Exception Mapping
ms:assetid: 1ef2ca93-f0d0-4611-88bc-b2f8565b738f
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg844127(v=AX.60)
ms:contentKeyID: 35241488
ms.date: 05/18/2015
mtps_version: v=AX.60
dev_langs:
- csharp
---

# Proxies and Exception Mapping 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

When an X++ object throws an exception, the exception value is an integer element from the X++ Exception enum. If the X++ object is being managed by a proxy object in the .NET Framework, the thrown element value of the enum is automatically marshaled into an instance of a .NET Framework exception class. This class is designed to represent the enum element.

## Name Pattern

There is a pattern of name correspondence between values of the X++ Exception enum and the .NET Framework exception classes that represent the enum values. There are approximately 15 elements in the Exception enum. The following table shows 3 examples of the pattern. For instance, the last row in the table shows that the enum element and the exception class are both named with the word Deadlock.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>X++ Exception enum element</p></th>
<th><p>Word in common</p></th>
<th><p>.NET Framework exception class</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Exception::Error</p></td>
<td><p>Error</p></td>
<td><p>Microsoft.Dynamics.AX.ManagedInterop.ErrorException</p></td>
</tr>
<tr class="even">
<td><p>Exception::Warning</p></td>
<td><p>Warning</p></td>
<td><p>Microsoft.Dynamics.AX.ManagedInterop.WarningException</p></td>
</tr>
<tr class="odd">
<td><p>Exception::Deadlock</p></td>
<td><p>Deadlock</p></td>
<td><p>Microsoft.Dynamics.AX.ManagedInterop.DeadlockException</p></td>
</tr>
</tbody>
</table>


## Inheritance Hierarchy of the .NET Exception Classes

The following indented list of .NET exception classes shows the inheritance hierarchy of the ErrorException class. This is one of the exception classes that a proxy object might encounter if the underlying X++ object has a problem. The inheritance hierarchy is the same for the other exceptions such as Microsoft.Dynamics.AX.ManagedInterop.WarningException.

``` csharp
System.Exception
   Microsoft.Dynamics.AX.ManagedInterop.XppBaseException
      Microsoft.Dynamics.AX.ManagedInterop.ManagedInteropException
         Microsoft.Dynamics.AX.ManagedInterop.XppException
            Microsoft.Dynamics.AX.ManagedInterop.ErrorException
```

## Exceptions Not From the X++ Object

A proxy object can encounter exceptions that have nothing to do with the behavior of its underlying X++ object. For example, if the Application Object Server (AOS) is stopped by the administrator, the proxy can encounter a Microsoft.Dynamics.AX.ManagedInterop.ServerUnavailableException. This ServerUnavailableException class extends the Microsoft.Dynamics.AX.ManagedInterop.ManagedInteropException class.

## See also

[Proxy Classes for .NET Interop to X++](proxy-classes-for-net-interop-to-x.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

