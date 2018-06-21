---
title: DateTime Helper
TOCTitle: DateTime Helper
ms:assetid: ab05c519-935a-43d1-9e8e-cf0b8296653d
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh812511(v=AX.60)
ms:contentKeyID: 44090297
ms.date: 11/07/2012
mtps_version: v=AX.60
dev_langs:
- csharp
---

# DateTime Helper [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

In Microsoft Dynamics AX you can set the preferred time zone. To get the date/time value that considers the preferred time zone, use the AxDateTimeHelper class. This class is part of the Microsoft.Dynamics.Framework.Portal.UI namespace. You will use the [Session Object](session-object.md) when you retrieve the value.

For example, the following code for a button in a User Control retrieves the current date and time. The local time and the UTC time are derived from this value and displayed in text boxes in the User Control.

``` csharp
protected void WhatTimeIsIt_Click(object sender, EventArgs e)
{
    DateTime dt = AxDateTimeHelper.GetUserNow(AxSession);

    LocalTime.Text = dt.ToString();
    UTCTime.Text = dt.ToUniversalTime().ToString();
}
```

## See also

[Session Object](session-object.md)

