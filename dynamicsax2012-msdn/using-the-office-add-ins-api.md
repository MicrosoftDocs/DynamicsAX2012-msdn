---
title: Using the Office Add-ins API
TOCTitle: Using the Office Add-ins API
ms:assetid: 33be53b8-aac7-4784-ba4a-fe8bb70ee148
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ677288(v=AX.60)
ms:contentKeyID: 49384059
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Using the Office Add-ins API [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

The Microsoft Office Add-ins for Microsoft Dynamics AX enables you to integrate data from the Microsoft Dynamics AX client together with Microsoft Excel or Microsoft Word. When you install Office Add-ins, a tab labeled **Dynamics AX** is added to the ribbon in Excel and Word. You use the controls on this tab to add, remove, or update Microsoft Dynamics AX data that appears in an Excel spreadsheet or Word document.

The Microsoft Dynamics AX 2012 R2 Office Add-ins include an application programming interface (API) that you can use to change filter and other criteria in an Excel spreadsheet or Word document. You use the API when you want to programmatically customize a spreadsheet or document.

For example, you use the **Export to Excel** button on the Action Pane of a form to create a spreadsheet that is used by several people. You now want to create a version of that spreadsheet file for one person who works with a smaller set of records. To show a subset of records in the spreadsheet, you create an application that uses the API to filter records from the spreadsheet. You then save that file as a separate version of the original spreadsheet.

## Working with Spreadsheet and Document Files

Excel 2007, Word 2007, and later versions use the Office Open XML format for spreadsheet and document files. To programmatically modify these files, you use the Open method of the SpreadsheetDocument class or the WordprocessingDocument class of the DocumentFormat.OpenXml.Packaging namespace. The namespace is found in the DocumentFormat.OpenXml assembly.

## XML Metadata for Office Add-ins

The Office Add-ins embeds a custom XML part in every spreadsheet or document. The XML part includes metadata that describes the connections, tables, fields, filters, and other information that helps show Microsoft Dynamics AX data in the spreadsheet or document.

The following illustration shows how the metadata in the custom XML part is organized for an Excel spreadsheet. In the diagram, the Office Add-ins XML is the embedded XML part. The diagram also shows that the part includes nodes for the workbook options and data sources.

![Office Add-ins custom XML metadata components](images/JJ677288.Client_OfficeAddin(en-us,AX.60).png "Office Add-ins custom XML metadata components")

To programmatically add, remove, or modify the XML that Office Add-ins embeds in a file, you use the Serializer class. The class is in the Microsoft.Dynamics.AX.Framework.OfficeAddin.XmlParts namespace of the Microsoft.Dynamics.AX.Framework.OfficeAddin.XmlParts.dll .NET assembly. When you install the Office Add-ins, the assembly is put in the C:\\Program Files (x86)\\Microsoft Dynamics AX\\60\\OfficeAddins folder. The Serializer class includes the following methods:

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Method</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>GetWorkbookXmlPart</p></td>
<td><p>Get the custom XML part from a spreadsheet. The method returns a WorkbookXmlPart object.</p></td>
</tr>
<tr class="even">
<td><p>SetWorkbookXmlPart</p></td>
<td><p>Saves changes to the custom XML part of a spreadsheet.</p></td>
</tr>
<tr class="odd">
<td><p>GetDocumentXmlPart</p></td>
<td><p>Get the custom XML part from a Word document. The method returns a DocumentXmlPart object.</p></td>
</tr>
<tr class="even">
<td><p>SetDocumentXmlPart</p></td>
<td><p>Saves changes to the custom XML part of a document.</p></td>
</tr>
</tbody>
</table>


In addition, the DocumentFormat.OpenXml and Microsoft.Dynamics.AX.Framework.OfficeAddin.XmlParts assemblies are added to the list of **References** in the AOT. As a result, you can use the classes in these assemblies from your X++ code to programmatically add, remove, or modify the XML in a spreadsheet or document. For more information about how to use a .NET assembly from X++, see [How to: Compile and Run X++ that Calls CLR Managed Assemblies](how-to-compile-and-run-x-that-calls-clr-managed-assemblies.md).

### ![JJ677288.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "JJ677288.collapse_all(en-us,AX.60).gif")Workbook Options

The workbook options node is a collection of properties you use to control the behavior of an Excel spreadsheet. You can use the Office Add-ins API to programmatically access the following properties of the workbook options node:

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Property</p></th>
<th><p>Type</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>IsDesignLocked</strong></p></td>
<td><p><strong>bool</strong></p></td>
<td><p>Specifies whether the spreadsheet or document is locked. To enable the lock, set the property to true. For information about how to programmatically access the workbook options node, see <a href="how-to-use-office-add-ins-to-lock-an-excel-spreadsheet.md">How to: Use Office Add-ins to Lock an Excel Spreadsheet</a>.</p>
<p>If the file is locked, you cannot use the controls in the <strong>Dynamics AX</strong> tab to modify the data source or fields that appear in the spreadsheet.</p></td>
</tr>
<tr class="even">
<td><p><strong>RefreshAllDataOnOpen</strong></p></td>
<td><p><strong>bool</strong></p></td>
<td><p>Specifies whether the data in the spreadsheet is refreshed when the file is opened. To refresh the data, set the property to true.</p>
<p>You can also use the <strong>Options for working with Microsoft Dynamics AX</strong> window from the <strong>Dynamic AX</strong> tab to set this property value.</p></td>
</tr>
</tbody>
</table>


### ![JJ677288.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "JJ677288.collapse_all(en-us,AX.60).gif")Data Sources

The data sources node is the XML metadata that describes one or more data connections that a spreadsheet or document uses to obtain data from Microsoft Dynamics AX. Typically, the data sources are added when you export data from a form or you use the Office Add-ins to retrieve data.

The following illustration shows the structure of the XML metadata for the data sources node. Notice how a data source can include filters and matrix fields.

![The structure of the XML metadata for data sources](images/JJ677288.Client_OfficeAddinDataSources(en-us,AX.60).png "The structure of the XML metadata for data sources")

### ![JJ677288.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "JJ677288.collapse_all(en-us,AX.60).gif")Using the Office Add-ins API with XML Metadata Nodes

To programmatically add, remove, and modify Office Add-ins XML nodes, you use several classes in the Microsoft.Dynamics.AX.Framework.OfficeAddin.XmlParts namespace. The namespace is found in the Microsoft.Dynamics.AX.Framework.OfficeAddin.XmlParts.dll .NET assembly. The classes include properties and methods that you use to modify the metadata values in the Office Add-ins XML part. To see how you can use API classes to add a filter to a spreadsheet, see [How to: Add an Office Add-in Filter to a Spreadsheet](how-to-add-an-office-add-in-filter-to-a-spreadsheet.md).

The following table shows the class you use with each XML node you find in the custom XML part that Office Add-ins embed in a spreadsheet or document file.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>XML node</p></th>
<th><p>Class</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Office Add-ins XML</p></td>
<td><p>You use the WorkbookXmlPart class to represent the Office Add-ins XML part from a spreadsheet. You use the DocumentXmlPart class to represent the Office Add-ins XML part from a document.</p></td>
</tr>
<tr class="even">
<td><p>Workbook options</p></td>
<td><p>You use the WorkbookOptionsXmlPart class to access the workbook option properties for a spreadsheet. You use this class to change the IsDesignLocked and RefreshAllDataOnOpen properties for a spreadsheet.</p></td>
</tr>
<tr class="odd">
<td><p>Data sources</p></td>
<td><p>You use the DataSourcesXmlPartDictionary class to get the collection of data sources in the Office Add-ins XML.</p></td>
</tr>
<tr class="even">
<td><p>Data source</p></td>
<td><p>You use the DataSourceXmlPart class to get a single data source node from the data source collection of a spreadsheet or document.</p></td>
</tr>
<tr class="odd">
<td><p>Filter collection</p></td>
<td><p>You use the FilterXmlPartCollection class to get the filters for a specified data source. You can use the Add method of this class to create a new filter node. You can also use the Remove method to delete an existing filter node.</p></td>
</tr>
<tr class="even">
<td><p>Filter</p></td>
<td><p>You use the FilterXmlPart class to view and modify the properties of an individual filter node.</p></td>
</tr>
<tr class="odd">
<td><p>Matrix field collection</p></td>
<td><p>You use the MatrixFieldXmlPartCollection class to get the matrix fields for a specified data source.</p></td>
</tr>
<tr class="even">
<td><p>Matrix field</p></td>
<td><p>You use the MatrixFieldXmlPart class to view the properties of an individual matrix field node and modify the expression property of that matrix field.</p></td>
</tr>
</tbody>
</table>


## Filtering Records in a Data Source

The earlier diagram shows that a data source can include filters. The diagram also shows that the Filters node can include one or more individual filter nodes. A filter node includes the criteria that specify the data records that appear in a spreadsheet or document. To customize the spreadsheet or document, you can use the Office Add-ins API to add, remove, or modify filter nodes.

### ![JJ677288.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "JJ677288.collapse_all(en-us,AX.60).gif")Filter Nodes

A filter is an XML metadata node that specifies a field, a table, and criteria. The data source uses the properties of the filter to determine what records appear in a spreadsheet or document. A filter node is like a **Range** in an AX query. For information about how to modify a filter, see [How to: Add an Office Add-in Filter to a Spreadsheet](how-to-add-an-office-add-in-filter-to-a-spreadsheet.md). To learn about AX queries and ranges, see [Query Elements in the AOT](query-elements-in-the-aot.md).

To populate the properties, you use the same values that you would use with **Add Condition** in the **Filter results** dialog window. The following table shows the properties for a filter node.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Property</p></th>
<th><p>Type</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Criteria</strong></p></td>
<td><p><strong>string</strong></p></td>
<td><p>Specifies the filter operation and value. For example, you could use &gt; 0 to specify the criteria for a credit limit field.</p></td>
</tr>
<tr class="even">
<td><p><strong>FieldFullyQualifiedName</strong></p></td>
<td><p><strong>string</strong></p></td>
<td><p>Specifies the fully qualified name of the field for the filter. The format for the name is &lt;data source&gt;.&lt;table name&gt;.&lt;field name&gt;.</p></td>
</tr>
<tr class="odd">
<td><p><strong>TableFullyQualifiedName</strong></p></td>
<td><p><strong>string</strong></p></td>
<td><p>Specifies the fully qualified name of the table where the field appears. The format for the name is &lt;data source&gt;.&lt;table name&gt;.</p></td>
</tr>
</tbody>
</table>


## Modifying a Matrix Field in a Data Source

The earlier diagram shows a data source can include a collection of matrix field nodes. A matrix field is an XML metadata node you use to show a total for a group of related records on a spreadsheet. To add a matrix field, you use the **Create New Matrix Field** dialog window in the **Dynamics AX** tab. A matrix field includes the following components:

  - A field that contains the values that you use to put related records into groups. For example, you could group customer records by **Credit rating**.

  - A measure field that contains the numeric values that you want to total for each group. For example, you could total the **Credit limit** field to show the total credit available to each **Credit rating** group.

  - An expression that specifies whether to include a record in one of the groups that appears in the spreadsheet. The total for the measure field will not include the value of any records that are excluded by the expression. For example, you could use the expression to show credit rating groups for customers from a specified country or region.

The following table shows the properties for a matrix field node. You use the read-only properties to identify the matrix field you want to work with. You can then use the Office Add-ins API to modify the expression property for that matrix field. If you change the value of a read-only property, the value that you set will be ignored when you save the XML to the spreadsheet.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Property</p></th>
<th><p>Type</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>DataSourceName</strong></p></td>
<td><p><strong>string</strong></p></td>
<td><p>The name of the data source. This property is read-only.</p></td>
</tr>
<tr class="even">
<td><p><strong>DataSourceQualifiedName</strong></p></td>
<td><p><strong>string</strong></p></td>
<td><p>The full name for the data source. This property is read-only.</p></td>
</tr>
<tr class="odd">
<td><p><strong>DisplayName</strong></p></td>
<td><p><strong>string</strong></p></td>
<td><p>The name of the filter. This property is read-only.</p></td>
</tr>
<tr class="even">
<td><p><strong>ExpressionModel</strong></p></td>
<td><p><strong>string</strong></p></td>
<td><p>The serialized form of the expression associated with the field. To modify a matrix field, you change the values in the expression</p>
<p>To de-serialize and modify the expression, you can use the ExpressionInfo class and related classes in the Microsoft.Dynamics.AX.Framework.OfficeAddin assembly.</p></td>
</tr>
<tr class="odd">
<td><p><strong>FieldName</strong></p></td>
<td><p><strong>string</strong></p></td>
<td><p>The name of the field. This property is read-only.</p></td>
</tr>
<tr class="even">
<td><p><strong>FullyQualifiedFieldName</strong></p></td>
<td><p><strong>string</strong></p></td>
<td><p>Specifies the fully qualified name of the field for the filter. This property is read-only.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Id</strong></p></td>
<td><p><strong>Guid</strong></p></td>
<td><p>Specifies the ID of the MatrixField object associated with this filter. This property is read-only.</p></td>
</tr>
<tr class="even">
<td><p><strong>MeasureFieldFullyQualifiedName</strong></p></td>
<td><p><strong>string</strong></p></td>
<td><p>Specifies the full name of the field that defines the measure for the matrix field. This property is read-only.</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

