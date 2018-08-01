---
title: Writing a Select Statement as an Expression
TOCTitle: Writing a Select Statement as an Expression
ms:assetid: f24bc2d7-22f3-42d4-9d41-79e686d1c028
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Ee677512(v=AX.60)
ms:contentKeyID: 35253413
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Writing a Select Statement as an Expression [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

In Microsoft Dynamics AX, you can use an X++ SQL select statement as an expression. This is called an expression select. A table buffer variable cannot be used in an expression select statement. The name of the table must be used in the from clause.

## Limitations of Expression Selects

The following table shows some limitations of expression selects.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Limitation</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>join keyword is not supported</p></td>
<td><p>The join keyword is not supported in an expression join.</p>
<p>Test_3 in the code sample shows that a subselect is supported, but only in a limited way.</p></td>
</tr>
</tbody>
</table>


## Code Sample and Test Cases

The following table describes the test cases in the code sample.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Test case</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Test_1.a</p></td>
<td><p>The select statement inside the parentheses returns one row. The only column that can be populated with data is the column that is named in the select clause before the from clause. The name of that one column is used after the closing parenthesis to reference the data value: ).AccountNum;.</p>
<p>This test case returns a maximum of one row because it uses the firstonly keyword. However, the value that is assigned to sAccountNum is the same even if the firstonly keyword is omitted.</p>
<p>The where clause in this example serves no purpose other than to show that the where clause must occur after the order by clause. The table name cannot be used to qualify a field name in the order by clause.</p></td>
</tr>
<tr class="even">
<td><p>Test_1.b</p></td>
<td><p>This is a simpler way to achieve the same result as Test_1.a.</p></td>
</tr>
<tr class="odd">
<td><p>Test_2.c</p></td>
<td><p>Includes a where clause. In a where clause, the table name must be used as a qualifier of the field.</p>
<p>Here the maxof aggregate function is used, and the field RecId is mentioned in the function. The field that is mentioned in the aggregate function must be the same field name that is used to reference the data value after the closing parenthesis. Otherwise, empty data is returned.</p></td>
</tr>
<tr class="even">
<td><p>Test_2.d</p></td>
<td><p>Demonstrates that a field name, here RecId, is used to reference a data value that is not a RecId. The count aggregate function does not return a RecId value. The RecId field is ordinarily used with the count function.</p></td>
</tr>
<tr class="odd">
<td><p>Test_3</p></td>
<td><p>The join keyword is not supported in expression selects. This test case demonstrates a subselect. But expression selects do not support subselects that are equivalent to a standard inner join.</p>
<p>For instance, the following X++ SQL does not compile. The problem is that it mentions two tables inside one expression select, namely inside the subselect.</p>

```X++
// X++. This job does not compile.
static void BadJob86(Args _args)
{
    // Test_3.f
    sName = (select Name from AssetTable
        where AssetTable.AssetId ==
            // Here starts the subselect.
            (select AssetId from AssetTrans
                where AssetTrans.AssetId ==
                    AssetTable.AssetId // Compiler rejects this line.
            ).AssetId).Name;
    info(strFmt(&quot;Test_3: %1&quot;, sName));
}
```
</td>
</tr>
</tbody>
</table>


### ![Ee677512.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Ee677512.collapse_all(en-us,AX.60).gif")Code Sample

The following code sample demonstrates several expression selects. Its test cases are described in the previous table.

```X++
    // X++
    static void SelectAsExpression3Job(Args _args)
    {
        int64 nRecId,
            nCount;
        str sAccountNum,
            sName;
        ;
        // Test_1.a
        sAccountNum = (select firstonly AccountNum from CustTable
            order by AccountNum desc
            where 0 == 0 // 'where' must occur after 'order by'.
            ).AccountNum;
        info(strFmt("Test_1.a: %1", sAccountNum));
    
        // Test_1.b
        sAccountNum = (select maxof(AccountNum) from CustTable).AccountNum;
        Global::info(strFmt("Test_1.b: %1", sAccountNum));
    
        // Test_2.c
        nRecId = (select maxof(RecId) from CustTable
            where CustTable.Blocked == CustVendorBlocked::No).RecId;
        info(strFmt("Test_2.c: %1", nRecId));
    
        // Test_2.d
        nRecId = (select count(RecId) from CustTable
            where CustTable.Blocked == CustVendorBlocked::No).RecId;
        info(strFmt("Test_2.d: %1", nRecId));
        
        // Test_3
        sName = (select Name from AssetTable
            where AssetTable.AssetId ==
                (select AssetId from AssetTrans
                    where AssetTrans.AssetId == "CNC-01"
                ).AssetId).Name;
        info(strFmt("Test_3: %1", sName));
    }
```

The output from a run of the previous code sample is shown in the following table.

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Output to Infolog</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Test_1.a: 4507</p>
<p>Test_1.b: 4507</p>
<p>Test_2.c: 5637144604</p>
<p>Test_2.d: 29</p>
<p>Test_3: CNC-Metal shade</p></td>
</tr>
</tbody>
</table>


## See also

[Select Statements](select-statements.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

