---
title: while select Statements
TOCTitle: while select Statements
ms:assetid: 1f749f04-8604-46e6-b444-bf6fa5c2482b
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa558063(v=AX.60)
ms:contentKeyID: 35241513
ms.date: 05/18/2015
mtps_version: v=AX.60
description: Master the use of while select statements in Microsoft Dynamics AX 2012 with this comprehensive guide. Learn syntax, examples, and optimization tips.
---

# while select Statements 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

while select statements are used to handle data. They are the most widely used form of the [select statement](select-statements.md) in X++.

while select loops over many records (meeting certain criteria) and can execute a statement on each record.

When you perform data manipulation by using the while select statement, you would typically do this in a [transaction](transaction-integrity.md) to ensure data integrity.

In a while select, the select statement itself is executed only one time, immediately before the first iteration of the statements in the loop. Also, any Boolean expressions (such as iCounter \< 1) added to the while select are tested only one time. This differs from how the while statement behaves in languages such as C++ and C\#. For example, in X++ the following loop could iterate more than one time.
```X++  
    static void JobWhileSelect(Args _args) // X++ job.
    {
        int iCounter = 0;
        BankAccountTable xrecBAT;
    
        while select * from xrecBAT
            where iCounter < 1
        {
            iCounter++;
            Global::info(strFmt("%1 , %2", iCounter, xrecBAT.AccountID));
        }
    }
    /*** Display from infolog:
    Message (04:59:38 pm)
    1 , Cash1
    2 , STB-DKK
    3 , STB-EUR
    ***/
```
The results of a while select statement are returned in a table buffer variable. If you use a field list in the select statement, only those fields are available in the table variable. If you use aggregate functions such as sum or count, the results are returned in the fields you perform the sum or count over. You can only count, average, or sum the integer and real fields.

## Syntax

The syntax of a while select statement resembles that of a select statement except that it is preceded by while select instead of select.

## Examples

### ![Aa558063.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa558063.collapse_all(en-us,AX.60).gif")Printing a Sorted Telephone List for Some Customers
```X++  
    static void JobPrintTel(Args _args)
    {
        CustTable xrecCT;
    
        while select xrecCT 
            order by xrecCT.AccountNum
                where  xrecCT.AccountNum >= "4010" 
                    && xrecCT.AccountNum <= "4100"
        {
            Global::info(strFmt("%1 , %2", 
                xrecCT.AccountNum, xrecCT.SalesGroup));
        }
    }
    /*** Display from Infolog:
    Message (06:04:03 pm)
    4010 , CSG-EU
    4011 , CSG-EU
    4012 , CSG-OTH
    4013 , CSG-OTH
    4014 , CSG-OTH
    4015 , CSG-OTH
    4016 , CSG-EU
    4017 , CSG-EU
    4018 , CSG-EU
    4020 , 
    4024 , 
    ***/
```
This prints the name reference and telephone number of customers in CustTable who have an account number within a specified range.

### ![Aa558063.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa558063.collapse_all(en-us,AX.60).gif")deleteTransFromVoucher Method in the LedgerJournalTrans Table
```X++  
    static void LedgerJob(Args _args)
    {
        LedgerJournalTrans ledgerJournalTrans;
        LedgerJournalTable ledgerJournalTable;
        LedgerJournalId    jnJournalNum;
        Voucher            vVoucher;
        Counter            counter = 0;
    
        jnJournalNum = "999999_999"; //"000012_003";
        vVoucher = "88888_888"; //"00001_IRG";
        
        ledgerJournalTable = 
            ledgerJournalTable::find(jnJournalNum);
        
        ttsBegin;
     
        while select forUpdate ledgerJournalTrans
            index hint NumVoucherIdx
                where ledgerJournalTrans.journalNum == jnJournalNum 
                   && ledgerJournalTrans.voucher == vVoucher
        {
            ledgerJournalTrans.doDelete();
            counter++;
        }
        
        //NumberSeq updates needed?
        
        ttsCommit;
        
        Global::info(strFmt("counter = %1", counter));
    }
```
The previous code example uses the X++ forUpdate keyword.

## Deleting a Set of Records

Use a while select statement to loop over a set of records that meet some criteria and perform an action on each record. One such action is to delete.
```X++  
{   
   TableName myXrec;   
   while select myXrec   
     where  Conditions   
   {   
     myXrec.delete();   
   }   
 }
```
You can economize your X++ statements and achieve the same effect using the [delete\_from](delete-from.md) keyword.
```X++  
{   
   TableName myXrec;   
   delete\_from myXrec   
     where  Conditions ;   
 }
```
## See also

[Aggregate Functions: Differences Between X++ and SQL](aggregate-functions-differences-between-x-and-sql.md)

[Optimizing Record Inserts](optimizing-record-inserts.md)

[insert\_recordset](insert-recordset.md)

[Select Statement Syntax](select-statement-syntax.md)

[Select Statements](select-statements.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

