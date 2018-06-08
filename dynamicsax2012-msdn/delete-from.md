---
title: delete_from
TOCTitle: delete_from
ms:assetid: 3aa57193-06c4-464e-a113-a5d1e3a934c2
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa624886(v=AX.60)
ms:contentKeyID: 35242883
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# delete\_from 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

You can delete multiple records from a database table by using a delete\_from statement. This can be more efficient and faster than deleting one record at a time by using the xRecord .delete method in a loop.

If you have overridden the [delete method](delete-table-method.md), the system interprets the delete\_from statement into code that calls the delete method one time for each row that is deleted.

## Example 1: Comparing Multi-record Delete Techniques

The code examples in this section show that some techniques for deleting multiple records are more efficient than other techniques.

### ![Aa624886.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa624886.collapse_all(en-us,AX.60).gif")Example 1a: Delete\_From to Delete Multiple Records

The following X++ code example is an efficient way to delete multiple records.

    static void DeleteMultiRow1aJob(Args _args)
    {
        MyWidgetTable tabWidget;
        ;
        delete_from tabWidget
            where tabWidget .quantity <= 100;
    }

### ![Aa624886.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa624886.collapse_all(en-us,AX.60).gif")Example 1b: Delete Method Plus ForUpdate Keyword

The following X++ code example is inefficient. It issues a separate SQL delete call to the database server for each record. The xRecord .delete method never deletes more than one record per call.

    static void DeleteMultiRow1bJob(Args _args)
    {
        MyWidgetTable tabWidget; // extends xRecord.
        ;
        ttsBegin;
        while select
            forUpdate
            tabWidget
            where tabWidget .quantity <= 100
        {
            tabWidget .delete();
        }
        ttsCommit;
    }

## Example 2: Delete Plus Inner Join Logic

X++ does not support an inner join on the delete\_from statement. Therefore you cannot use the unmodified join keyword on the delete\_from statement. However, there are other ways to logically accomplish an inner join.

The examples in this section show techniques for achieving inner join logic by a sequence of X++ statements.

### ![Aa624886.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa624886.collapse_all(en-us,AX.60).gif")Example 2a: Delete Method Plus Inefficient Inner Join Logic

The following X++ code example is inefficient. It issues a separate SQL delete call to the database server for each record.

    static void DeleteInnerJoin2aJob(Args _args)
    {
        MyWidgetTable tabWidget; // extends xRecord.
        ;
        ttsBegin;
        while select
            forUpdate
            tabWidget
            join tabGalaxy
                where
                    tabWidget .GalaxyRecId == tabGalaxy .RecId
                    && tabGalaxy .isTrusted == 0
        {
            tabWidget .delete();
        }
        ttsCommit;
    }

### ![Aa624886.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa624886.collapse_all(en-us,AX.60).gif")Example 2b: Delete\_From Plus Efficient Inner Join Logic

The following X++ code example is relatively efficient. It issues a separate delete\_from statement for each loop iteration. However, each delete\_from statement can delete multiple records, a subset of all the records that the job deletes.

    static void DeleteInnerJoin2bJob(Args _args)
    {
        MyWidgetTable tabWidget; // extends xRecord.
        ;
        ttsBegin;
        while select
            from tabGalaxy
                where tabGalaxy .isTrusted == 0
        {
            delete_from tabWidget
                where tabWidget .GalaxyRecId ==
                      tabGalaxy .RecId;
        }
        ttsCommit;
    }

## Example 3: Delete\_From Notexists Join

You can use the notexists join keyword pair in a delete\_from statement.

The delete\_from statements in the following X++ code example are efficient. The notexists join clause enables the delete\_from statement to delete a specific set of rows. In this example the delete\_from statement removes all the parent order header rows for which there are no child order line rows.


> [!NOTE]
> <P>&nbsp;&nbsp;You can also use the exists&nbsp;join clause on the delete_from statement.</P>



    static void DeleteFromNotexists3bJob(Args _args)
    {
        GmTabOrderHeader tabOHeader;
        GmTabOrderLine tabOLine;
        AddressState tabAddressState;
        str 127 sOH_Info;
        str 127 sOL_Data;
        int64 i64OHRecId;
        ;
        delete_from tabOLine;
        delete_from tabOHeader;
    
        // Inserts into parent table.
    
        sOH_Info = "Albert needs tires.";
        insert_recordset tabOHeader
            (OH_Info)
            select firstOnly sOH_Info from tabAddressState;
    
        sOH_Info = "Benson wants plastic.";
        insert_recordset tabOHeader
            (OH_Info)
            select firstOnly sOH_Info from tabAddressState;
    
        // Obtain a OrderHeader RecId,
        // use it to insert one child row.
    
        sOL_Data = "4 re-treads.";
        while select firstOnly tabOHeader
                order by OH_Info
                where tabOHeader .OH_Info like "A*"
        {
            i64OHRecId = tabOHeader .RecId;
            insert_recordset tabOLine
                (OL_Data ,OrderHeaderRecId)
                select firstOnly
                    sOL_Data ,i64OHRecId
                    from tabAddressState;
            break;
        }
    
        // Before the delete notexists.
        // Display all parent, and then all child rows.
    
        while select tabOHeader
            order by OH_Info
        {
            info(strFmt(
                "Before: OHeader:  OH_Info==%1 , RecId==%2"
                ,tabOHeader .OH_Info ,tabOHeader .RecId
                ));
        }
        while select tabOLine
            order by OL_Data
        {
            info(strFmt(
                "Before: OLine:  OL_Data==%1 , OrderHeaderRecId==%2"
                ,tabOLine .OL_Data ,tabOLine .OrderHeaderRecId
                ));
        }
    
        // Delete_From NotExists Join, to remove from the
        // parent table all order headers without children.
    
        delete_from tabOHeader
            notexists join tabOLine
                where tabOHeader .RecId ==
                    tabOLine .OrderHeaderRecId;
    
        info(strFmt
            ("%1 is the number of childless OHeader records deleted."
            ,tabOHeader.rowCount()));
    
        // After the delete notexists.
        // Display all parent, and then all child rows.
    
        info("- - - - - - - - - - - - - - -");
        while select tabOHeader
            order by OH_Info
        {
            info(strFmt(
                "After: OHeader:  OH_Info==%1 , RecId==%2"
                ,tabOHeader .OH_Info ,tabOHeader .RecId
                ));
        }
        while select tabOLine
            order by OL_Data
        {
            info(strFmt(
                "After: OLine:  OL_Data==%1 , OrderHeaderRecId==%2"
                ,tabOLine .OL_Data ,tabOLine .OrderHeaderRecId
                ));
        }
    /**************  Actual Infolog output
    Message (12:54:14 pm)
    Before: OHeader:  OH_Info==Albert needs tires. , RecId==5637144608
    Before: OHeader:  OH_Info==Benson wants plastic. , RecId==5637144609
    Before: OLine:  OL_Data==4 re-treads. , OrderHeaderRecId==5637144608
    1 is the number of childless OHeader records deleted.
    - - - - - - - - - - - - - - -
    After: OHeader:  OH_Info==Albert needs tires. , RecId==5637144608
    After: OLine:  OL_Data==4 re-treads. , OrderHeaderRecId==5637144608
    **************/
    }

## See also

[Speeding Up SQL Operations](speeding-up-sql-operations.md)

[Maintain Fast SQL Operations](maintain-fast-sql-operations.md)

[Select Statement Examples](select-statement-examples.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

