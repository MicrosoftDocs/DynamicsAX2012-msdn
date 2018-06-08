---
title: 'How to: Create a Chart with Data from a Report Data Provider Class'
TOCTitle: 'How to: Create a Chart with Data from a Report Data Provider Class'
ms:assetid: ab336a00-792e-4b9e-ab5e-9fac1a8b8ca4
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh975424(v=AX.60)
ms:contentKeyID: 46357771
ms.date: 11/07/2012
mtps_version: v=AX.60
f1_keywords:
- Report Data Provider
- RDP EP Chart Control
- ReportDataProvider
- RDP Data Type
- RDP Data for a Chart Control
- EP Chart Control
- Chart Control
---

# How to: Create a Chart with Data from a Report Data Provider Class 


_**Applies To:** Microsoft Dynamics AX 2012 R2_

You can create your own Chart Controls for use on Enterprise Portal pages. A Chart Control allows many different ways of populating data in a chart. The Visual Studio tools for Microsoft Dynamics AX provides specific support to display data from a Report Data Provider (RDP) class or from an analysis cube.

This topic provides the summary steps about how to use the features in Microsoft Dynamics AX and Visual Studio to create and deploy a Chart Control that displays data from an RDP class. Chart Controls are created by using an EP Web Application project in Visual Studio. For more information about how to create an EP Web Application project, see [How to: Create an EP Web Application Project](how-to-create-an-ep-web-application-project.md). For information about Chart Controls that display Analysis Services cube data, see [How to: Create a Chart with Data from an Analysis Services Cube](how-to-create-a-chart-with-data-from-an-analysis-services-cube.md).

Most RDP classes have parameters. Parameters provide ways to choose data, connect related charts together, and vary the chart presentation. They are used when generating the chart data set. The parameters that an RDP class will reference are defined in a data contract class. The following two classes are required to be able to set **ReportDataProvider** as your data source type on a chart with parameters.

  - Data Contract Class – defines the parameters in the report.

  - Report Data Provider Class – processes business logic based on a query and parameters defined in the data contract class, and then returns the tables as a dataset for the report.

For information about how to define RDP classes and data contract classes, see [How to: Use a Report Data Provider Class in a Report](https://msdn.microsoft.com/en-us/library/gg731917\(v=ax.60\)).

## Adding a New Chart Control

### To add a new Chart Control

1.  Start Visual Studio. If User Account Control (UAC) is active, make sure that you start Visual Studio with administrative privileges.

2.  Open the EP Web Application project for which you are creating a Chart Control.

3.  Select the project in Solution Explorer.

4.  In the **Project** menu, click **Add New Item**.

5.  In the **Add New Item** window, expand the **Visual C\#** group of installed templates.

6.  Click **Microsoft Dynamics AX**.

7.  Select **EP Chart Control**.

8.  Name the new Chart Control. The name entered identifies the chart in SharePoint.

9.  Click **Add**. The new Chart Control is added to the project and in the AOT.

## Designing a New Chart Control

To design a Chart Control, use editors and tools that make it possible for you to create and modify chart components. There are two editing views:

  - **Design view** Use this view to edit charts graphically, make changes in the properties window and see the results instantly.

  - **Source view** Use this view to edit charts directly, insert asp tags and validate your markup.

### To design a new Chart Control

1.  In **Solution Explorer**, right-click the \[ChartControlName\].ascx.

2.  Click **View Designer** to view the graphical layout for the Chart Control.
    
    The following components are included in the layout for the chart:
    
      - AxChartDataSource - **\[ChartControlName\]DataSource**
    
      - Chart - **\[ChartControlName\]Chart**
        
        The **DataSourceID** property of the chart has been set to **\[ChartControlName\]DataSource**.
    
      - AxChartBehavior - **\[ChartControlName\]Behavior**
        
        The **ChartID** property of the AxChartBehavior component has been set to **\[ChartControlName\]Chart**.

3.  Right-click the **AxChartDataSource – \[ChartControlName\]DataSource** component in the layout, and then click **Properties**.

4.  Set the **DataType** property to **ReportDataProvider**.

5.  In the **CommandText** property, click the ellipsis **(…)** button. The DataSource picker opens and the **Select a Microsoft Dynamics AX Report Data Provider** tab is displayed.

6.  Select the RDP class that accesses the data that you want on your chart.

7.  Click **Next**. The **Select Fields** tab displays the fields available to display in the chart.

8.  Select the fields that you want available to display on the report.
    

    > [!NOTE]
    > <P>Note the names of the fields that you select. From that list, you must provide the XValueMember value and YValueMembers value to update the Series property in the next step.</P>



9.  Click **OK**.

10. In the **Design**, right-click the **\[ChartControlName\]Chart** component in the layout, and then click **Properties**.

11. In the **Series** property, click the ellipsis (…) button to open the **Series Collection Editor**.

12. In the **Series Collection Editor**, set the **XValueMember** and the **YValueMembers** property from the names of the fields you selected when you selected the RDP class.

13. You can also change the type of chart to display. Click the **ChartType** dropdown to see the chart types that are supported.

14. Click **OK** to save the changes to the series collection.

15. Use the Properties window to change the appearance and behavior of the chart. For example, you can add text to the **Titles** property that will be displayed as a title on the chart.

16. In Solution Explorer, right-click \[ChartControlName\].ascx and then click **View Markup**. The command text and series values contain the values that you entered in the **CommandText** property and **Series** property.

17. Save the Chart Control by making the .ascx file for the control active in Visual Studio, and then clicking **Save** in the **File** menu. The control will be saved. It will also be updated in the AOT.

## Adding a Parameter

You must set the required parameter values before the data set will be constructed. The data contract of the RDP class specifies the parameters available in the data source. The following procedure describes how to add a parameter.

### To add a parameter

1.  In Solution Explorer, right-click the \[ChartName\].ascx file and then click **View Markup**.

2.  In the \<dynamics:AxChartDataSource\> tag, add the parameters defined in the data contract of the RDP class that you are using to access data for the chart. The following example provides the parameter values for two parameters called OutputSorting and OutputQty. Add this tag between the \<dynamics:AxChartDataSource\> tag and the \</dynamics:AxChartDataSource\> tag.
    
        <Parameters>
            <dynamics:ChartParameter Name="OutputSorting" Value="0" />
            <dynamics:ChartParameter Name="OutputQty" Value="5" />
        </Parameters>

3.  Press Ctrl+S to Save.

## Compiling a New Chart Control in the AOT

To have security work correctly for the new Chart Control, you must compile it in the AOT. Be sure that the new Chart Control has been saved in Visual Studio, which will add the Chart Control to the AOT.

### To compile a new Chart Control in the AOT

1.  In the AOT, expand the **Web** node, and then expand the **Web Files** node.

2.  Expand the **Web Controls** node and locate the new Chart Control that you created.

3.  Right-click the new Chart Control and then click **Compile**.

4.  Verify that there are no compiling errors. If there are, correct them in Visual Studio and then compile again.

Next you can add the User Control web part to an existing page, such as a Role Center page. For information about how to display a chart in an existing page, see [How to: Add Web Parts](how-to-add-web-parts.md).

## See also

[Chart Controls Overview](chart-controls-overview.md)

[Walkthrough: Creating a Chart Control with Data from a Report Data Provider Class](walkthrough-creating-a-chart-control-with-data-from-a-report-data-provider-class.md)

[Walkthrough: Creating a Chart Control with Data from an Analysis Services Cube](walkthrough-creating-a-chart-control-with-data-from-an-analysis-services-cube.md)

