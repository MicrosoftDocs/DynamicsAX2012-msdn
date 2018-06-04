---
title: AxChartBehavior
TOCTitle: AxChartBehavior
ms:assetid: 293bbf22-aa5e-4863-b06e-a0a80f0719de
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh965684(v=AX.60)
ms:contentKeyID: 46331998
ms.date: 04/30/2013
mtps_version: v=AX.60
---

# AxChartBehavior 


_**Applies To:** Microsoft Dynamics AX 2012 R2_

An AxChartBehavior component provides the behavior for a Chart Control. For example, you can use the AxChartBehavior properties to assign color to the chart and update behavior tasks like grouping columns or provide a tool tip.

## Properties

The AxChartBehavior component has the following properties:

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
<td><p>A string value that is the control ID of the behavior of the Chart Control. The naming convention is the &lt;ChartControlName&gt;Behavior. For example, <strong>EPChartControl1Behavior</strong>.</p></td>
</tr>
<tr class="odd">
<td><p>ChartID</p></td>
<td><p>The control ID of the Chart Control. A string value that is the programmatic name of the chart. For example, <strong>EPChartControl1Chart</strong>.</p></td>
</tr>
<tr class="even">
<td><p>EnableViewState</p></td>
<td><p>Boolean value that indicates whether the control automatically saves its state for use in round-trips. This property is inherited from the base control. It is not used in Enterprise Portal scenarios.</p></td>
</tr>
<tr class="odd">
<td><p>Palette</p></td>
<td><p>A collection of custom color palettes available to the AxChartBehavior. A palette is used to assign colors to the data elements in the chart. You must set the <strong>UseAXColors</strong> property to <strong>False</strong> for the <strong>Palette</strong> property changes to take effect.</p></td>
</tr>
<tr class="even">
<td><p>SeriesBehaviors</p></td>
<td><p>The <strong>SeriesBehaviors</strong> property allows you to specify a different column to display for the value. For example, the <strong>AxisLabel</strong> is defined based on the Series <strong>XValueMember</strong> property. You can provide the name of a specific column name in the <strong>AxisLabelColumnName</strong> property of the SeriesBehavior object.</p>
<p>You can click the ellipsis <strong>(…)</strong> button to open the SeriesBehaviors Collection Editor. You can update behaviors in the SeriesBehaviors Collection Editor but you cannot add new SeriesBehavior objects. To add a SeriesBehavior object, add a &lt;dynamics:DynamicsSeriesBehavior&gt; tag in the &lt;SeriesBehaviors&gt; tag in the source markup.</p>
<p>The following is a list of the values that you can set to a specific column name.</p>
<ul>
<li><p>AxisLabelColumnName</p></li>
<li><p>DrillThroughColumnName</p></li>
<li><p>GroupByColumnName</p></li>
<li><p>LabelColumnName</p></li>
<li><p>LegendColumnName</p></li>
<li><p>ToolTipColumnName</p></li>
<li><p>XValueColumnName</p></li>
<li><p>YValueColumnName</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>UseAXColors</p></td>
<td><p>Indicates whether the chart behavior should apply its color palette. By default, the <strong>UseAXColors</strong> property is set to True. Set the <strong>UseAXColors</strong> property to False to define a custom palette. For more information, see <a href="how-to-format-chart-colors.md">How to: Format Chart Colors</a>.</p></td>
</tr>
<tr class="even">
<td><p>Visible</p></td>
<td><p>This property is inherited from the base control. Visibility is not relevant because AxChartBehavior is not a visible control. It is not used in Enterprise Portal scenarios.</p></td>
</tr>
</tbody>
</table>


## Events

A Chart Control can raise life-cycle events at each processing step, such as Init, Load, and PreRender. You can take advantage of these life-cycle events in your application. For example, in a Load event, you can set default values for controls.

The events that occur for Chart Controls are based on the ASP.NET Server Controls. The following section describes the event information that is specific to the Chart Control. For information about ASP.NET Server Control events, see [ASP.NET Web Server Control Event Model](http://go.microsoft.com/fwlink/?linkid=248543). The AxChartBehavior component has the events listed in the following table:

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
<td><p>Disposed</p></td>
<td><p>Occurs after the chart control is disposed.</p></td>
</tr>
<tr class="odd">
<td><p>Init</p></td>
<td><p>Occurs when the page is initialized, which is the first step in its life-cycle. Use this event to read or initialize control properties.</p></td>
</tr>
<tr class="even">
<td><p>Load</p></td>
<td><p>Occurs when the page is loaded into the System.Web.UI.Page object. For example, you can set default values for controls in a Load event.</p></td>
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

