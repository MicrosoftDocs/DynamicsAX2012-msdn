---
title: Chart Controls Overview
TOCTitle: Chart Controls Overview
ms:assetid: eb39c070-ddee-4dfd-89df-508a6bee847f
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh965689(v=AX.60)
ms:contentKeyID: 46332002
ms.date: 05/03/2013
mtps_version: v=AX.60
---

# Chart Controls Overview [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R2_

A Chart Control is a User Control option that enables you to display chart data in Enterprise Portal. A Chart Control provides good performance because the data needed for the chart to display is contained in the data set.

The Chart Control is an extension of the ASP.NET Chart Control. This topic describes the EP Chart Control. For information about the ASP.NET Chart Control, see [Chart Control](http://msdn.microsoft.com/en-us/library/dd456632.aspx).

## Elements of a Chart Control

The following table describes some of the elements that you can use in a Chart Control.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Chart Control Element</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Chart Title</p></td>
<td><p>A title on the chart. You can add any number of titles to a chart picture. This element corresponds to an item in the <strong>Titles</strong> collection.</p></td>
</tr>
<tr class="even">
<td><p>Legend</p></td>
<td><p>A legend for the chart. There can be more than one legend in a chart. This element corresponds to an item in the <strong>Legend</strong> collection.</p></td>
</tr>
<tr class="odd">
<td><p>Series</p></td>
<td><p>A related group of data points. Each series has an associated chart type. The number of series that a chart can display and how it displays the series depends on the chart type you specify. This element corresponds to the <strong>Series</strong> class.</p></td>
</tr>
<tr class="even">
<td><p>Axis Label</p></td>
<td><p>A label on an axis. It is generated automatically if no custom labels are supplied. This element corresponds to the <strong>Label</strong> class.</p></td>
</tr>
</tbody>
</table>


The following illustration shows these elements used in the chart.

![Elements of a Chart Control](images/Hh965689.EPChartControl(AX.60).gif "Elements of a Chart Control")

## Data for a Chart Control

A Chart Control can display data from a Report Data Provider (RDP) class or from an analysis cube. The following table provides information about which data source to use for the Chart Control.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Data source</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>RDP class</p></td>
<td><p>An RDP class contains X++ business logic to process data to display in a chart. Using an RDP class as a data source allows you to process the data at the time the chart is displayed, so the data is real time. To use an RDP class, set the <strong>DataType</strong> property of the AXChartDataSource to ReportDataProvider. You must provide an RDP class, data contract class, and a temp table to access data from an RDP class data source.</p>
<p>For more information, see <a href="how-to-create-a-chart-with-data-from-a-report-data-provider-class.md">How to: Create a Chart with Data from a Report Data Provider Class</a>.</p></td>
</tr>
<tr class="even">
<td><p>Analysis cube</p></td>
<td><p>An analysis cube consists of a set of measures and dimension attributes that provides the data to display in a chart. Using an analysis cube as a data source allows you to provide a snapshot of data from when the cube was processed. To use an analysis cube, set <strong>DataType</strong> property of the AXChartDataSource to MDXQuery. You must provide an MDX query to access data from a deployed and processed cube.</p>
<p>For more information, see <a href="how-to-create-a-chart-with-data-from-an-analysis-services-cube.md">How to: Create a Chart with Data from an Analysis Services Cube</a>.</p></td>
</tr>
</tbody>
</table>



> [!TIP]
> <P>It is a best practice to understand the data that will display in the chart and then decide how the data should be displayed. For information about which type of chart to use for your data, see <A href="http://go.microsoft.com/fwlink/?linkid=246705">Chart Types</A>.</P>



### Creating a Chart Control

You use Visual Studio tools for Microsoft Dynamics AX and the Microsoft Dynamics AX developer workspace to create and deploy a Chart Control. For information about how to create a Chart Control, see [Walkthrough: Creating a Chart Control with Data from an Analysis Services Cube](walkthrough-creating-a-chart-control-with-data-from-an-analysis-services-cube.md).

### In This Section

[How to: Create a Chart with Data from a Report Data Provider Class](how-to-create-a-chart-with-data-from-a-report-data-provider-class.md)

[How to: Create a Chart with Data from an Analysis Services Cube](how-to-create-a-chart-with-data-from-an-analysis-services-cube.md)

[How to: Format Chart Colors](how-to-format-chart-colors.md)

[Troubleshooting Charts](troubleshooting-charts.md)

[Walkthrough: Creating a Chart Control with Data from a Report Data Provider Class](walkthrough-creating-a-chart-control-with-data-from-a-report-data-provider-class.md)

[Walkthrough: Creating a Chart Control with Data from an Analysis Services Cube](walkthrough-creating-a-chart-control-with-data-from-an-analysis-services-cube.md)

## See also

[User Controls Overview](user-controls-overview.md)

[Walkthrough: Quickly Creating and Deploying a User Control](walkthrough-quickly-creating-and-deploying-a-user-control.md)

[Working with Analysis Services Projects](https://msdn.microsoft.com/en-us/library/cc640918\(v=ax.60\))

