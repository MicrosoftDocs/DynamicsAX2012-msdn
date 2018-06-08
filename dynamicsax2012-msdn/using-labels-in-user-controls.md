---
title: Using Labels in User Controls
TOCTitle: Using Labels in User Controls
ms:assetid: ba15b265-7cbc-4b02-91d9-5806a636faa6
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc574290(v=AX.60)
ms:contentKeyID: 28119485
ms.date: 11/07/2012
mtps_version: v=AX.60
dev_langs:
- xml
- csharp
---

# Using Labels in User Controls 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

When adding text that appears in User Controls, consider using labels so that the text can be more easily localized.

## Labels in Markup

You can use labels from Microsoft Dynamics AX in the markup for a User Control. Add a Label control from the **Toolbox** to the layout. Set the **Text** property to the following value, substituting the number of the label that contains the text you want to display.

\<%$axlabel:@SYS1234%\>

The text for the label will appear in the layout for the User Control. It will look like the following in the ASP.NET markup.

``` xml
<asp:Label ID="Label1" runat="server" Text="<%$axlabel:@SYS1234%>"></asp:Label>
```

## Labels in Code

Labels from Microsoft Dynamics AX can also be used in code for a User Control. The Labels class in the Microsoft.Dynamics.Framework.Portal.UI namespace provides the GetLabel method. Use this method to retrieve a label value. For example, the following code uses a label to set the text for a button that was added to a User Control.

``` csharp
protected void Page_Init(object sender, EventArgs e)
{
    // Set the button text to "Administration".
    Button1.Text = Labels.GetLabel("@SYS90142");
}
```

