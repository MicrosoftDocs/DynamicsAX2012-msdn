---
title: Cross-Company and the company Getter Method
TOCTitle: Cross-Company and the company Getter Method
ms:assetid: fc0e61d3-3e43-49f2-9a82-ff1fb189d5cd
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc642824(v=AX.60)
ms:contentKeyID: 35254198
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Cross-Company and the company Getter Method 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The dataAreaId value returned by the company getter method on table buffer variables can differ between cross-company versus single-company scenarios.

For information about how a table buffer variable inherits company from the xRecord class, see [Cross-Company Methods and Properties](cross-company-methods-and-properties.md).

Tables can be categorized into the following types:

  - Global - The **SaveDataPerCompany** property is set to **No**.

  - Company-specific - The **SaveDataPerCompany** property is set to **Yes**.

  - Shared - Company-specific tables associated with a virtual company.

These different types of tables interact differently with the cross-company feature. In cross-company scenarios, the current company can be different from the company of the row currently being processed by the application X++ code. This difference has implications for the company getter method.


> [!NOTE]
> <P>The current company (the user's session company) is shown in the status bar in the lower-right portion of the Microsoft Dynamics AX client window.</P>



## Global Tables and the company Method

For a table buffer variable declared from a global table, the company getter method returns the user's session company. Global tables do not have the field named dataAreaId.

## Company-Specific Tables and the company Method

A table buffer variable declared from a company-specific table can be populated by a while select crossCompany statement. This populates the buffer with rows that represent a variety of companies. When a buffer is populated in this manner, the company method returns the dataAreaId value of the buffer's current row, regardless of the user's session company.

## Shared Tables and the company Method

For some rows in a shared table, the dataAreaId field can have a value representing the virtual company that the table is associated with. Other rows can have dataAreaId values for real companies that are outside of the virtual company.

The following X++ code example populates the table buffer with a row set from a shared table that has both kinds of dataAreaId values.

    while select crossCompany * from SH_buffer { /* X++ */ }

The following descriptions assume that the shared table is associated with virtual company VC9. The descriptions assume that VC9 is associated with real companies CM1 and CM2.

During the while select loop that processes rows of each dataAreaId value, the company getter method on the table buffer returns values according to the following table.

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Test case number</p></th>
<th><p>dataAreaId in shared table's current row</p></th>
<th><p>Current session company</p></th>
<th><p>Returned by company getter method</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>1</p></td>
<td><p>VC9</p></td>
<td><p>CM1</p></td>
<td><p>CM1</p></td>
</tr>
<tr class="even">
<td><p>2</p></td>
<td><p>VC9</p></td>
<td><p>CM2</p></td>
<td><p>CM2</p></td>
</tr>
<tr class="odd">
<td><p>3</p></td>
<td><p>VC9</p></td>
<td><p>CM3</p></td>
<td><p>Either CM1 or CM2, whichever the user has greater permissions on.</p>
<p>For example, Delete permission is greater than Read permission.</p></td>
</tr>
<tr class="even">
<td><p>4</p></td>
<td><p>CM3</p></td>
<td><p><em>(Any company)</em></p></td>
<td><p>CM3</p></td>
</tr>
</tbody>
</table>



> [!NOTE]
> <P>In Microsoft Dynamics AX 2009 the above table describes the behavior when either a table or a view is the subject of the while select. In the previous version, it applied to tables but not to views.</P>



### ![Cc642824.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc642824.collapse_all(en-us,AX.60).gif")Rules Governing the company Method

The following rules govern the behavior of the company getter method of table buffer objects:

  - The session company can never be a virtual company.

  - The company method never returns a value that conflicts with the dataAreaId of the current row. The dataAreaId takes precedence over the session company.

  - The company method never returns the dataAreaId value of a virtual company. Instead, a real company in the virtual company is returned.

  - When the current row has the dataAreaId of a virtual company, the company method returns one of the real companies in the virtual company.

  - After the clear method is called on a table buffer, the company getter method retrieves the current company of the client. However, this is not true for temporary tables.

### ![Cc642824.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc642824.collapse_all(en-us,AX.60).gif")Greater Permissions Factor for Test Case 3

Test case number 3 in the preceding table shows that sometimes the system chooses which real company to return when the company method is called. In cases where the session company is not part of the current row's virtual company, the company method returns whichever real company the user has the most permissions for.

In test case 3, if the user has both read and insert permission for CM1, but only read permission for CM2, then CM1 is returned.

The system determines which real company the user has greater permissions for only when the session company is not in the virtual company.

## See also

[Best Practices for Table Collections](best-practices-for-table-collections.md)

[Table Properties](https://msdn.microsoft.com/en-us/library/aa871620\(v=ax.60\))

[xRecord.company Method](https://msdn.microsoft.com/en-us/library/gg929126\(v=ax.60\))

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

