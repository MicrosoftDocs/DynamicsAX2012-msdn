---
title: Metadata
TOCTitle: Metadata
ms:assetid: aa8ebad5-4c40-4081-9591-8e4d3460cd20
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc616802(v=AX.60)
ms:contentKeyID: 28119472
ms.date: 11/07/2012
mtps_version: v=AX.60
dev_langs:
- csharp
---

# Metadata 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

When adding code to User Controls, it can be useful to retrieve metadata for the resources used in Enterprise Portal. For example, retrieving the list of fields available in a data set view can be helpful when dynamically defining a lookup.

Metadata for Enterprise Portal is retrieved in two ways.

  - Classes in the Microsoft.Dynamics.AX.Framework.Services.Client namespace access metadata for resources like tables, data sets, and enumerations.

  - The Business Connector proxy provides access to metadata for the AOT resources used for Enterprise Portal.

## Microsoft.Dynamics.AX.Framework.Services.Client

The Microsoft.Dynamics.AX.Framework.Services.Client namespace contains several classes that work together to retrieve metadata. Some of the classes contain static methods that perform retrieve operations. Other classes define the metadata objects that can be retrieved.

### Numeric Identifier

The numeric identifier for a specific resource can be retrieved. This value is used in cases such as defining a data set through code. The numeric identifier is also used when retrieving the metadata objects for some resources. The following table lists the class and the static method of that class that is used to retrieve a numeric identifier for the resource type.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Class</p></th>
<th><p>Static Method</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>EnumMetadata</p></td>
<td><p>EnumNum</p></td>
<td><p>Retrieves the numeric identifier for a base enumeration defined in the AOT.</p></td>
</tr>
<tr class="even">
<td><p>ExtendedDataTypeMetadata</p></td>
<td><p>TypeNum</p></td>
<td><p>Retrieves the numeric identifier for an extended data type defined in the AOT.</p></td>
</tr>
<tr class="odd">
<td><p>TableMetadata</p></td>
<td><p>TableNum</p></td>
<td><p>Retrieves the numeric identifier for a table defined in the AOT.</p></td>
</tr>
<tr class="even">
<td><p>TableDataFieldMetadata</p></td>
<td><p>FieldNum</p></td>
<td><p>Retrieves the numeric identifier for a field in a table defined in the AOT.</p></td>
</tr>
</tbody>
</table>


For example, the following code retrieves the numeric identifier of the table CustTable.

``` csharp
int custTableNum;
custTableNum = TableMetadata.TableNum("CustTable");
```

The following example retrieves the numeric identifier for the enumeration AssetType.

``` csharp
int assetTypeEnumNum;
assetTypeEnumNum = EnumMetadata.EnumNum("AssetType");
```

### Metadata Objects

To access the detailed information about a resource, you must retrieve its metadata object. In some cases, the metadata for a resource is contained in several objects that you will retrieve and use.

Most of the metadata objects are retrieved using static methods defined for the MetadataCache class. The following table lists the static methods in this class that retrieve metadata.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Static Method</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>GetDataSetMetadata</p></td>
<td><p>Retrieves the metadata for a data set.</p></td>
</tr>
<tr class="even">
<td><p>GetEnumMetadata</p></td>
<td><p>Retrieves the metadata for an enumeration.</p></td>
</tr>
<tr class="odd">
<td><p>GetExtendedDataTypeMetadata</p></td>
<td><p>Retrieves the metadata for an extended data type.</p></td>
</tr>
<tr class="even">
<td><p>GetTableMetadata</p></td>
<td><p>Retrieves the metadata for a table.</p></td>
</tr>
</tbody>
</table>


The following example retrieves a DataSetMetadata object for the CustomerList data set.

``` csharp
DataSetMetadata custListMetadata;
custListMetadata = MetadataCache.GetDataSetMetadata(this.AxSession, "CustomerList");
```

The following example retrieves a TableMetadata object for the table CustTable. Notice that the numeric identifier for the table is retrieved first, and then used to retrieve the table metadata object. To retrieve additional information about the table, other metadata objects are used. The FieldGroupMetadata object is created for the first field group in the table. The name of the field group is retrieved from this object.

``` csharp
int custTableNum;
TableMetadata custTableMetadata;
FieldGroupMetadata firstFieldGroup;
string fieldGroupName;

// Retrieve the numeric identifier for the table.
custTableNum = TableMetadata.TableNum("CustTable");

// Retrieve the table metadata object for the table.
custTableMetadata = MetadataCache.GetTableMetadata(custTableNum);

// Retrieve the metadata object for the first field group in the 
// table and examine its name.
firstFieldGroup = custTableMetadata.FieldGroups[0];
fieldGroupName = firstFieldGroup.Name;
```

## AOT Resources

Some Enterprise Portal resources that you may want to examine with code are located in the AOT. Classes and methods are included in the Business Connector proxy to enable you to access metadata for these AOT resources. To access the Business Connector proxy, the following using statement must be included.

``` csharp
using Proxy = Microsoft.Dynamics.Framework.BusinessConnector.Proxy;
```

The following example is a helper method that retrieves the definition of the RoomAddEdit web page from the AOT. The helper method examines the nodes in the AOT to find the correct page definition, which is returned.

``` csharp
private Proxy.webPageDefNode PageDefinition
{
    get
    {
        string AOTPageDefinitionsPath = "\\Web\\Web Files\\Page Definitions\\RoomAddEdit";
        Proxy.TreeNode pageDef;
        pageDef = Proxy.TreeNode.findNode(AxSession.AxaptaAdapter, AOTPageDefinitionsPath);
        if (pageDef != null)
        {
            return new Proxy.webPageDefNode(AxSession.AxaptaAdapter, pageDef.AxaptaObjectAdapter);
        }
        else
        {
            return null;
        }
    }
}
```

The following example uses the helper method defined in the previous example to retrieve the Web page title.

``` csharp
string pageTitle;
pageTitle = PageDefinition.pageTitle;
```


> [!NOTE]
> <P>In some cases, you can set the values of the properties of the object returned to override the values stored in the AOT. For example, you could set the pageTitle property to override the title of the page displayed in Enterprise Portal.</P>


