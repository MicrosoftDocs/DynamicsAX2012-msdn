---
title: Using the Infolog
TOCTitle: Using the Infolog
ms:assetid: 994d9753-9bf4-456e-9044-0268c40c80fb
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc606908(v=AX.60)
ms:contentKeyID: 28119455
ms.date: 11/07/2012
mtps_version: v=AX.60
dev_langs:
- csharp
---

# Using the Infolog 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

As you add code to User Controls, you may have situations that require communicating important information to the user. Do this by sending a message to the Infolog that is displayed on the page. The Infolog is a separate web part on the page. It is automatically included on new pages that you create for Enterprise Portal.

## Accessing the Infolog

The Infolog is accessed through the .NET Business Connector proxy for Enterprise Portal. To access the .NET Business Connector proxy, you must add the following reference to your code so the items in the proxy can be accessed.

``` csharp
using Proxy = Microsoft.Dynamics.Framework.BusinessConnector.Proxy;
```

You must create an instance of the Info object to be able to work with the Infolog. This is shown in the following example.

``` csharp
Proxy.Info objInfoLog = new Proxy.Info(this.AxSession.AxaptaAdapter);
```

## Writing to the Infolog

Several message types can be written to the Infolog. The Exception enumeration defined in the Enterprise Portal proxy defines the various types. The most common message types are listed in the following table.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Error type</p></th>
<th><p>Enumeration value</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Information</p></td>
<td><p>Exception.Info</p></td>
</tr>
<tr class="even">
<td><p>Warning</p></td>
<td><p>Exception.Warning</p></td>
</tr>
<tr class="odd">
<td><p>Error</p></td>
<td><p>Exception.Error</p></td>
</tr>
</tbody>
</table>


To add a message to the Infolog, use the add() method for the Info object. The following example adds a warning message to the Infolog.

``` csharp
objInfoLog.add(Proxy.Exception.Warning, "This is a warning sent to the Infolog");
```

## Clearing the Infolog

When you add a message to the Infolog, any messages that are currently displayed will remain. This allows for the Infolog to display multiple messages at the same time. To clear the Infolog of any messages that have been added to it, use the clear() method for the Info object. The following example clears the Infolog.

``` csharp
objInfoLog.clear(0);
```

## See also

[Infolog Web Part](infolog-web-part.md)

[Session Object](session-object.md)

