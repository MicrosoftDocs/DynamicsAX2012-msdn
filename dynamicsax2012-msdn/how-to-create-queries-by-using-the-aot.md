---
title: 'How to: Create Queries by using the AOT'
TOCTitle: 'How to: Create Queries by using the AOT'
ms:assetid: 6acebb36-fcc6-4c6e-af28-3f275fb90113
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Bb314753(v=AX.60)
ms:contentKeyID: 35244789
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Create Queries by using the AOT 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The Application Object Tree (AOT) provides a graphical interface for creating queries. These are known as static queries. When a query is created using the AOT, the SysQuery and SysQueryRun classes are used behind the scenes.

## Create a Query for a Single Data Source

1.  In the AOT, right-click **Queries**, and then click **New Query**.

2.  Right-click **Data Dictionary**, and then click **Open New Window**.

3.  Drag a table, map, or view from the second window to the **Data Sources** node under the new query in the first window. All the fields in the data source are included in the query by default.
    
    For more information, see [How to: Create Tables](how-to-create-tables.md), [How to: Create Maps](how-to-create-maps.md), and [How to: Create a View Based on a Query](how-to-create-a-view-based-on-a-query.md).

4.  To remove fields and add fields, do the following:
    
    1.  Click **Data Sources**, click the data source that you added in step 3, right-click **Fields**, and then click **Properties**.
    
    2.  Set the **Dynamic** property to **No**.
    

    > [!NOTE]
    > <P>By default, the <STRONG>Dynamic</STRONG> property is set to <STRONG>Yes</STRONG> and returns all fields from the table, map, or view. This makes maintenance easier because you don't need to change the query if a field is changed in the underlying data source. However, restricting the fields returned by the query is better for performance because unused data is not returned to the client each time the query is run.</P>

    
    1.  Expand the **Fields** node, locate the field that you want to delete, right-click the field, and then click **Delete**.
    
    2.  Right-click the **Fields** node, and then click **New** \> **Field**.
    
    3.  Right-click the new field, click **Properties**, and select the field that you want to add in the **Field** property list.

5.  To override a [QueryRun Class](https://msdn.microsoft.com/en-us/library/gg923354\(v=ax.60\)) method, right-click the **Methods** node, click **Override Method**, and then click a method.

6.  Right-click the new query, click **Properties**, and then modify the properties as needed.

7.  Save the new query.

## Define a Group By

This section describes how to add a field to the **Group By** specification of your query. You can add several fields to the **Group By** by repeating the following steps:

1.  Navigate to **AOT** \> **Queries** \> YourQuery \> **Data Sources** \> YourDataSource.

2.  Expand the **Fields** node.

3.  Drag any field onto the **Group By** node.

## Define an Order By

This section describes how to add a field to the **Order By** specification of your query. You can add several fields to the **Order By** by repeating the following steps:

1.  Navigate to **AOT** \> **Queries** \> YourQuery \> **Data Sources** \> YourDataSource.

2.  Expand the **Fields** node.

3.  Drag any field onto the **Order By** node.

4.  In the properties window for the **Direction** property, you have the option of changing the default from **Ascending** to **Descending**.

## Define a Range

1.  In the AOT, click **Queries**, and locate the query that you want to define a range for.

2.  Expand the query, click **Data Sources**, and then expand a data source.

3.  Right-click **Ranges**, and then click **New Range**.

4.  Right-click the new range, click **Properties**, and then select a field in the **Field** property list.

5.  Type an expression in the **Value** property to specify which records are retrieved.


> [!NOTE]
> <P>Complex range expressions can impact performance. The more filter expressions Microsoft Dynamics AX must apply to the data the longer the query will run.</P>



Range expressions on different fields are ANDed. Range expressions on the same field are ORed. The following table lists the operators and symbols that can be used in range expressions.

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Symbol</p></th>
<th><p>Meaning</p></th>
<th><p>Example</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>=</p></td>
<td><p>Equal to</p></td>
<td><p>=Smith</p></td>
<td><p>Finds Smith.</p></td>
</tr>
<tr class="even">
<td><p>!</p></td>
<td><p>Not equal to</p></td>
<td><p>!Smith</p></td>
<td><p>Finds all values except Smith.</p></td>
</tr>
<tr class="odd">
<td><p>..</p></td>
<td><p>Between two values</p></td>
<td><p>A..C</p></td>
<td><p>Finds all records from A to C including records with A and C.</p></td>
</tr>
<tr class="even">
<td><p>&gt;</p></td>
<td><p>Greater than</p></td>
<td><p>&gt;1000</p></td>
<td><p>Finds all values greater than 1,000.</p></td>
</tr>
<tr class="odd">
<td><p>&lt;</p></td>
<td><p>Less than</p></td>
<td><p>&lt;1000</p></td>
<td><p>Finds all values less than 1,000 including negative values.</p></td>
</tr>
<tr class="even">
<td><p>*</p></td>
<td><p>Match values containing the characters before or after the asterisk.</p></td>
<td><p>S*</p>
<p>or</p>
<p>*east*</p></td>
<td><p>Finds all values that begin with the letter S.</p>
<p>Finds all values that include the word east.</p>
<p>The NOT symbol, !, can be used in front of these wildcard * values. For example, if you set the range’s <strong>Value</strong> property to the eight characters of ! *east*, all values that contain the four characters east are excluded from the query results.</p></td>
</tr>
<tr class="odd">
<td><p>?</p></td>
<td><p>Match a single unknown character</p></td>
<td><p>Sm?th</p></td>
<td><p>Finds all values that include only the letters s, m, t, and h in the order shown and any character in the ? placeholder.</p></td>
</tr>
<tr class="even">
<td><p>,</p></td>
<td><p>Separates expression components</p></td>
<td><p>A..D, !C</p></td>
<td><p>Finds A, B, and D.</p></td>
</tr>
</tbody>
</table>


1.  Set the **Status** property to specify specific behavior for the range.
    
    1.  Open - The user can modify the query range.
    
    2.  Locked - The user can see the range but cannot modify it.
    
    3.  Hidden - The user cannot see the range but can add new ranges to the query.

## See also

[How to: Create Queries by Using X++](how-to-create-queries-by-using-x.md)

[Using Expressions in Query Ranges](using-expressions-in-query-ranges.md)

[Query Properties](https://msdn.microsoft.com/en-us/library/aa842737\(v=ax.60\))

[How to: Add Multiple Data Sources to a Query](how-to-add-multiple-data-sources-to-a-query.md)

[Query Framework in the AOT](query-framework-in-the-aot.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

