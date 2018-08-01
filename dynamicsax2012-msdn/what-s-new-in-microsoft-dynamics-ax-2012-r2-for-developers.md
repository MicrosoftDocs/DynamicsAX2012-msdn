---
title: What's New in Microsoft Dynamics AX 2012 R2 for Developers
TOCTitle: What's New in Microsoft Dynamics AX 2012 R2 for Developers
ms:assetid: 0f17938a-22da-4d5c-8dd7-a397d5da78a6
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ677282(v=AX.60)
ms:contentKeyID: 49384053
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# What's New in Microsoft Dynamics AX 2012 R2 for Developers [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

This topic describes the new and enhanced features that are available in Microsoft Dynamics AX 2012 R2. Updated and additional developer documentation for Microsoft Dynamics AX can be found at the [Microsoft Dynamics AX Developer Center](http://go.microsoft.com/fwlink/?linkid=110356) on the Microsoft Developer Network (MSDN).

The following table describes what has changed in this release:

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Feature area</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Partition</p></td>
<td><p><strong>What can you do?</strong></p>
<p>The business data in each partition is isolated from the data in all other partitions in the same installation of Microsoft Dynamics AX. Business data that is shared among companies is shared only among companies that are in the same partition.</p>
<p>A holding corporation that has subsidiary companies can reduce deployment and maintenance costs by hosting all the subsidiaries in one installation of Microsoft Dynamics AX. The system administrator for the holding corporation can put each subsidiary in its own partition. In this configuration, the personnel of a given subsidiary company cannot access the data of any other subsidiary.</p>
<p>Each Microsoft Dynamics AX client session starts in a partition. The session cannot later be switched to another partition. Instead the user must start a new session and direct it to start in a different partition, if the user is authorized for another partition. The system prevents even the system administrator from accessing data in any partition other than the current partition of the session.</p>
<p>Nothing additional is required to define or maintain reports in a configuration that has multiple partitions.</p>
<p><strong>Where can I find more information?</strong></p>
<ul>
<li><p><a href="partitions-companies-and-data-isolation-in-microsoft-dynamics-ax.md">Partitions, Companies, and Data Isolation in Microsoft Dynamics AX</a> - Describes the following aspects of partitions:</p>
<ul>
<li><p>The relationship between partitions and companies</p></li>
<li><p>The effects of partitions on data access</p></li>
<li><p>The sequence of tasks to create and use a new partition</p></li>
</ul></li>
<li><p><a href="how-to-include-a-filter-for-partition-in-direct-transact-sql.md">How to: Include a Filter for Partition in Direct Transact-SQL</a> - Describes how the few users who might have authority to access data directly from Microsoft SQL Server can access the data in a manner that preserves the intention of partitions.</p></li>
<li><p><a href="https://msdn.microsoft.com/en-us/library/jj133001(v=ax.60)">getCurrentPartition Function</a> - Provides reference documentation for the X++ language function that returns the short name of the current partition.</p></li>
<li><p><a href="https://msdn.microsoft.com/en-us/library/aa893873(v=ax.60)">runAs Function</a> - Describes the new partition parameter.</p></li>
<li><p><a href="https://msdn.microsoft.com/en-us/library/jj728665(v=ax.60)">Data partitioning architecture</a> - Provides a graphic to describe the overall architecture of partitions.</p></li>
<li><p><a href="https://msdn.microsoft.com/en-us/library/jj728668(v=ax.60)">Plan for data partitioning</a> - Describes what to consider when you plan for partitions. These considerations also apply when you upgrade to Microsoft Dynamics AX 2012 R2 from an earlier version.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Client</p></td>
<td><p><strong>What can you do?</strong></p>
<p>When you install the Microsoft Dynamics AX client, AX32.exe registers as a COM server. You can use the Dynamics AX COM object to programmatically open a specified form. In Microsoft Dynamics AX 2012 R2, you can also specify the partition to use with the form.</p>
<p>You can use the API in Office Add-ins for Microsoft Dynamics AX to programmatically modify a Microsoft Excel spreadsheet or Microsoft Word document that includes data that you exported from a form. You can also use the API to lock the data that appears in an Excel spreadsheet.</p>
<p><strong>Why is this important?</strong></p>
<p>You use a partition with the Dynamics AX COM object to specify the business entity that includes the data that you want to appear in the form. The partition prevents the form from displaying data from other business entities.</p>
<p>The Office Add-ins API gives you additional flexibility to programmatically customize a spreadsheet or document file that includes Microsoft Dynamics AX data. You can use the API with a spreadsheet or document that you created by exporting data from a form. For example, you can lock a spreadsheet to prevent people from changing the data fields and records that appear in the spreadsheet.</p>
<p><strong>How was this performed in previous versions?</strong></p>
<p>These features were not available.</p>
<p><strong>Where can I find more information?</strong></p>
<ul>
<li><p><a href="how-to-specify-the-partition-for-the-form.md">How to: Specify the Partition for the Form</a> – Describes how to specify a partition when you use the Dynamics AX COM object to open a form.</p></li>
<li><p><a href="using-the-office-add-ins-api.md">Using the Office Add-ins API</a> – Describes the Office Add-ins XML metadata and the API. You can use the API to add, remove, and modify Office Add-ins metadata for a specified spreadsheet or document file.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Enterprise Portal</p></td>
<td><p><strong>What can you do?</strong></p>
<p>A new User Control option was added called Chart Control. A Chart Control enables you to display chart data in Enterprise Portal. A Chart Control can display data from a Report Data Provider (RDP) class or from an analysis cube.</p>
<p><strong>Why is this important?</strong></p>
<p>A Chart Control is optimized for performance because everything needed for the chart to display is contained in the data set. The Chart Control does not need a Reporting Services server to render the chart which improves the performance.</p>
<p>The alternative is to use Reporting Services to render charts on Enterprise Portal pages. The performance issues become problematic when role centers have multiple charts to render.</p>
<p><strong>How was this performed in previous versions?</strong></p>
<p>In Microsoft Dynamics AX 2009 and Microsoft Dynamics AX 2012, you can use Visual Studio tools for Microsoft Dynamics AX to create a chart report that uses Reporting Services.</p>
<p><strong>Where can I find more information?</strong></p>
<ul>
<li><p><a href="chart-controls-overview.md">Chart Controls Overview</a> – Introduces the Chart Control user control. This topic describes the elements that you can use in a Chart Control, how to access data in a Chart Control, and the tools that you use to define a Chart Control.</p></li>
<li><p><a href="axchartdatasource.md">AxChartDataSource</a> – Describes the AxChartDataSource user control component that was developed to bind a Chart Control to a data source. The Chart Control will use the AxChartDataSource to retrieve data in the data set.</p></li>
<li><p><a href="axchartbehavior.md">AxChartBehavior</a> – Describes the AxChartBehavior component that provides the behavior for a Chart Control. For example, you can use the AxChartBehavior properties to assign color to the chart and update behavior tasks like grouping columns or provide a tool tip.</p></li>
<li><p><a href="how-to-create-a-chart-with-data-from-a-report-data-provider-class.md">How to: Create a Chart with Data from a Report Data Provider Class</a> – Provides a summary of how to create a Chart Control with data from an RDP class.</p></li>
<li><p><a href="how-to-create-a-chart-with-data-from-an-analysis-services-cube.md">How to: Create a Chart with Data from an Analysis Services Cube</a> – Provides a summary of how to create a Chart Control with data from an Analysis Services Cube.</p></li>
<li><p><a href="walkthrough-creating-a-chart-control-with-data-from-a-report-data-provider-class.md">Walkthrough: Creating a Chart Control with Data from a Report Data Provider Class</a> – Provides the steps to create a Chart Control with data from an RDP class.</p></li>
<li><p><a href="walkthrough-creating-a-chart-control-with-data-from-an-analysis-services-cube.md">Walkthrough: Creating a Chart Control with Data from an Analysis Services Cube</a> – Provides the steps to create a Chart Control with data from an Analysis Services Cube.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Services and Application Integration Framework (AIF)</p></td>
<td><p><strong>What can you do?</strong></p>
<p>AIF supports a Microsoft Dynamics AX installation that has multiple partitions. The new data partitioning feature affects the way data is accessed by service operations in Microsoft Dynamics AX. Each service request must contain the information to identify a specific partition. If you do not specify a partition in the call context or message header XML, AIF uses the default partition for the calling user.</p>
<p>The administration of AIF is not per-partition. That is, the administration forms provide a view of the status of the service operation infrastructure that includes inbound and outbound integration ports, the message history, and the exception log, for all partitions at the same time.</p>
<p>The call context, the schema for the message header, and the administration form for inbound ports have changed to enable you to restrict service requests to a specific partition.</p>
<p><strong>Where can I find more information?</strong></p>
<ul>
<li><p><a href="https://msdn.microsoft.com/en-us/library/hh582244(v=ax.60)">Using the Call Context</a> – Describes the use of the call context in external service clients. Information about specifying the partition has been added.</p></li>
<li><p><a href="https://msdn.microsoft.com/en-us/library/aa872025(v=ax.60)">Message Header</a> – Describes the schema of the message header. Information about specifying a particular partition has been added.</p></li>
<li><p><a href="https://msdn.microsoft.com/en-us/library/hh202131(v=ax.60)">Configure security for integration ports</a> – Describes how to restrict service requests on an enhanced inbound integration port to a particular partition.</p></li>
<li><p><a href="https://msdn.microsoft.com/en-us/library/jj728665(v=ax.60)">Data partitioning architecture</a> – Contains background and graphical representation of the new partitioning architecture.</p></li>
</ul>

> [!note]  
> <P>In Microsoft Dynamics AX 2012 R2, AIF includes support for optional replacement fields for a surrogate foreign key that has multiple replacement fields. In other words, a replacement field is optional if the referring surrogate foreign key field is specified as non-mandatory on the table. In previous versions of Microsoft Dynamics AX, AIF considered all surrogate foreign key replacement fields as mandatory.  For outbound transfers, this meant that previous versions of Dynamics AX serialized each field when sending Axd documents. Therefore, in external clients written to use outbound document services in previous versions of Microsoft Dynamics AX, fields that were previously mandatory are now optional, and may be missing from the XML message.</P>

</td>
</tr>
<tr class="odd">
<td><p>Standard Document Services</p></td>
<td><p><strong>What can you do?</strong></p>
<p>The following services are new in Microsoft Dynamics AX 2012 R2:</p>
<ul>
<li><p>Advanced ledger entry</p></li>
<li><p>Bank statement</p></li>
<li><p>Budget plan</p></li>
<li><p>Customer collection letters for Norway</p></li>
<li><p>Payroll earnings import</p></li>
<li><p>Worker import</p></li>
<li><p>Warehouse space utilization forecast</p></li>
<li><p>Warehouse workload capacity forecast</p></li>
</ul>
<p><strong>Why is this important?</strong></p>
<p>Now you can use services to import different types of transactions, to import bank statements, to maintain budget plans, to import earnings statements from external systems, to forecast warehouse workload capacity and space utilization, and to read, create, and update worker information in the Human resources module by using external systems.</p>
<p><strong>How was this performed in previous versions?</strong></p>
<p>These features were not available.</p>
<p><strong>Where can I find more information?</strong></p>
<p>For more information, see <a href="https://msdn.microsoft.com/en-us/library/aa859008(v=ax.60)">Standard Document Services</a>.</p></td>
</tr>
<tr class="even">
<td><p>Language-Integrated Query (LINQ) to AX, for Interop from .NET</p></td>
<td><p><strong>What can you do?</strong></p>
<p>In .NET Framework languages such as C#, you can use the same <a href="http://msdn.microsoft.com/en-us/library/bb397926.aspx">LINQ</a> syntax and paradigm that you already use with LINQ to SQL.</p>
<p><strong>Why is this important?</strong></p>
<p>LINQ to AX makes it easier to interoperate with Microsoft Dynamics AX data from your C# program.</p>
<p><strong>How was this performed in previous versions?</strong></p>
<p>Without LINQ to AX, the primary way your C# program can access table data is to call the methods on a C# class that is a <a href="proxy-classes-for-net-interop-to-x.md">proxy</a> to a table.</p>
<p><strong>Where can I find more information?</strong></p>
<p>For more information, see <a href="code-example-linq-to-ax-from-csharp.md">Code Example: LINQ to AX from C#</a>.</p></td>
</tr>
<tr class="odd">
<td><p>Licensing Framework for ISVs</p></td>
<td><p><strong>What can you do?</strong></p>
<p>ISVs can now query named-users license information. ISVs can use the information to apply license fees for their intellectual property.</p>
<p><strong>Why is this important?</strong></p>
<p>ISVs can use the same named-user licensing information that Microsoft uses. The concurrent users licensing model of Microsoft Dynamics AX 2009 is no longer available.</p>
<p><strong>How was this performed in previous versions?</strong></p>
<p>In Microsoft Dynamics AX 2009, ISVs applied licenses based on the concurrent users model.</p>
<p>In Microsoft Dynamics AX 2012, Microsoft moved away from the concurrent users model, and switched to the named-users licensing model. In Microsoft Dynamics AX 2012 R2, ISVs can use the same named-user licensing information that Microsoft uses.</p>
<p><strong>Where can I find more information?</strong></p>
<p>For more information, see <a href="licensing-framework-for-isvs-of-microsoft-dynamics-ax.md">Licensing Framework for ISVs of Microsoft Dynamics AX</a>.</p></td>
</tr>
</tbody>
</table>

  
   


> [!NOTE]
> <P>For Microsoft Dynamics AX 2012 R2 the Help topics that document each individual upgrade script are present on the MSDN website, at <A href="data-upgrade-scripts-for-microsoft-dynamics-ax-2012.md">this link</A>.</P>
> <P>In the earlier version, Microsoft Dynamics AX 2012, these topics were provided in the file UpgradeScripts.chm which could be downloaded from a website. But that CHM file is no longer being updated.</P>



## See also

[Getting Started with Microsoft Dynamics AX](getting-started-with-microsoft-dynamics-ax.md)

[What's New in Microsoft Dynamics AX 2012 for Developers](what-s-new-in-microsoft-dynamics-ax-2012-for-developers.md)

[What's new in Microsoft Dynamics AX 2012](https://msdn.microsoft.com/en-us/library/dn527180\(v=ax.60\))

[New, Changed, and Deprecated Features for Microsoft Dynamics AX 2012](http://go.microsoft.com/fwlink/?linkid=212966)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

