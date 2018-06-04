---
title: 'How to: Create a Chart with Data from an Analysis Services Cube'
TOCTitle: 'How to: Create a Chart with Data from an Analysis Services Cube'
ms:assetid: fa936f30-9c6e-4d06-a605-5d4ee949c9f2
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh965688(v=AX.60)
ms:contentKeyID: 46332001
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# How to: Create a Chart with Data from an Analysis Services Cube 


_**Applies To:** Microsoft Dynamics AX 2012 R2_

You can create your own Chart Controls for use on Enterprise Portal pages. A Chart Control is a User Control you can use to display chart data from a Report Data Provider (RDP) class or from an Analysis Services cube.

This topic describes how to use the features in Microsoft Dynamics AX and Visual Studio to create and deploy a Chart Control that displays analysis cube data. Chart Controls are created by using an EP Web Application project in Visual Studio. For more information about how to create an EP Web Application project, see [How to: Create an EP Web Application Project](how-to-create-an-ep-web-application-project.md). For information about Chart Controls that display RDP data, see [How to: Create a Chart with Data from a Report Data Provider Class](how-to-create-a-chart-with-data-from-a-report-data-provider-class.md).

## Adding a New Chart Control

### To add a new Chart Control

1.  Start Visual Studio. If User Account Control (UAC) is active, be sure you start Visual Studio with administrative privileges.

2.  Open the EP Web Application project for which you are creating a Chart Control.

3.  Select the project in Solution Explorer.

4.  In the **Project** menu, click **Add New Item**.

5.  In the **Add New Item** window, expand the **Visual C\#** group of installed templates.

6.  Click **Microsoft Dynamics AX**.

7.  Select **EP Chart Control**.

8.  Name the new Chart Control. The name entered identifies the chart in SharePoint.

9.  Click **Add**. The new Chart Control is added to the project and in the AOT.

## Designing a New Chart Control

To design a Chart Control, you will use the graphical design view in Visual Studio. There will also be cases where you will modify the source code for the Chart Control directly.

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

4.  Verify that the **DataType** property is set to **MDXQuery**, to indicate that the data is coming from an Analysis Services cube.

5.  In the **CommandText** property, click the ellipsis button (...) to open the OLAP query builder. Enter a Multidimensional Expression (MDX) query string to access analysis cube data. For information about MDX syntax, see [MDX Query Fundamentals](http://go.microsoft.com/fwlink/?linkid=247282).

6.  Click the execute query **\!** button. The results of the MDX query are displayed.
    

    > [!NOTE]
    > <P>The column headers of the results provide the XValueMember value and YValueMembers value to update the Series property in the next step.</P>



7.  Click **OK** to save the query text.

8.  In the **Design**, right-click the **\[ChartControlName\]Chart** component in the layout, and then click **Properties**.

9.  In the **Series** property, click the ellipsis (…) button to open the **Series Collection Editor**.

10. In the **Series Collection Editor**, set the **XValueMember** and the **YValueMembers** property to the column header results when you executed the MDX query.

11. Click **OK** to save the Series value members.

12. Use the Properties window to change the appearance and behavior of the chart. For example, you can add text to the **Titles** property that will be displayed as a title on the chart.

13. In Solution Explorer, right-click \[ChartControlName\].ascx and then click **View Markup**. The command text and series values contain the values that you entered in the **CommandText** property and **Series** property. Add code to the markup file for the Chart Control to provide further detail.

14. In Solution Explorer, right-click \[ChartControlName\].ascx and then click **View Code** to view the source that defines the Chart Control. If required, add any code to the code-behind file for the Chart Control.

15. Save the Chart Control by making the .ascx file for the control active in Visual Studio, and then clicking **Save** in the **File** menu. The control will be saved. It will also be updated in the AOT.

## Compiling a New Chart Control in the AOT

To have security work correctly for the new Chart Control, you must compile it in the AOT. Be sure that the new Chart Control has been saved in Visual Studio, which will add the Chart Control to the AOT.

### To compile a new Chart Control in the AOT

1.  In the AOT, expand the **Web** node, and then expand the **Web Files** node.

2.  Expand the **Web Controls** node and locate the new Chart Control that you created.

3.  Right-click the new Chart Control and then click **Compile**.

4.  Verify that there are no compiling errors. If there are, correct them in Visual Studio and then compile again.

Next you can add the User Control web part to an existing page, such as a Role Center page. For information about how to display a chart in an existing page, see [How to: Add Web Parts](how-to-add-web-parts.md).

## See also

[Walkthrough: Creating a Chart Control with Data from an Analysis Services Cube](walkthrough-creating-a-chart-control-with-data-from-an-analysis-services-cube.md)

