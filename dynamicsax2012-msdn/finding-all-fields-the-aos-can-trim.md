---
title: Finding All Fields the AOS can Trim
TOCTitle: Finding All Fields the AOS can Trim
ms:assetid: 6bdc6817-d653-419c-a41b-426927326eac
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg840968(v=AX.60)
ms:contentKeyID: 35244795
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Finding All Fields the AOS can Trim [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

This topic provides a Microsoft Dynamics AX X++ code sample that reports the fields that the Application Object Server (AOS) would withhold or trim from a user. The security configuration of each field is assessed for the current user. This security behavior is called field trimming because the restricted fields are trimmed out of the results before the results are sent from the AOS to the client. The code sample scans all fields that are under **AOT** \> **Data Dictionary** \> **Tables**, for a specified range of tables.

## Trim a Field from the Results Based on AOS Authorization

When a user runs a query, the system can refuse to send data from the AOS for particular columns that the current user has no authority to access. The access is controlled by the AOSAuthorization property that is available on each field during run time. This property value cannot be known at compile time. The run time value of the AOSAuthorization property is controlled by the roles that the user belongs to.

## X++ Code Sample to Find Fields the User Cannot Access

The following code sample scans the system tables to find fields that the current user cannot access, on tables that he can otherwise access. The code prints progress reports to the **Print** window while it runs. The final output of field names appears in the **Infolog** window.

The macros near the top of the code sample are explained in a section that follows the code sample.
```X++  
    static void GmTrimAccessFieldScan3Job(Args _args)
    {
        // Edit the following three macro values to your needs.  For example:
        // ** Start: with a table whose name starts with an 'A'.
        // ** Stop:  with a table whose name starts with a 'Z'.
        #define.SearchTableNameRangeStart("")
        #define.SearchTableNameRangeStop("")
        #define.TargetTableNameLikeFilter("*")
    
        TreeNode tnTable,
            tnField;
        str sTableAosAuth,
            sFieldAosAuth;
        int nCountOfTpfTablesFound = 0,
            nCountOfAotTables = 0,
            nCountOfTrimmedFields = 0;
    
        // Establish start node among the table nodes.
        if (#SearchTableNameRangeStart == "")
        {
            tnTable = TreeNode::findNode
                ("\\Data Dictionary\\Tables").AOTfirstChild();
        }
        else
        {
            tnTable = TreeNode::findNode
                ("\\Data Dictionary\\Tables\\" + #SearchTableNameRangeStart);
        }
    
        
        while (true)
        {
            nCountOfAotTables++;
            // Provide ongoing progress reports.
            if ((nCountOfAotTables MOD 50) == 3)
            {
                print int2Str(nCountOfAotTables)
                    + " tables examined so far, at " + tnTable.AOTname();
                print int2Str(nCountOfTpfTablesFound) + " TPF okay tables found so far.";
                print int2Str(nCountOfTrimmedFields) + " trimmed fields found so far.";
                print "---------------- Wait...";
            }
            // Perhaps stop before the end of the AOT, for convenience.
            if (#SearchTableNameRangeStop < tnTable.AOTname() &&
                #SearchTableNameRangeStop != ""
               )
            {
                break;
            }
    
            // Apply the table name wild card filter.
            if (tnTable.AOTname() like #TargetTableNameLikeFilter)
            {
                sTableAosAuth = tnTable.AOTgetProperty('AOSAuthorization');
                // Test whether there is authority to access the table, under TPF.
                if (sTableAosAuth != 'None')
                {
                    nCountOfTpfTablesFound++;
                    // Loop through the fields on this table.
                    for (tnField = TreeNode::findNode
                            ('\\Data Dictionary\\Tables\\'
                                + tnTable.AOTname()
                                + '\\Fields').AOTfirstChild();
                        tnField;
                        tnField = tnField.AOTnextSibling()
                        )
                    {
                        sFieldAosAuth = tnField.AOTgetProperty('AOSAuthorization');
                        // Test whether there is authority to access the field.
                        if (sFieldAosAuth != 'No')
                        {
                            nCountOfTrimmedFields++;
                            info(strFmt('%1 %2 is a trimmed field that you cannot access.',
                                tnTable.AOTname(), tnField.AOTname()));
                        }
                    } // for each field in AOT
                } // if table is guarded by the Table Protection Framework (TPF).
            } // name is Like
    
            // Prepare for next interation of this loop.
            tnTable = tnTable.AOTnextSibling();
            if (tnTable == null) break;
    
        } // for each table in AOT
    
        print "-------- Final Report (see also the Infolog) --------";
        print int2Str(nCountOfAotTables)
            + " tables examined so far, at end.";
        print int2Str(nCountOfTpfTablesFound) + " TPF tables found so far, at end.";
        print int2Str(nCountOfTrimmedFields) + " trimmed fields found so far, at end.";
        print "-------- Done. --------";
        pause;
    }
```
## Explanation of the Macros

This section explains the use of the macro definitions in the previous code sample.

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Macro name</p></th>
<th><p>Default value</p></th>
<th><p>Sample value</p></th>
<th><p>Comment</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>#SearchTableNameRangeStart</p></td>
<td><p>&quot;&quot;</p>
<p>The recommended default value is the two character string &quot;&quot; (just two quotation marks). This causes the code to begin its scan at the first table under <strong>AOT</strong> &gt; <strong>Data Dictionary</strong> &gt; <strong>Tables</strong>.</p></td>
<td><p>&quot;CaseAssociation&quot;</p>
<p>You can write the name of a specific table inside the quotation marks, such as &quot;CaseAssociation&quot;. The scan skips all tables that appear under the <strong>Tables</strong> node previous to this table. In this example, any table name that starts the letter A or B is skipped.</p></td>
<td><p>This macro specifies the start point of a scan range, and the #SearchTableNameRangeStop macro specifies the end point of the range.</p>
<p>The use of a narrow range can greatly reduce the default run duration of perhaps 30 minutes.</p></td>
</tr>
<tr class="even">
<td><p>#SearchTableNameRangeStop</p></td>
<td><p>&quot;&quot;</p>
<p>The recommended default value is the two character string &quot;&quot; (just two quotation marks). This causes the code to end its scan at the final table under <strong>AOT</strong> &gt; <strong>Data Dictionary</strong> &gt; <strong>Tables</strong>.</p></td>
<td><p>&quot;CustVendTransportTime&quot;</p>
<p>You can write the name of a specific table inside the quotation marks, such as &quot;CustVendTransportTime&quot;. The scan skips all tables that appear under the <strong>Tables</strong> node following this table. In this example, any table name that starts a letter D-Z is skipped.</p></td>
<td><p>This macro specifies the stop point of a scan range, and the #SearchTableNameRangeStart macro specifies the start point of the range.</p></td>
</tr>
<tr class="odd">
<td><p>#TargetTableNameLikeFilter</p></td>
<td><p>&quot;*&quot;</p>
<p>The recommended default value is the of the three character string &quot;*&quot; (quotation marks included). The asterisk is a wildcard that matches zero-to-many characters of any type. The asterisk is used with the X++ like operator. The default value matches each table name during the loop, except the tables that are excluded by the range macros.</p></td>
<td><p>&quot;Cust*&quot;</p>
<p></p></td>
<td><p>The duration of the code sample is increased only slightly if an asterisk wildcard occurs at the start of the macro value.</p></td>
</tr>
</tbody>
</table>


## See also

[runAs Function](https://msdn.microsoft.com/en-us/library/aa893873\(v=ax.60\))

[Security Policies in the AOT for Data Records](security-policies-in-the-aot-for-data-records.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

