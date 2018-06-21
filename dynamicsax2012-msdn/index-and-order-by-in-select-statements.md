---
title: Index and Order By in Select Statements
TOCTitle: Index and Order By in Select Statements
ms:assetid: a2c2d401-6e27-40e2-b180-0fbce65553ca
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa849686(v=AX.60)
ms:contentKeyID: 35248353
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Index and Order By in Select Statements [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Use the order by keyword in your select statements to order the data that's returned.

Use the index hint keywords to specify that a particular index should be used in the query and to sort the selected records as defined by the index. Indexes optimize the selection of records.

Combine the index hint keyword with an order by expression to select records in a specific order. If you want the sorted output in reverse order, use the reverse keyword.

If a table index has been disabled by setting the index's Enabled property to **No**, the select statement that references the index is still valid. However, the database can't use the index as a hint for how to sort the data, because the index doesn't exist in the database.

The following table is an overview of how to use the index hint and order by keywords in select statements.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>To</p></th>
<th><p>Use</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Select records where the order isn't significant.</p></td>
<td><p>select ..</p>
<p>where ...</p></td>
</tr>
<tr class="even">
<td><p>Select records where the order is significant.</p></td>
<td><p>select ..</p>
<p>order by ...</p>
<p>where ...</p></td>
</tr>
<tr class="odd">
<td><p>Select records and force a specific index to be used.</p></td>
<td><p>select ..</p>
<p>index hint ...</p>
<p>where ...</p></td>
</tr>
<tr class="even">
<td><p>Select records where the order is significant and force a specific index to be used.</p></td>
<td><p>select ..</p>
<p>index hint ...</p>
<p>order by ...</p>
<p>where ...</p></td>
</tr>
</tbody>
</table>


## Example 1

To select the transactions from the salestable based on a range of customers and due dates, use the following code.

    SalesTable salesTable;
        select salesTable
        index hint CustIdx
        order by CustAccount
        where salesTable.CustAccount >= '3000'
              && salesTable.CustAccount <= '4000'
                        && salesTable.FixedDueDate >= 12\12\2004
                        && salesTable.FixedDueDate <= 05\05\2009;

## Using Index Hints

To use index hints in queries you must first specify the use of hints on the server using the following procedure.

1.  Open **Start** \> **Administrative Tools** \> **Microsoft Dynamics AX Server Configuration** and select the **Database Tuning** tab.

2.  Select **Allow INDEX hints in queries** and click OK.

3.  A message box prompting you to restart the AOS service appears. Click **Yes** to restart the AOS service. Index hints won't be enabled until the service is restarted.


> [!NOTE]
> <P>When an index hint in a select statement refers to a non-clustered index and the WHERE clause contains only the fields that are found in a clustered index on the same table, the clustered index is used instead of the index specified in the hint.</P>



For example, if you run sp\_helpindex InventTable in SQL Server Management Studio, you see that the InventTable has a clustered index on the DataAreaId and ItemId columns and a non-clustered index on the DataAreaId, ItemProductId, and ItemType columns.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Index name</p></th>
<th><p>Description</p></th>
<th><p>Key columns</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>I_175ITEMIDX</p></td>
<td><p>Clustered, unique, primary key located on PRIMARY</p></td>
<td><p>DATAAREAID, ITEMID</p></td>
</tr>
<tr class="even">
<td><p>I_175PRODUCTIDX</p></td>
<td><p>Nonclustered located on PRIMARY</p></td>
<td><p>DATAAREAID, ITEMPRODUCTID, ITEMTYPE</p></td>
</tr>
</tbody>
</table>


In the following code the clustered index will be used instead of the non-clustered index specified in the index hint.

    static void IndexHint(Args _args)
    {
        InventTable inv;
        ;
        select * from inv index hint GroupItemIdx 
            where inv.ItemId == 'B-R14';
    }

## See also

[How to: Create an Index](how-to-create-an-index.md)

[Table Index Properties](https://msdn.microsoft.com/en-us/library/aa881522\(v=ax.60\))

[How to: Update Data](how-to-update-data.md)

[Select Statements](select-statements.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

