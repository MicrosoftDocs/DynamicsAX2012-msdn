---
title: Designing Reports for Enterprise Portal
TOCTitle: Designing Reports for Enterprise Portal
ms:assetid: e03670eb-7861-48b1-b2fe-f5c7a41db65a
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh330356(v=AX.60)
ms:contentKeyID: 36806169
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# Designing Reports for Enterprise Portal 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

To provide the best user experience for SSRS reports in Enterprise Portal, use these guidelines when you are designing your reports.

## Layout

When you create a report for use in Enterprise Portal, consider the page on which the report will be displayed. If the report is included on a page with limited space, the existing design for the report may not be usable. Consider adding a separate design for the report that can be used specifically when the report is displayed in Enterprise Portal.

## Parameters

When you are designing a report for use in Enterprise Portal, consider providing default values for the report parameters whenever possible. This makes it much easier for the user to add the report to an Enterprise Portal page, because the report will run without requiring parameters to be set. The user can adjust the parameters as necessary after the report has been added to the page.

## Drill-through

The report drill-through improves the usability for a report because it lets the user access related information for the data displayed in the report. When you create a report for use in Enterprise Portal, consider whether there are pages that you could link to that display additional information for data in the report. Typically, Entity Overview pages are used to display related data for a report.

To create a drill-through that works for a report in Enterprise Portal, use the following basic procedure:

### To create a drill-through

1.  Identify the page to be displayed when the link in the report is clicked. Typically this will be an Entity Overview page in Enterprise Portal.

2.  Create a web menu item that links to the page that you want to display when the link in the report is clicked.

3.  Add a data method to the report. The code for the method will perform the drill-through action. The following example is a data method that performs the drill-through for the HcmWorker field in a report. Notice that the code is specifying the table and value to pass through the link. Another important area to notice is that the context is retrieved to determine whether the report is running in the Microsoft Dynamics AX client or in Enterprise Portal. Then the corresponding parameters are passed to the GenerateLinkToAXMenuItem() method for the DrillthroughHelper object.
    
        using System;
        using System.Collections.Generic;
        using System.Security.Permissions;
        using System.Data;
        using Microsoft.Dynamics.Framework.Reports;
        
        public partial class Rooms
        {
            [DataMethod(), PermissionSet(SecurityAction.Assert, Name = "FullTrust")]
            public static string DrillthroughToHcmWorker(string reportContext, object fieldValue)
            {
                string tableName = "HcmWorker";
                Dictionary<string, object> fields = new Dictionary<string, object>();
                fields.Add("RecId", fieldValue);
        
                if (RuntimeReportContext.IsClientContext(reportContext))
                {
                    // The report is being run from the Microsoft Dynamics AX client.
                    return DrillthroughHelper.GenerateLinkToAXMenuItem(reportContext, "HcmWorker", MenuItemType.Display, tableName, fields);
                }
                else
                {
                    // The report is being run from Enterprise Portal.
                    return DrillthroughHelper.GenerateLinkToAXMenuItem(reportContext, "HcmEPMyEmployeeInfo", MenuItemType.WebMenuItemTypeUrl, tableName, fields);
                }
            }
        }

4.  In the design for the report, display the data field that will have the drill-through action. Right-click the field, click **Add**, and then click **URL Drill Through Action**.

5.  Select the new URL drill through action. In the **Properties** list, display the list for the **Expression** property. Click **\<Expression…\>** to open the **Edit Expression** window.

6.  Expand the **Methods** node and then click **Data methods**. Double-click the drill-through method that you created.

7.  Add parentheses and supply values for the reportContext and fieldValue objects. The reportContext is passed using the AX\_ReportContext in the Parameters group. The fieldValue is passed using one of the fields from the Fields group. The following is the expression for the drill-through to a worker.
    
    \=DrillthroughToHcmWorker(Parameters\!AX\_ReportContext.Value,Fields\!AssignedToRecId.Value)

8.  Save the changes to the report.

9.  Deploy the updated report to the reports server.

