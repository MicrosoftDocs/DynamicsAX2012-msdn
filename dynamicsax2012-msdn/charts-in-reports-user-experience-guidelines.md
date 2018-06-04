---
title: Charts in Reports User Experience Guidelines
TOCTitle: Charts in Reports
ms:assetid: 3cbe2c1b-2e52-4a08-bb59-e18e325a8084
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg886589(v=AX.60)
ms:contentKeyID: 35267953
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# Charts in Reports User Experience Guidelines 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Charts are visual tools for data analysis and information management. Charting should be used in reports in such a way that they enable users to get the most out of their data. At a minimum, charts should be readable and understandable, and they should identify tasks that users can act on. They should help users find items of interest and outliers in business data, based on objectives or measures.

Example of a chart in a report

  
![Chart in a report](images/Gg886589.ChartsAndGraphsInReports01(AX.60).png "Chart in a report")Example of a chart in a report

## Design concepts

For charts to be effective in enhancing the content in a report, charts should be designed so that they are:

  - As simple as possible.

  - Easy to skim and read.

  - Consistent across all report types.

  - Aligned with the design guidelines.

  - Easy to localize and customize.
    
      - Optimized for U.S. format (Letter, Tabloid).
    
      - Acceptable for EU format (A4, A3).

## Guidelines

The following sections discuss the guidelines for when and how charts should be used in reports.

### When to use a chart

A report would benefit from having a chart if you can answer "yes" to any of the following questions.

  - Would a chart make it easier to:
    
      - Compare individual items of a series?
    
      - Compare a series of values as a whole?
    
      - Understand the contribution of individual items to a total series of items?
    
      - Understand where individual items fall in terms of certain value ranges?
    
      - Identify outliers in a series in terms of one (or multiple) measures?
    
      - Discover or validate correspondences between several measurements and identify items that do not follow?
    
      - Discover trends and identify patterns?
    
      - Understand dependencies and relations?
    
      - Forecast consequences of potential changes?
    
      - Identify tasks that users can act on?

### Position of charts in a report

We highly recommend placing charts at the top of a report. However, charts can appear throughout a report. The following illustration shows a report with a summary chart at the top of the page and callouts.

![Report with summary chart at the top with callouts](images/Gg886589.ChartsAndGraphsInReports02(AX.60).png "Report with summary chart at the top with callouts")![Report with summary chart at the top with callouts](images/Gg886589.ChartsAndGraphsInReports03(AX.60).png "Report with summary chart at the top with callouts")

Because of their value to summarize data quickly and visually, we recommend that charts are prioritized as the first component of a report, and that they are positioned underneath the report header title.

Charts should appear directly above their supporting data. A chart should include a legend, and it should be followed immediately by the parameters defining the chart. A chart does not need a background color, but if one is needed, a light gray is best. In the guideline examples that follow, a background is added to help provide a visual reference of the available space for the chart.

### Size of charts in a report

We highly recommend that the combined height of the chart and parameters section is no greater than half of the available content area (or 4.5 inches) to provide room for the supporting data.

### Interaction

Charts should not have any complex interactive controls. Charts should be used strictly for data visualization. Changing parameters of a report is handled through the Microsoft SQL Server Reporting Services framework; there should be no controls within the confines of the content area. The only interaction found in any report should be a standard drill down, which appears as a standard blue hyperlink.

### Types of charting used in Microsoft Dynamics AX

We ranked each chart type in one or more usage areas and according to certain capabilities such as *Y* values per point, the number of supported series, and whether the chart type could be combined with another chart to enhance value. Based on this ranking, we make the following recommendations for using charts in Microsoft Dynamics AX 2012.

#### Recommended chart types

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p><strong>Discontinuous data</strong></p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Shows values for different categories</p></td>
</tr>
<tr class="even">
<td><p></p>
<ul>
<li><p>Column</p></li>
<li><p>Grouped column</p></li>
</ul></td>
</tr>
</tbody>
</table>


<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Continuous data</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Measures trends in data over intervals</p></td>
</tr>
<tr class="even">
<td><p>Best for showing chronological data</p>
<ul>
<li><p>Point</p></li>
<li><p>Line</p></li>
<li><p>Tree / Flow / Organizational</p></li>
</ul></td>
</tr>
</tbody>
</table>


#### Acceptable chart types

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Proportion</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Illustrates relative quantity of data</p></td>
</tr>
<tr class="even">
<td><p>Best if used only to compare proportions</p>
<ul>
<li><p>Pie</p></li>
<li><p>Tree map</p></li>
</ul></td>
</tr>
</tbody>
</table>


<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Multi-variable</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Compares many measures for multiple series</p></td>
</tr>
<tr class="even">
<td><p>Best if used only to show commonality or outlying data</p>
<ul>
<li><p>Stacked column</p></li>
<li><p>Radar</p></li>
</ul></td>
</tr>
</tbody>
</table>


#### Chart types not recommend

Additional functionality such as transparency and 3D plot adjustment is required to make some of the following charting types effective in Microsoft SQL Server Reporting Services reports, and are not currently recommended. Other types are not recommended because they are almost never used with Microsoft Dynamics AX data types.

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr class="odd">
<td><ul>
<li><p>3D charts</p></li>
<li><p>Bubble</p></li>
<li><p>Stacked area</p></li>
<li><p>Horizontal bar charts</p></li>
<li><p>Charts with two separate y-axis</p></li>
<li><p>Stock-related chart type</p></li>
</ul></td>
</tr>
</tbody>
</table>


### Chart components

**Chart title**

The chart title should be left-aligned and appear at the top the chart.

**Chart legend**

A legend should be included with the chart. A legend can be either horizontal or vertical.

  - **Horizontal legend** – Should be placed directly below the title and be left-aligned.
    
    ![Chart with horizontal legend](images/Gg886589.ChartsAndGraphsInReports04(AX.60).png "Chart with horizontal legend")

  - **Vertical legend** – Should be placed immediately to the left of the chart and be left-aligned.
    
    ![Chart with vertical legend](images/Gg886589.ChartsAndGraphsInReports05(AX.60).png "Chart with vertical legend")
    
      

**Chart colors**.

To provide a seamless data visualization experience across Microsoft Dynamics AX and Microsoft® Office, charts should use the default color scheme shipped with Microsoft Excel®.

Illustration showing Microsoft Excel color scheme

  
![Microsoft Excel color scheme](images/Gg886589.ChartsAndGraphsInReports06(AX.60).png "Microsoft Excel color scheme")Illustration showing Microsoft Excel color scheme

The following color tables reflect the default color themes. (Shadows are included in case they are needed.)

![Colors in order of priority to ensure legibility](images/Gg886589.ChartsAndGraphsInReports07(AX.60).png "Colors in order of priority to ensure legibility")

Default color values (left) and shadow color values (right)

  
![Color values: Default](images/Gg886589.ChartsAndGraphsInReports08(AX.60).png "Color values: Default")Default color values (left) and shadow color values (right)

Continuous color values

  
![Color values: Continuous](images/Gg886589.ChartsAndGraphsInReports09(AX.60).png "Color values: Continuous")Continuous color values

Gray color values

  
![Color values: Gray](images/Gg886589.ChartsAndGraphsInReports10(AX.60).png "Color values: Gray")Gray color values

## Labels and text

**Labels and tick marks**

Labels should be clearly legible at all times.

**Text**

There should be no additional names embedded in the chart. The report header title should be the only title on the page and should be implicit enough to imply the purpose and function of the chart.

## See also

[General Reporting User Experience Guidelines](general-reporting-user-experience-guidelines.md)

