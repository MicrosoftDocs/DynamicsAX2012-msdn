---
title: Record Level Security
TOCTitle: Record Level Security
ms:assetid: e1af2783-0a55-433e-9e12-337fa08a206e
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa879172(v=AX.60)
ms:contentKeyID: 35253093
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Record Level Security [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Record-level security (RLS) is automatically handled by the kernel when a form or report is opened. However, record-level security is bypassed in the following situations:

  - Using display and edit methods

  - Using FormListControl, FormTreeControl or TableListControl to show data

  - Using a temporary table as a data source

You can enable the **Database trace** option to view messages that indicate when record-level security is applied to a method call.


> [!NOTE]
> <P>The record-level security feature will be removed in a future release. If you previously set up record-level security filters, they will continue to function. If you are setting up new filters, we recommend that you create data security policies using the extensible data security framework. For more information about data security policies, see <A href="overview-of-security-policies-for-table-records.md">Overview of Security Policies for Table Records</A>.</P>




> [!NOTE]
> <P>Record-level security has its own configuration key (SysRecordLevelSecurity).</P>



## Using Display and Edit Methods

Whenever a display or edit method is used to return a value from another row, you must evaluate the business impact of displaying this data. If you determine that displaying this data could cause unwanted data disclosure, you should perform an explicit authorization check before you call these methods.

Record-level security is not required in these situations:

  - When the value is calculated.

  - When the value is only based on the values of the fields in the current record.


> [!NOTE]
> <P>For more security-related information about how to use display and edit methods, see <A href="security-on-display-and-edit-methods.md">Security on Display and Edit Methods</A>.</P>



## Using FormListControl, FormTreeControl, and TableListControl to Show Data

Populating a FormListControl, FormTreeControl, or TableListControl with data from a query could lead to unwanted information disclosure. In these cases you should manually enable record-level security.

The following example illustrates how to manually enable record-level security:

    public void run
    {
        CustTable custTable;
    
        super();
    
        // Ensure record-level security (RLS) is used
        custTable.recordLevelSecurity(true);
    
        while select custTable
        {
            listView.add(custTable.AccountNum);
        }
    }

## Using a Temporary Table as a Data Source

When the form cache is being filled with data from a temporary table, you must make sure that the data uses record-level security. This includes tables that are declared as temporary in the code or where the **Temporary** property of a table in the Application Object Tree (AOT) has been set to **Yes**.

The following example shows how to use record-level security with a temporary table.

    public void run
    {
        CustTable custTable, tmpDatasource;
    ;
        // Ensure record-level security (RLS) is used
        custTable.recordLevelSecurity(true);
    
        while select custTable
        {
            tmpDataSource.data(custTable);
            tmpDataSource.insert();
        }
    
        formDataSource.setTmp();
        formDataSource.checkRecord(false);
        formDataSource.setTmpData(tmpDatasource);
    
        super();
    }

## Using Database Tracing to Identify Where Record-Level Security Is Applied

When the database trace is started, the output that it sends to the message window includes information about which statements have record-level security applied. A line displaying (RLS) at the end indicates that record-level security was enabled on the call to that method.

The following example message shows that record-level security is enabled on the call to the salesLine.select method.

salesLine.select() (RLS)

### To enable database tracing

1.  Click **Tools** \> **Options**, and then click the **Development** link.

2.  On the **Trace** FastTab, select the **Database trace** check box.

## See also

[Manage record level security](https://msdn.microsoft.com/en-us/library/aa570084\(v=ax.60\))

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

