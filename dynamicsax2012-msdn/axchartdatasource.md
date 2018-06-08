---
title: AxChartDataSource
TOCTitle: AxChartDataSource
ms:assetid: 7d849b9a-b8c1-4277-810b-350aef86fae0
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh965686(v=AX.60)
ms:contentKeyID: 46331997
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# AxChartDataSource 


_**Applies To:** Microsoft Dynamics AX 2012 R2_

An AxChartDataSource component provides access to a data set in the AOT for a chart. The Chart Control will use the AxChartDataSource to retrieve data in the data set.

## Properties

The AxChartDataSource component has the following properties:

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Property</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Expressions</p></td>
<td><p>The expressions that are bound to properties of the control. This property is inherited from the base control. It is not used in Enterprise Portal scenarios.</p></td>
</tr>
<tr class="even">
<td><p>ID</p></td>
<td><p>A string value that is the programmatic name of the control. The ID naming convention is <strong>&lt;ChartName&gt;DataSource</strong>. For example, <strong>EPChartControl1DataSource</strong>.</p></td>
</tr>
<tr class="odd">
<td><p>CommandText</p></td>
<td><p>The query text for the chart data source that determines the data that gets returned. The <strong>DataType</strong> property determines which picker will launch when you click the <strong>CommandText</strong> ellipsis <strong>(…)</strong> button.</p>
<ol>
<li><p>When the <strong>DataType</strong> property is set to <strong>MDXQuery</strong>, the MDX Query editor will open and you will enter an MDX query to access Analysis Services cube data.</p></li>
<li><p>When the <strong>DataType</strong> property is set to <strong>ReportDataProvider</strong>, the <strong>Select a Microsoft Dynamics AX Report Data Provider</strong> dialog will open and you will select an RDP class with logic to access data.</p></li>
</ol></td>
</tr>
<tr class="even">
<td><p>DataType</p></td>
<td><p>The type of the data queried by the chart data source. The following data types are supported by the AxChartDataSource component:</p>
<ul>
<li><p><strong>MDXQuery</strong> - An analysis cube consists of a set of measures and dimension attributes that provides the data to display in a chart. Using an analysis cube as a data source allows you to provide a snapshot of data from when the cube was processed. You must provide an MDX query to access data from a deployed and processed cube.</p>
<p>For more information, see <a href="how-to-create-a-chart-with-data-from-an-analysis-services-cube.md">How to: Create a Chart with Data from an Analysis Services Cube</a>.</p></li>
<li><p><strong>ReportDataProvider</strong> (RDP) - An RDP class contains X++ business logic to process data to display in a chart. Using an RDP class as a data source lets you process the data at the time the chart is displayed, so that the data is real time. You must provide an RDP class, data contract class, and a temp table to access data from an RDP class data source.</p>
<p>For more information, see <a href="how-to-create-a-chart-with-data-from-a-report-data-provider-class.md">How to: Create a Chart with Data from a Report Data Provider Class</a>.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>EnableViewState</p></td>
<td><p>Boolean value that indicates whether the control automatically saves its state for use in round-trips. This property is inherited from the base control. It is not used in Enterprise Portal scenarios.</p></td>
</tr>
<tr class="even">
<td><p>Parameters</p></td>
<td><p>The parameters collection for the chart data source. Add the parameters that are required for the chart to render. You can set a default value for each parameter. You must evaluate the data to know what parameters are required.</p></td>
</tr>
</tbody>
</table>


## Events

A Chart Control can raise life-cycle events at each processing step, such as Init, Load, and PreRender. You can take advantage of these life-cycle events in your application. For example, in a Load event, you can set default values for controls.

The events that occur for Chart Controls are based on the ASP.NET Server Controls. The following section describes the event information that is specific to the Chart Control. For information about ASP.NET Server Control events, see [ASP.NET Web Server Control Event Model](http://go.microsoft.com/fwlink/?linkid=248543). The AxChartDataSource component has the events listed in the following table:

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Event</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>DataBinding</p></td>
<td><p>Occurs before the data binding expressions are evaluated.</p></td>
</tr>
<tr class="even">
<td><p>DataSourceChanged</p></td>
<td><p>Occurs when the data source is changed.</p></td>
</tr>
<tr class="odd">
<td><p>Disposed</p></td>
<td><p>Occurs after the chart control is disposed.</p></td>
</tr>
<tr class="even">
<td><p>Init</p></td>
<td><p>Occurs when the page is initialized, which is the first step in its life-cycle. Use this event to read or initialize control properties.</p></td>
</tr>
<tr class="odd">
<td><p>Load</p></td>
<td><p>Occurs when the page is loaded into the System.Web.UI.Page object. For example, you can set default values for controls in a Load event.</p></td>
</tr>
<tr class="even">
<td><p>PostProcessData</p></td>
<td><p>Occurs after the data is processed for the chart control.</p></td>
</tr>
<tr class="odd">
<td><p>PreRender</p></td>
<td><p>Occurs before the chart control is rendered.</p></td>
</tr>
<tr class="even">
<td><p>Unload</p></td>
<td><p>Occurs when the page is unloaded from memory.</p></td>
</tr>
</tbody>
</table>


## See also

[Chart Controls Overview](chart-controls-overview.md)

