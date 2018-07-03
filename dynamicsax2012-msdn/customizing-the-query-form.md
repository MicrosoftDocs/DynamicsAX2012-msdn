---
title: Customizing the Query Form
TOCTitle: Customizing the Query Form
ms:assetid: 281f74fa-fb35-4597-94f1-6d1572b1a9cd
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa601676(v=AX.60)
ms:contentKeyID: 35241713
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Customizing the Query Form 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The Query form is displayed prior to a query being run and enables users to change the elements of a query. Use the Query form to do the following:

  - Modify data sources.

  - Specify ranges.

  - Define a sort order.

  - Save the query.

By default, the Query form is the SysQueryRun form that's specified by a query's Form property. To implement your own Query form, create a form, and then set the Query.Form property to the name of the custom form.

## Display the Query Form from the Application Object Tree

1.  Navigate to the **Queries** node.

2.  Right-click the query, and then select **Open**.

The Query form uses the [SysQueryRun](https://msdn.microsoft.com/en-us/library/gg964759\(v=ax.60\)) application class, which extends the [QueryRun](https://msdn.microsoft.com/en-us/library/gg923354\(v=ax.60\)) kernel class.

## Display the Query Form from Code

Display the Query form from code by using the [QueryRun.prompt](https://msdn.microsoft.com/en-us/library/gg923723\(v=ax.60\)) method. The following example instantiates the SalesQuotationUpdate query, displays the Query form by calling the prompt method, and then iterates through the returned records.

```X++
    static void RunSalesQuotationUpdate(Args _args)
    {
    
    QueryRun    SalesQuotationUpdate;
    SalesQuotationTable SalesQuotationTable;
    
    ;
    
    SalesQuotationUpdate = new QueryRun(QueryStr(SalesQuotationUpdate));
    
        if (SalesQuotationUpdate.prompt())
        {
            while (SalesQuotationUpdate.next())
            {
                if (SalesQuotationUpdate.changed(tablenum(SalesQuotationTable)))
                {
                    SalesQuotationTable = SalesQuotationUpdate.get(
                        tablenum(SalesQuotationTable));
                    info(SalesQuotationTable.QuotationId);
                }
            }
        }
    }
```

## Customize the Query Form

Customize the Query form by calling methods that are available from the [SysQueryRun](https://msdn.microsoft.com/en-us/library/gg964759\(v=ax.60\)) class. The following table describes the options that can be set for the Query form.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Option</p></th>
<th><p>When the value is set to</p></th>
<th><p>Default</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Allows the user to add a child data source.</p></td>
<td><p>SysQueryRun.promptAllowAddDataSource</p>
<p>    (true);</p></td>
<td><p>true</p></td>
</tr>
<tr class="even">
<td><p>Allows the user to add a range.</p></td>
<td><p>SysQueryRun.promptAllowAddRange</p>
<p>    (QueryAllowAdd::AllFields);</p></td>
<td><p>QueryAllowAdd::</p>
<p>AllFields</p></td>
</tr>
<tr class="odd">
<td><p>Allows the user to add a sort order.</p></td>
<td><p>SysQueryRun.promptAllowAddSorting</p>
<p>    (QueryAllowAdd::AllFields);</p></td>
<td><p>QueryAllowAdd::</p>
<p>AllFields</p></td>
</tr>
<tr class="even">
<td><p>Allows the user to save or delete the query.</p></td>
<td><p>SysQueryRun.promptAllowSave(true);</p></td>
<td><p>true</p></td>
</tr>
<tr class="odd">
<td><p>Displays and loads the Query form with the query that was last run, its data sources, ranges, and sort orders.</p></td>
<td><p>SysQueryRun.promptLoadLastUsedQuery</p>
<p>    (true);</p></td>
<td><p>true</p></td>
</tr>
<tr class="even">
<td><p>Allows queries to be saved for each user. Users can also delete their own saved queries.</p></td>
<td><p>SysQueryRun.promptSaveQueryPrUser</p>
<p>    (true);</p></td>
<td><p>true</p></td>
</tr>
<tr class="odd">
<td><p>Allows users to change and save their queries. If false, the user cannot change or save a query.</p></td>
<td><p>Query.userUpdate(true);</p></td>
<td><p>true</p></td>
</tr>
<tr class="even">
<td><p>Displays the Query form's Select query combo box.</p></td>
<td><p>SysQueryRun.promptShowQuerySelect</p>
<p>    (true);</p></td>
<td><p>true</p></td>
</tr>
<tr class="odd">
<td><p>Displays the <strong>Reset</strong> button, which sets all the data sources, ranges, and sort orders to their original states.</p></td>
<td><p>SysQueryRun.ShowReset(true);</p></td>
<td><p>true</p></td>
</tr>
<tr class="even">
<td><p>Displays the <strong>Sorting</strong> tab.</p></td>
<td><p>SysQueryRun.promptShowSorting</p>
<p>    (true);</p></td>
<td><p>true</p></td>
</tr>
</tbody>
</table>


## See also

[Query Elements in the AOT](query-elements-in-the-aot.md)

[Accessing Data](accessing-data.md)

[How to: Create Queries by Using X++](how-to-create-queries-by-using-x.md)

[How to: Create Queries by using the AOT](how-to-create-queries-by-using-the-aot.md)

[Query Object Model](query-object-model.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

