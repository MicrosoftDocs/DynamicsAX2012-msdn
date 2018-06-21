---
title: Retrieving the Current Company
TOCTitle: Retrieving the Current Company
ms:assetid: 2ca1859c-e793-4b6f-9fe2-a87313013510
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh812492(v=AX.60)
ms:contentKeyID: 44090278
ms.date: 11/07/2012
mtps_version: v=AX.60
dev_langs:
- csharp
---

# Retrieving the Current Company [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

When adding code to User Controls, you may want to know the company that the user is accessing. A method in the ControlHelper class from the Microsoft.Dynamics.Framework.Portal.CommonControls namespace simplifies this process. To access this namespace, you must add the following reference to your code.

``` csharp
using Microsoft.Dynamics.Framework.Portal.CommonControls;
```

The GetCurrentSessionCompany method is a static method for the ControlHelper class. The method returns the current company for the Enterprise Portal session as an uppercase string value. The method requires that you supply the [Session Object](session-object.md). The following example code for a User Control retrieves the current company and displays the value in a text box.

``` csharp
protected void GetCompany_Click(object sender, EventArgs e)
{
    CompanyTextBox.Text = ControlHelper.GetCurrentSessionCompany(AxSession);
}
```

## See also

[Session Object](session-object.md)

