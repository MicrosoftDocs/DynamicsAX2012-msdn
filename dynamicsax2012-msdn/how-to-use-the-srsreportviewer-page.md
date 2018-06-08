---
title: 'How to: Use the SRSReportViewer Page'
TOCTitle: 'How to: Use the SRSReportViewer Page'
ms:assetid: c1c592a0-7b09-49f2-9868-25696f1744d6
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh330354(v=AX.60)
ms:contentKeyID: 36806167
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# How to: Use the SRSReportViewer Page 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The main Enterprise Portal site contains a Report Viewer page that you can use to display SSRS reports. The page is named **SRSReportViewer.aspx**. To use the Report Viewer page, you supply the URL to access the page. The query string passed on the URL indicates which report to display, how the viewer is configured, and the parameters passed to the report.

The Report Viewer page is sometimes used as a simple way to display reports. You can also use it when you create report drill-through actions for SSRS reports that are displayed in Enterprise Portal.

## Using the SRSReportViewer Page

### To use the SRSReportViewer page

1.  Start with the base URL for the Report Viewer page. The base URL is:
    
    http:// *server*/sites/DynamicsAx/Enterprise%20Portal/SRSReportViewer.aspx

2.  Add the query parameter that specifies the menu item identifying the report to display. The query parameter has the following syntax:
    
    ?MenuItemName=*name*
    
    For *name*, substitute the name of the menu item for the report.

3.  Add the query parameter that specifies the toolbar configuration. The query parameter has the following syntax:
    
    \&ReportViewerToolbarSize=*size*
    
    The possible size values are **None**, **Small**, or **Full**.

4.  Add a query parameter for each report parameter that is needed for the report. The query parameter has the following syntax:
    
    \&MainReport.Parameters. *name*=*value*
    
    For *name*, substitute the name of the report parameter. For *value*, supply the value to use for the report parameter.

## Example

The following example shows a complete URL to display the **Cash inflow vs. cash outflow chart** in the SRSReportViewer.aspx page. The full toolbar is shown for the report. The report has one parameter named P1CashInflowvsCashOutflow\_EndDate.

http://devep/sites/DynamicsAx/Enterprise%20Portal/SRSReportViewer.aspx?MenuItemName=CustCashInflowvsCashOutflow\&ReportViewerToolbarSize=Full\&MainReport.Parameters.P1CashInflowvsCashOutflow\_EndDate=06/19/2011

