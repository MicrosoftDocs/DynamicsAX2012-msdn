---
title: Select Statement Examples
TOCTitle: Select Statement Examples
ms:assetid: 9f4f3861-8b60-43a8-8c3e-c89ffad2a832
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa848113(v=AX.60)
ms:contentKeyID: 35248262
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Select Statement Examples [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

All of the following examples use the CustTable.

## General Examples

The following X++ job shows several small examples of how you can use the select statement.

    static void SelectRecordExamples3Job(Args _args)
    {
        CustTable custTable;  // As of AX 2012.
    
        // A customer is found and returned in custTable
        select * from custTable;
        info("A: " + custTable.AccountNum);
    
        // A customer with account number > "100" is found
        select * from custTable
            where custTable.AccountNum > "100";
        info("B: " + custTable.AccountNum);
    
        // Customer with the lowest account number > "100" found:
        select * 
            from custTable 
                order by accountNum
                    where custTable.AccountNum > "100";
        info("C1: " + custTable.AccountNum);
    
        // The next customer is read
        next custTable;
        info("C2: " + custTable.AccountNum);
    
        // Customer with higest account number
        // (greater than 100) found: Fourth Coffee
        select * 
            from custTable 
                order by accountNum desc
                    where custTable.accountNum > "100";
        info("D1: " + custTable.AccountNum);
        
        // The next record is read (DESC): Fabrikam, Inc.
        next custTable; 
        info("D2: " + custTable.AccountNum);
    
        // Customer with highest account number found: Fourth Coffee
        select reverse custTable 
            order by accountNum;
        info("E: " + custTable.AccountNum);
    
        // Customer with "lowest" name and account number
        // in the interval 100 to 1000 is found. This is Coho Winery.
        select * 
            from custTable 
                order by DlvMode
                    where custTable.accountNum > "100"
                        && custTable.accountNum < "1000";
        info("F: " + custTable.AccountNum);
    
        // The count select returns the number of customers.
        select count(AccountNum) 
            from custTable;
        // Prints the result of the count
        info(strFmt("G: %1 = Count of AccountNums", custTable.accountNum));
    
        // Returns the average credit max for non-blocked customers.
        select avg(CreditMax) 
            from custTable
                where custTable.blocked == CustVendorBlocked::No;
        // Prints the result of the avg
        info(strFmt("H: %1 = Average CreditMax", custTable.CreditMax));
    }
    /*** Display from infolog:
    Message (02:00:34 pm)
    A: 4000
    B: 4000
    C1: 4000
    C2: 4001
    D1: 4507
    D2: 4506
    E: 4507
    F: 
    G: 29 = Count of AccountNums
    H: 103.45 = Average CreditMax
    ***/

## Join Sample

This X++ code sample shows how an inner join can be performed as part of an SQL select statement.

The sample also shows an order by clause that has each field qualified by a table name. This enables you to control how the retrieved records are sorted by using only one order by clause.

    static void SelectJoin22Job(Args _args)
    {
        CustTable xrecCustTable;
        CashDisc xrecCashDisc;
        struct sut4;
    
        sut4 = new struct("str AccountNum; str CashDisc; str Description");
    
        while select firstOnly10 *
            from xrecCustTable
                order by xrecCashDisc.Description
                    join xrecCashDisc
                        where xrecCustTable.CashDisc ==
                            xrecCashDisc.CashDiscCode
                            && xrecCashDisc.Description LIKE "*Days*"
        {
            sut4.value("AccountNum", xrecCustTable.AccountNum );
            sut4.value("CashDisc", xrecCashDisc.CashDiscCode );
            sut4.value("Description", xrecCashDisc.Description );
    
            info(sut4.toString());
        }
    /*********  Actual Infolog output
    Message (02:29:37 pm)
    (AccountNum:"1101"; CashDisc:"0.5%D10"; Description:"0.5% 10 days")
    (AccountNum:"4001"; CashDisc:"0.5%D10"; Description:"0.5% 10 days")
    (AccountNum:"1102"; CashDisc:"0.5%D30"; Description:"0.5% 30 days")
    (AccountNum:"1201"; CashDisc:"0.5%D30"; Description:"0.5% 30 days")
    (AccountNum:"2211"; CashDisc:"0.5%D30"; Description:"0.5% 30 days")
    (AccountNum:"1202"; CashDisc:"1%D15"; Description:"1% 15 days")
    (AccountNum:"1203"; CashDisc:"1%D07"; Description:"1% 7 days")
    (AccountNum:"2212"; CashDisc:"1%D07"; Description:"1% 7 days")
    (AccountNum:"2213"; CashDisc:"1%D07"; Description:"1% 7 days")
    (AccountNum:"2214"; CashDisc:"1%D07"; Description:"1% 7 days")
    *********/
    }

## Group By and Order By

This X++ code sample shows that the fields in the group by clause can be qualified with a table name. There can be multiple group by clauses instead of just one. The fields can be qualified by table name in only one group by clause. Use of table name qualifiers is recommended.

The order by clause follows the same syntax patterns that group by follows. If provided, both clauses must appear after the join (or from) clause, and both must appear before the where clause that might exist on the same join. It is recommended that all group by and order by and where clauses appear immediately after the last join clause.

    static void SelectGroupBy66Job(Args _args)
    {
        CustTable xrecCustTable;
        CashDisc xrecCashDisc;
        struct sut4;
    
        sut4 = new struct("str AccountNum_Count; str CashDisc; str Description");
    
        while select
            count(AccountNum)
            from xrecCustTable
                order by xrecCashDisc.Description
                    join xrecCashDisc
            group by
                xrecCashDisc.CashDiscCode
                        where xrecCustTable.CashDisc ==
                            xrecCashDisc.CashDiscCode
                            && xrecCashDisc.Description LIKE "*Days*"
        {
            sut4.value("AccountNum_Count", xrecCustTable.AccountNum );
            sut4.value("CashDisc", xrecCashDisc.CashDiscCode );
            sut4.value("Description", xrecCashDisc.Description );
    
            info(sut4.toString());
        }
    /*********  Actual Infolog output
    Message (02:45:26 pm)
    (AccountNum_Count:"2"; CashDisc:"0.5%D10"; Description:"")
    (AccountNum_Count:"3"; CashDisc:"0.5%D30"; Description:"")
    (AccountNum_Count:"4"; CashDisc:"1%D07"; Description:"")
    (AccountNum_Count:"1"; CashDisc:"1%D15"; Description:"")
    (AccountNum_Count:"1"; CashDisc:"2%D30"; Description:"")
    (AccountNum_Count:"1"; CashDisc:"3%D10"; Description:"")
    *********/
    }

## See also

[Select Statements](select-statements.md)

[while select Statements](while-select-statements.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

