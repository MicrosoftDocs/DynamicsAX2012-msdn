---
title: 'How to: Add SSRS Reports to Pages'
TOCTitle: 'How to: Add SSRS Reports to Pages'
ms:assetid: 4375201f-2fd5-4030-af42-0fb581436106
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc553120(v=AX.60)
ms:contentKeyID: 35245285
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# How to: Add SSRS Reports to Pages 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Reports that have been created in SQL Server Reporting Services (SSRS) can be displayed on Enterprise Portal pages. To add SSRS reports to pages in Enterprise Portal, you must make them available and then add a [SSRS Report Web Part](ssrs-report-web-part.md) to the page to display the report.

## Making SSRS Reports Available

### To make SSRS reports available

1.  In the AOT, expand the **Menu Items** node, and then expand the **Output** node.

2.  Right-click **Output**, and then click **New Menu Item**.

3.  Right-click the new menu item that you added, and then click **Properties**.

4.  In the property sheet, do the following:
    
    1.  Click **ObjectType**. Select **SSRSReport**.
    
    2.  For the **Object** property, specify the name of the SSRS report that you want to make available. This is the name as you defined it in the Report Designer.
    
    3.  For the **ReportDesign** property, specify the design that you want to use for the report. Choose one of the designs that you created when you made the report.
    
    4.  Modify other properties as needed.

5.  Save the changes in the AOT.

## Adding a Report Web Part to a Page

### To add a Report web part to a page

1.  To add a web part to a page, use the procedure that is described in [How to: Add Web Parts](how-to-add-web-parts.md).

2.  When you specify the properties of the Report web part, the **Report selection** property lists the names of the SSRS reports that have had menu items created for them and can be used in Enterprise Portal. See [Accessible Reports for Enterprise Portal](accessible-reports-for-enterprise-portal.md) for more information about which reports you can use. Choose the report that you want to display.

3.  If the SSRS report uses parameters, you can use the **Report parameters** to set them.

4.  Specify the **Toolbar size** property to indicate whether a toolbar should be displayed for the web part.

5.  Specify the **Report drillthrough target toolbar size** property to specify the size of the toolbar that is displayed when report drill-through is used.

6.  Set the **Title** property to a name appropriate for the report. This title will be displayed in the Report web part.

7.  Set the **Width** and **Height** properties so the SSRS report will display optimally.

8.  Save the changes for the web part and page.

9.  Display the page that contains the report.

