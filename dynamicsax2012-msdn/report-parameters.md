---
title: Report Parameters
TOCTitle: Report Parameters
ms:assetid: a80f9628-d3e7-4978-9560-e0bcca2dcef9
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh330284(v=AX.60)
ms:contentKeyID: 36806098
ms.date: 11/07/2012
mtps_version: v=AX.60
dev_langs:
- xml
- csharp
---

# Report Parameters [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The parameters passed to the SSRS report are important in controlling how the report is processed. The following sections describe issues that you should consider when you are working with parameters for SSRS reports that are displayed in Enterprise Portal.

## SysQuery Parameters

The reports that are accessed from Enterprise Portal cannot use any of the SysQuery parameters that are available when the report is run from the Microsoft Dynamics AX client. You will see these as "DynamicParameter" types in the SSRS report definition. The other parameters are available.

## Default Parameters

When you add a report to a page in Enterprise Portal, the [SSRS Report Web Part](ssrs-report-web-part.md) will use the default values for any available parameters. However, the report may not have default values for the parameters. If you decide to use the default values, but the report does not have any defined, the report will not be displayed. Check the report definition in the Report Builder or Visual Studio to verify whether specific parameters have default values.

Before you add a report to an Enterprise Portal page, you may want to try the actual parameter values that you want to use with the report. In the Report Manager it is easier to change the parameters and then view the report that has modified parameter values.

## Passing Parameters through Code

You may want users to input the parameter values before they display the report. To do this, you can create a User Control that has fields that let the user supply the parameter values. Typically the User Control will have a button that adds the parameters to the report, and then displays the report. The User Control must have the [AxReportViewer](axreportviewer.md) component to display the report. The report will not display until it has all of the required parameter values.


> [!TIP]
> <P>The SalesRankingReport is an example of a report in Enterprise Portal that uses this technique.</P>



In another example of this technique, the **Cash inflow vs. cash outflow** report takes one optional parameter that specifies the end date for the report. In a User Control, the following markup code uses the AxReportViewer component to reference this report.

``` xml
<dynamics:AxReportViewer ID="AxReportViewer1" runat="server" 
    MenuItemName="CustCashInflowvsCashOutflow" AsyncRendering="False" />
```

The following markup code adds a calendar control to the User Control.

``` xml
<asp:Calendar ID="Calendar1" runat="server" Caption="End Date" 
    onselectionchanged="Calendar1_SelectionChanged"></asp:Calendar>
```

The following code is the Calendar1\_SelectionChanged event. This event occurs when the user selects a new date from the calendar. In the event, the value of the date selected is used as the value for the **P1CashInflowvsCashOutflow\_EndDate** parameter for the report.

``` csharp
protected void Calendar1_SelectionChanged(object sender, EventArgs e)
{
    Dictionary<string, object> parms = new Dictionary<string, object>();
 
    parms.Add("P1CashInflowvsCashOutflow_EndDate", this.Calendar1.SelectedDate.ToShortDateString());
 
    this.AxReportViewer1.AddParameters(parms);
}
```

