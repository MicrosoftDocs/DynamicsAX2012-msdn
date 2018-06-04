---
title: Session Object
TOCTitle: Session Object
ms:assetid: 0b643829-dc31-4aa2-84eb-b27fc63276ad
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc581944(v=AX.60)
ms:contentKeyID: 28119403
ms.date: 11/07/2012
mtps_version: v=AX.60
dev_langs:
- csharp
---

# Session Object 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

When adding code to User Controls for Enterprise Portal, many of the methods that you will use in the Enterprise Portal framework require access to the Session object.

## Accessing the Session Object

The Session object can be accessed through the web part that is hosting the User Control. The following using statement is required to access the object.

``` csharp
using Microsoft.Dynamics.Framework.BusinessConnector.Session;
```

A helper method is typically used to make accessing the Session object simple. The following private method can be added to the code for a User Control to provide access to the Session object.

``` csharp
private ISession AxSession
{
    get
    {
        AxBaseWebPart webpart = AxBaseWebPart.GetWebpart(this);
        return webpart == null ? null : webpart.Session;
    }
}
```

## Using the Session object

To access the Session object by using the helper method in the previous example, just access the AxSession property defined by the private method. The following example shows how the Session object is used when metadata for a table is retrieved.

``` csharp
int custTableNum;
custTableNum = TableMetadata.TableNum(this.AxSession, "CustTable");
```

