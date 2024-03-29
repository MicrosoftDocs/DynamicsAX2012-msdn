---
title: 'X++ Standards: select Statements'
TOCTitle: 'X++ Standards: select Statements'
ms:assetid: bc884a0f-629c-49be-a2af-868a28d465a4
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa861766(v=AX.60)
ms:contentKeyID: 35250003
ms.date: 05/18/2015
mtps_version: v=AX.60
description: Master X++ standards for select statements in Microsoft Dynamics AX 2012. Learn best practices, usage of keywords, and how to optimize your code.
---

# X++ Standards: select Statements 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The basic rules for select statements are as follows:

  - Specify what records you need by using the where statement to limit the returned rows. To sort the returned records, use the order by statement.

  - Add an index hint on realistic data only if you discover performance problems without the hint.

  - Use the index keyword if the order should be defined by the index definition.

## Ordering of Data

Most select statements should be written without an index or an index hint, leaving the job of ordering the data to the optimizer in the database system. Whenever you use the index hint functionality, make a comment about why you are explicitly specifying it, thereby taking control away from the database management system (DBMS). Consider using the forceLiterals or forcePlaceholder statements as well or instead of select statements.


> [!NOTE]
> <P>Be careful when using the forceLiterals keyword in X++ select statements. It could expose code to an SQL injection security threat.</P>



Use the order by statement when you want the data ordered, and you do not want to specify which index to use. Ordering of data can take time and should only be done if needed.

Use the index keyword when you want the data to be centrally ordered as specified in the index specification on the table. If the index is specified as Enabled: No, an index is not generated by the database system.

The use of the index statement can sometimes result in an index hint. 

## Using the firstOnly Qualifier

If you are going to use only the first record or if only one record can be found, use the firstOnly qualifier. This optimizes the select statement for only one record.


> [!NOTE]
> <P>The firstOnly qualifier does not guarantee that only one record is returned. For more information, see <A href="x-keywords.md">X++ Keywords</A>.</P>



Do not use while select firstOnly.

The firstOnly qualifier and the field list are implicit in (select...).\< field \> statements, and are not explicitly needed. Use this kind of select statement wherever reasonable.

It is a best practice to use the firstOnly qualifier in find methods on tables. 

## Using select Statements Locally in Methods

If a select statement is local to a method, use a field list to increase performance. If you use a select or a while select statement and the size of the fields that are used total less than 50 percent of the total record size, a warning appears if you do not use a field list. ![Warning icon](images/Aa658028.WarningIcon(en-us,AX.60).gif "Warning icon")

If a select statement is local to a method and the firstOnly qualifier is not used, you must use the next statement on the result set. ![Warning icon](images/Aa658028.WarningIcon(en-us,AX.60).gif "Warning icon")

## Layout Examples

Here are two (contrived) examples of how to find ledger transactions in account number, transaction date order.

The following code shows how to find the last week's (that is, a few days) transactions on all of the (many) Profit and Loss accounts.

select firstOnly ledgerTrans

     index hint DateIdx

    order by accountNum, transDate

    where ledgerTrans.accountNum \>= '40000'    

        && ledgerTrans.accountNum \<= '99999'    

        && ledgerTrans.transDate \>= 26\\04\\1999

        && ledgerTrans.transDate \<= 02\\05\\1999;

The following code shows how to find transactions for the entire year (many dates) on (the few) liquid assets accounts.

while select ledgerTrans

    order by accountNum, transDate

    where ledgerTrans.accountNum \>= '11100'    

        && ledgerTrans.accountNum \<= '11190'    

        && ledgerTrans.transDate \>= 01\\07\\1999

        && ledgerTrans.transDate \<= 30\\06\\2000

{

    // Do whatever is needed.

    print ledgerTrans.amountMST;

}

Following are best practices from the previous examples:

  - The index, order by, and where statements are indented once relative to the select or while select statements.

  - The where expression is structured in a column.

  - The Boolean operators (&&) are at the beginning of the line (and in columns).

  - The while select block has braces even though it contains only one statement.

  - The braces are at the same column position as the while block.

  - The uppercase- and lowercase-name standards are adhered to.

## See also

[Select Statements](select-statements.md)

[Queries Best Practices](queries-best-practices.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

