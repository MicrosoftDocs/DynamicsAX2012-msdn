---
title: Cross-Company X++ Code Basics
TOCTitle: Cross-Company X++ Code Basics
ms:assetid: 0312d6e1-e409-434f-8ee6-c2081f8d4002
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc518738(v=AX.60)
ms:contentKeyID: 35240189
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Cross-Company X++ Code Basics [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

You can create a cross-company query by using X++ code. There are two ways to do this:

  - crossCompany keyword on the select statement

  - Query class methods

A cross-company query can also be created under the Query node in the Application Object Tree (AOT).

A cross-company query cannot return data for companies that the user does not have permission to access. A cross-company query can be limited to a subset of the companies that the user is authorized to access.

The cross-company query is useful if at least one of the tables has the **SaveDataPerCompany** property set to **Yes**.

## crossCompany Keyword

You can create a cross-company query by using the crossCompany keyword on the X++ select statement. You have the option of adding a container variable of company identifiers immediately after the crossCompany keyword (separated by a colon). The container restricts the selected rows to those with a dataAreaId that match a value in the container.

The following code example populates a table buffer with all the BankAccountTable rows that have a dataAreaId of either cm1 or cm2 or dat. This example assumes that the user has authority to access data for these three companies. The first two dataAreaId values that are found will be printed.
```X++  
    static void JobDemoCrossCompany(Args _args)
    {
        BankAccountTable tabBAT; // saveDataPerCompany == true.
        container conCompanies = [ 'cm1', 'cm2', 'dat' ];
        str 4 sCompanyPrevious = " "; // Maximum length is 4 characters.
        int iCountCompanies = 0;
        ;
        while select
            crossCompany
                : conCompanies
            * from tabBAT
            order by dataAreaId
        {
            if ( sCompanyPrevious != tabBAT.dataAreaId )
            {
                info( tabBAT.dataAreaId + " = tabBAT.dataAreaId" );
                iCountCompanies++;
                if ( iCountCompanies >= 2 )
                {
                    break;
                }
                sCompanyPrevious = tabBAT.dataAreaId;
            }
        }
        return;
    }
```
## Query Class

In X++ code you can use the Query .allowCrossCompany property method to achieve the same result as you can with the crossCompany keyword on a select statement. The calls to the Query .addCompanyRange method are the same as appending a container of companies to the crossCompany keyword.

You cannot perform data source level filtering by company in a cross-company query. This is why the call to qbds3 .company is commented out in the following code example.
```X++  
    static void JobDemoAllowCrossCompany(Args _args)
    {
        BankAccountTable tabBAT; // saveDataPerCompany == true.
        Query qry2;
        QueryBuildDataSource qbds3;
        QueryRun qrun4;
        str sCompanyPrevious = "   ";
        int iCountCompanies = 0;
        int iTableNumBAT;
        ;
        qry2 = new Query();
        qry2.allowCrossCompany( true );
        qry2.addCompanyRange( 'dat' );
        qry2.addCompanyRange( 'twf' );
        
        iTableNumBAT = tableNum( BankAccountTable );
        qbds3 = qry2 .addDataSource( iTableNumBAT );
        //qbds3.company( 'dat' );
        
        qrun4 = new QueryRun( qry2 );
        
        while ( qrun4.next() )
        {
            if ( qrun4.changed( iTableNumBAT ) )
            {
                tabBAT = qrun4.get( iTableNumBAT );
        
                if ( sCompanyPrevious != tabBAT.dataAreaId )
                {
                    print( tabBAT.dataAreaId + " = tabBAT.dataAreaId" );
                    iCountCompanies++;
                    if ( iCountCompanies >= 2 )
                    {
                        break;
                    }
                    sCompanyPrevious = tabBAT.dataAreaId;
                }
            }
        }
        pause;
        return;
    }
```
## Query in the AOT

In the AOT, you can get cross-company functionality from a query node by setting the **AllowCrossCompany** property to **Yes** (the equivalent of true in X++ code). You can override methods on the node of your query to call the Query.addCompanyRange method.

For more information, see [Cross-Company Reports in the AOT](cross-company-reports-in-the-aot.md).

## See also

[Cross-Company Data Access](cross-company-data-access.md)

[DataArea Table](https://msdn.microsoft.com/en-us/library/gg887932\(v=ax.60\))

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

