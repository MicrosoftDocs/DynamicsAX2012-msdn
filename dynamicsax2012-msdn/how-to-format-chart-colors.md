---
title: 'How to: Format Chart Colors'
TOCTitle: 'How to: Format Chart Colors'
ms:assetid: bc2c0767-55a8-40dc-add4-1fbed1308d2a
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ677315(v=AX.60)
ms:contentKeyID: 49384086
ms.date: 11/07/2012
mtps_version: v=AX.60
dev_langs:
- csharp
---

# How to: Format Chart Colors 


_**Applies To:** Microsoft Dynamics AX 2012 R2_

The Microsoft Dynamics AX framework provides automatic chart formatting. You can use the default chart colors or specify the color specifically. You can specify the chart colors in the chart behavior properties or programmatically in the control class definition. For example, you could assign a color palette to charts based on what company data is displayed.

### To Specify Chart Colors in Properties

1.  In your Visual Studio chart project, in design view, select the **AxChartBehavior**.

2.  In the Properties window, set the **UseAXColors** property to **False**.

3.  Click the **Palette** ellipsis button (…). The **Palette Collection Editor** opens.

4.  Click the **Add** button. A **Microsoft.Dynamics.Framework.Portal.UI.WebControls.Palette** member is added.

5.  Click the **Color** dropdown to select a color palette and then click **OK**.

6.  Click **Save** to update the color changes.

### To Specify Chart Colors in Code

1.  In your Visual Studio chart project, in Solution Explorer, double-click the **\[ChartName\].ascx.cs** control class definition to open the class in code editor.

2.  The following code example will set the chart color to dark red.
    
    ``` csharp
    protected void Page_Load(object sender, EventArgs e)
        {
            // Set the AxChartBehavior to not use Microsoft Dynamics AX colors.
            this. MyAxChartBehavior.UseAXColors = false;
    
            // Set the color value of the palette.
            this.MyAxChartBehavior.Palette.Add(new Palette(ChartColors.RedDark));
        }
    ```

## See also

[Chart Controls Overview](chart-controls-overview.md)

