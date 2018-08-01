---
title: Cross-Company Reports in the AOT
TOCTitle: Cross-Company Reports in the AOT
ms:assetid: 44a9703a-ec7c-4d86-9847-f644a6c3d9af
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc588001(v=AX.60)
ms:contentKeyID: 35242960
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Cross-Company Reports in the AOT [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

You can use the Application Object Tree (AOT) to create a cross-company report. The simplest way to create a report is to set the **AllowCrossCompany** property to **Yes** on your query. Then drag the query node onto your report's **Data Sources** node.

To fully control the cross-company behavior of an AOT query or report, you must understand the relationships between:

  - AOT query node

  - Query class

  - QueryRun class

For basic information about cross-company queries, see [Cross-Company X++ Code Basics](cross-company-x-code-basics.md).

## Relationships between AOT, Query, and QueryRun

The properties of an AOT query node match the Query class. The methods available for override on a query node match the QueryRun class.

The QueryRun class has a property method named query, which is the query instance it will run. You can access this QueryRun .query property in methods that you override on the **Queries** node of the AOT. This enables you to control the details of the cross-company behavior at run time.

## AllowCrossCompany Property

In the AOT, query node objects have the **AllowCrossCompany** property listed in the **Properties** window. For new queries the default value is **No** (which is equivalent to false in X++ code). To make a query cross-company you need to set **AllowCrossCompany** to **Yes**.

The classes QueryRun and Query both have the **AllowCrossCompany** property, but their values always equal each other. When you read **AllowCrossCompany** from QueryRun, QueryRun reads it from Query. When you set **AllowCrossCompany** on QueryRun, it sets in on Query.


> [!NOTE]
> <P>Although the QueryRun class and Query classes both have the allowCrossCompany property, only the Query class has the cross-company methods such as addCompanyRange.</P>



## Company Range Methods in AOT Reports

You can override methods on the AOT report node to control the details of cross-company behavior. For example, you could override the report's **init** method with the following X++ code.

```X++
    public void init()
    {
        super();
        this.query().allowCrossCompany( true );
        this.query().addCompanyRange( "dat" );
        this.query().addCompanyRange( "dmo" );
    }
```

## See also

[MorphX Reporting Tools](https://msdn.microsoft.com/en-us/library/bb427701\(v=ax.60\))

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

