---
title: Effects of Valid Time State Tables on Read and Write Operations
TOCTitle: Effects of Valid Time State Tables on Read and Write Operations
ms:assetid: 15000280-13d7-498e-a5f3-c684e185eb08
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg843767(v=AX.60)
ms:contentKeyID: 35240608
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Effects of Valid Time State Tables on Read and Write Operations 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

This topic uses X++ code examples to demonstrate the behavior of operations that read and write data in a valid time state table. The system affects the behaviors in ways that are not always visually apparent in your X++ code.

## Prerequisites

Before you read this topic, you should read the topic [Walkthrough: Creating a Valid Time State Table](walkthrough-creating-a-valid-time-state-table.md). The scenario in that topic creates the table needed for use with this topic, along with other structures that you need.

## Description of This Scenario

In the present scenario, you write X++ code to insert, delete, and update data in the table. After each data modification stage, you select rows from the table to see the effects.

You need to have a valid time state table TabEmplProjVts open to complete this topic.

## Phases of This Scenario

In this scenario, you perform the following tasks:

  - Delete all rows from the table.

  - Insert rows.

  - Examine all rows.

  - Select rows for specific effective dates.

  - Update a date range.

## Delete All Rows from the Table

Run the following X++ code to delete all rows.

Notice that the deletions are performed in a while loop one row at a time, rather than all rows being deleted in one set operation. Tables with their **ValidTimeStateFieldType** property set to **Yes** cannot have deletes, inserts, or updates performed in one multi-row operation. If your X++ SQL code is designed to perform a multi-row operation, the system internally transforms it into many single-row operations.

   ```X++

    static void Vts2_DeleteVtsJob25(Args _args) // X++ Job, in AOT > Jobs.
    {
        TabEmplProjVts xEP;
        
        delete_from xEP;
        
        info("ALL rows deleted from TabEmplProjVts, not just current rows.");
    }
    /** Pasted of the output:
    Message (06:17:57 pm)
    ALL rows deleted from TabEmplProjVts, not just current rows.
    **/
   ```

## Insert Rows into the Table

Run the following X++ job code. The data to be inserted has been designed so that no two rows with the same combination of employee plus project have an overlap in the date range.

   ```X++
   static void Vts2_InsertVtsJob30(Args _args)
    {
        //-------- Inner function.
        void OneEP
            (str sEm, str sPr, str sKey,
            str sColor, str sFruit,
            date vFrom, date vTo)
        {
            TabEmplProjVts xEP;
    
            xEP.EmplID        = sEm;
            xEP.ProjID        = sPr;
            xEP.EPPrimaryKey  = sKey;
            xEP.AssocColor    = sColor;
            xEP.AssocFruit    = sFruit;
            xEP.ValidFrom     = vFrom;
            xEP.ValidTo       = vTo;
    
            xEP.insert();
            xEP = null;
        }
        //-------- End of inner function.
    
        OneEP("em21", "pr44", "key61", "Red"   , "Apple" , 1\1\2000 , 31\12\2003);
        OneEP("em21", "pr44", "key62", "Orange", "Banana", 1\1\2004 , 31\12\2039);
    
        OneEP("em22", "pr44", "key63", "Yellow", "Cherry", 1\1\2001 , 31\12\2005);
        OneEP("em22", "pr44", "key64", "Green" , "Fig"   , 1\1\2009 , 31\12\2038);
    
        OneEP("em22", "pr45", "key65", "Blue"  , "Grape" , 13\2\1910, 14\3\1924 );
        OneEP("em22", "pr45", "key66", "Indigo", "Lemon" , 16\5\1936, 17\6\1948 );
        OneEP("em22", "pr45", "key67", "Violet", "Melon" , 18\7\2111, 19\8\2119 );
    
        Global::info("7 rows were inserted.");
    }
    /**  Output to Infolog
    Message (02:32:45 pm)
    7 rows are inserted.
    **/
   ```

## Examine All Rows in the Table

Run the following X++ code to display all the rows that were inserted into the table.

Notice the validTimeState keyword that appears after the select keyword. Two date values are passed in as parameters. In this case, they represent the largest possible date range, so that all rows can be selected.

   ```X++
   static void Vts2_SelectVtsJob10(Args _args)
    {
        TabEmplProjVts xEP;
        date dateFrom, dateTo;
        str strTemp;
    
        // Specify the largest possible date range
        // so that all ValidFrom value qualify.
        // Here 1\1\1900 is not treated as null by validTimeState().
        dateFrom = 01\01\1900;
        dateTo   = 31\12\2154;
    
        Global::info("Will display rows, if any exist.");
    
        While SELECT
            validTimeState(dateFrom, dateTo)
            * from xEP
            order by xEP.EmplID, xEP.ProjID, xEP.ValidFrom
        {
            strTemp = xEP.EmplID
                + " , " + xEP.ProjID
                + " ;  " + date2str(xEP.ValidFrom, 321, 2,3,2,3,4)
                + " -- " + date2str(xEP.ValidTo, 321, 2,3,2,3,4)
                + " ;  " + xEP.EPPrimaryKey
                + " ;  " + xEP.AssocColor
                + " ;  " + xEP.AssocFruit;
            info(strTemp);
        }
    }
    /*** Pasted from the output:
    Message (03:19:55 pm)
    Will display rows, if any exist.
    em21 , pr44 ;  2000-01-01 -- 2003-12-31 ;  key61 ;  Red ;  Apple
    em21 , pr44 ;  2004-01-01 -- 2039-12-31 ;  key62 ;  Orange ;  Banana
    em22 , pr44 ;  2001-01-01 -- 2005-12-31 ;  key63 ;  Yellow ;  Cherry
    em22 , pr44 ;  2009-01-01 -- 2038-12-31 ;  key64 ;  Green ;  Fig
    em22 , pr45 ;  1910-02-13 -- 1924-03-14 ;  key65 ;  Blue ;  Grape
    em22 , pr45 ;  1936-05-16 -- 1948-06-17 ;  key66 ;  Indigo ;  Lemon
    em22 , pr45 ;  2111-07-18 -- 2119-08-19 ;  key67 ;  Violet ;  Melon
    ***/
   ```

The output from the preceding X++ job Select has two rows that begin with the values em21 , pr44. Notice that the date ranges of these two rows make one larger uninterrupted range. However, the two rows for em22 , pr44 have a gap between their two date ranges. This gap is allowed, because the **ValidTimeStateMode** property is set to **Gap** on the idxEPAltKeyVts index.

## Select Rows for Specific Effective Dates

Run the following code to issue X++ SQL select statements for subsets of rows.

The select statement has the option to include the validTimeState keyword, and to pass in one or two date parameters. This code example includes a select that has only one parameter passed in to validTimeState. In this case, only those rows are returned which contain that date parameter value within their own date range.

Another select in the example omits the validTimeState keyword. This is equivalent to including validTimeState with one target date parameter whose value is equal to today().

   ```X++
   static void Vts2_SelectVtsJob40(Args _args)
    {
        TabEmplProjVts xEP;
        date dateTarget;
        str strTemp;
    
    
        dateTarget = 22\7\2002;
        Global::info("Select rows for EXplicit PAST target date = "
            + date2str(dateTarget, 321, 2,3,2,3,4)
            );
        While SELECT
            validTimeState(dateTarget)
            * from xEP
            order by xEP.EPPrimaryKey
        {
            strTemp = "For target "
                + date2str(dateTarget, 321, 2,3,2,3,4)
                + " :  " + xEP.EmplID
                + " , " + xEP.ProjID
                + " ;  " + date2str(xEP.ValidFrom, 321, 2,3,2,3,4)
                + " -- " + date2str(xEP.ValidTo, 321, 2,3,2,3,4)
                + " ;  " + xEP.EPPrimaryKey
                + " ;  " + xEP.AssocColor
                + " ;  " + xEP.AssocFruit;
            info(strTemp);
        }
    
    
        info("");
        dateTarget = today();
        Global::info("Select rows for EXplicit CURRENT system date = "
            + date2str(today(), 321, 2,3,2,3,4)
            );
        xEP = null;
        While SELECT
            validTimeState(dateTarget)
            * from xEP
            order by xEP.EPPrimaryKey
        {
            strTemp = "For target "
                + date2str(today(), 321, 2,3,2,3,4)
                + " :  " + xEP.EmplID
                + " , " + xEP.ProjID
                + " ;  " + date2str(xEP.ValidFrom, 321, 2,3,2,3,4)
                + " -- " + date2str(xEP.ValidTo, 321, 2,3,2,3,4)
                + " ;  " + xEP.EPPrimaryKey
                + " ;  " + xEP.AssocColor
                + " ;  " + xEP.AssocFruit;
            info(strTemp);
        }
    
        
        info("");
        Global::info("Select rows for IMplicit CURRENT system date.");
        xEP = null;
        While SELECT
            // DEFAULT , validTimeState(dateTarget)
            * from xEP
            order by xEP.EPPrimaryKey
        {
            strTemp = "For target "
                + date2str(today(), 321, 2,3,2,3,4)
                + " :  " + xEP.EmplID
                + " , " + xEP.ProjID
                + " ;  " + date2str(xEP.ValidFrom, 321, 2,3,2,3,4)
                + " -- " + date2str(xEP.ValidTo, 321, 2,3,2,3,4)
                + " ;  " + xEP.EPPrimaryKey
                + " ;  " + xEP.AssocColor
                + " ;  " + xEP.AssocFruit;
            info(strTemp);
        }
    }
    /** Pasted from the output:
    Message (05:58:31 pm)
    Select rows for EXplicit PAST target date = 2002-07-22
    For target 2002-07-22 :  em21 , pr44 ;  2000-01-01 -- 2003-12-31 ;  key61 ;  Red ;  Apple
    For target 2002-07-22 :  em22 , pr44 ;  2001-01-01 -- 2005-12-31 ;  key63 ;  Yellow ;  Cherry
    
    Select rows for EXplicit CURRENT system date = 2012-07-17
    For target 2012-07-17 :  em21 , pr44 ;  2004-01-01 -- 2039-12-31 ;  key62 ;  Orange ;  Banana
    For target 2012-07-17 :  em22 , pr44 ;  2009-01-01 -- 2038-12-31 ;  key64 ;  Green ;  Fig
    
    Select rows for IMplicit CURRENT system date.
    For target 2012-07-17 :  em21 , pr44 ;  2004-01-01 -- 2039-12-31 ;  key62 ;  Orange ;  Banana
    For target 2012-07-17 :  em22 , pr44 ;  2009-01-01 -- 2038-12-31 ;  key64 ;  Green ;  Fig
    **/
   ```

Consider the output of the Select statements from the preceding code example. Notice that, within each subset of returned rows, all the date ranges include the date that is specified in the validTimeState keyword. Also, no rows that have em22 , pr45 are returned, because the specified dates fall in the gap between the date ranges for those rows.

### ![Gg843767.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg843767.collapse_all(en-us,AX.60).gif")Other Read Operations Affected by Valid Time State

**Views:** The views under **AOT** \> **Data Dictionary** \> **Views** have a property named **ValidTimeStateEnabled**. This property controls whether reads from the view retrieve only the current records. The values are as follows:

  - **No** – Read operations from the view retrieve records, regardless of their ValidFrom-ValidTo range. **No** is the default.

  - **Yes** – Read operations from the view retrieve only the current records. This matches the behavior of reads from the table.

**Query class:** Instances of the Query class have a method named ValidTimeStateAsOfDate and other similar methods. The ValidTimeStateAsOfDate method is equivalent to the validTimeState(targetDate) keyword syntax in the X++ SQL select statement. For more information, see [How to: Use the Query Class to Read From a Valid Time State Table](how-to-use-the-query-class-to-read-from-a-valid-time-state-table.md).

## Update

The code example in this section demonstrates a variety of ways to update table records.

One way to update records is with the xRecord.update method after an X++ SQL select for update statement. Except for the system fields ValidFrom and ValidTo, the xRecord.update statement is unaffected by whether a table has implement the valid time state feature. However, the select statement is affected by valid time state. By default, it can only retrieve records which have a ValidFrom-ValidTo range that includes the current date.

Another way to update records is with the X++ SQL update\_recordset statement. This statement is unaffected by valid time state, except when a ValidFrom or ValidTo field is being updated. The X++ SQL delete\_from statement is also unaffected by valid time state.

The code example in this section performs three updates, as described in the following table.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>ID of update</p></th>
<th><p>Discussion</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>// Update A: ValidTo</p></td>
<td><p>On the select for update statement, the validTimeState keyword is given date parameters for the maximum date range possible. Therefore, all records are available for retrieval by the select statement, not just the records for the current day.</p>
<p>For record key61, the ValidTo field is updated to a date that is within the date range for the sister record, key62.</p>
<p>The output shows that the system automatically updates the ValidFrom field of record key62 to eliminate the overlap. This particular outcome is controlled by the following line of code:</p>
<p>xEP.ValidTimeStateUpdateMode (ValidTimeStateUpdate::Correction);</p></td>
</tr>
<tr class="even">
<td><p>// Update B: AssocColor</p></td>
<td><p>On the select for update statement, the validTimeState keyword is given the current date. Therefore, only records which include the current date in their ValidFrom-ValidTo range are available for retrieval by the select statement. Only record key61 is selected.</p>
<p>For record key61, the AssocColor field is updated to Brown.</p></td>
</tr>
<tr class="odd">
<td><p>// Update C: AssocFruit</p></td>
<td><p>This uses the X++ SQL keyword update_recordset. This mode of update is unaffected by valid time state considerations, unless a ValidFrom or ValidTo field is updated. In the present example, only the AssocFruit field is updated.</p>
<p>There is nothing in the where clause of this update_recordset to prevent all records from having their AssocFruit field set to Peach. So all records are set to Peach.</p></td>
</tr>
</tbody>
</table>


   ```X++
    static void Vts2_UpdateVtsJob54(Args _args)
    {
        TabEmplProjVts xEP;
        date dateToday,
            dateFrom,
            DateTo;
        str 10 strEmplID,
            strProjID,
            strEPPrimaryKey;
        int iCountRows_BeforeDelete;
    
        dateToday = today();
        dateFrom = 1\1\1900;
        dateTo = 31\12\2154;
    
    
        // This pair of values identifies two records, where
        // alternate keys different only by ValidFrom-ValidTo.
        // One of the two records is the current record.
        strEmplID       = "em21";
        strProjID       = "pr44";
    
        // Identifies exactly one of the two records that
        // are identified by the em21 && pr44 value pair.
        strEPPrimaryKey = "key61";
    
    
        // '::Correction' is the default.
        // The alternative is '::CreateNewTimePeriod' (or '::EffectiveBase').
        xEP.ValidTimeStateUpdateMode (ValidTimeStateUpdate::Correction);
    
    
        // Update A:  ValidTo
        ttsBegin;
        while
        SELECT
            forUpdate
            // This Select finds ZERO records if this
            // next keyword, 'validTimeState', is omitted.
            validTimeState(dateFrom, dateTo) // Maximum date range, includes all.
            * from xEP
            where xEP.EPPrimaryKey == strEPPrimaryKey
                && xEP.ValidTo != 22\1\2033
        {
            xEP.ValidTo = 22\1\2033; // Changes this record into the current record.
            xEP.update();
            info("Update to ValidTo was needed, and was performed.");
        }
        ttsCommit;
    
    
        // Update B:  AssocColor
        ttsBegin;
        while
        SELECT
            forUpdate
            // This Select finds ONE record regardless of
            // whether this next keyword, 'validTimeState', is omitted.
            validTimeState(dateToday) // Single date, indicates the current record, the default.
            * from xEP
            where xEP.EmplID == strEmplID
                && xEP.ProjID == strProjID
                && xEP.AssocColor != "Brown"
        {
            xEP.AssocColor = "Brown";
            xEP.update();
            info("Update to AssocColor was needed, and was performed.");
        }
        ttsCommit;
    
        
        // Update C:  AssocFruit
        // Set the fruit for ALL records, not just current records.
        // Valid time state aspect is irrelevant to update_recordset,
        // unless ValidFrom or ValidTo is updated.
        update_recordSet xEP setting AssocFruit = "Peach"
            where xEP.AssocFruit != "Peach";
        info("Update_RecordSet to Peach is done, for ALL records.");
    
        info("Update job has reached its end.");
    }
    /***
    Message (03:37:55 pm)
    Update to ValidTo was needed, and was performed.
    Update to AssocColor was needed, and was performed.
    Update_RecordSet to Peach is done, for ALL records.
    Update job has reached its end.
    ***/
   ```

### ![Gg843767.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg843767.collapse_all(en-us,AX.60).gif")Select of Updated Records Shows That ValidFrom Was Automatically Modified

To see the updated records, you can rerun the X++ code for Vts2\_SelectVtsJob10. The expected output is shown next.

Notice that the ValidFrom value for record key62 was updated by the system and immediately follows the ValidTo value of the key61 record that the code example explicitly updated.

  
 Message (03:45:51 pm)   
 Will display rows, if any exist.   
 em21 , pr44 ; 2000-01-01 -- 2033-01-22 ; key61 ; Brown ; Peach   
 em21 , pr44 ; 2033-01-23 -- 2039-12-31 ; key62 ; Orange ; Peach   
 em22 , pr44 ; 2001-01-01 -- 2005-12-31 ; key63 ; Yellow ; Peach   
 em22 , pr44 ; 2009-01-01 -- 2038-12-31 ; key64 ; Green ; Peach   
 em22 , pr45 ; 1910-02-13 -- 1924-03-14 ; key65 ; Blue ; Peach   
 em22 , pr45 ; 1936-05-16 -- 1948-06-17 ; key66 ; Indigo ; Peach   
 em22 , pr45 ; 2111-07-18 -- 2119-08-19 ; key67 ; Violet ; Peach   

### ![Gg843767.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg843767.collapse_all(en-us,AX.60).gif")The ValidTimeStateUpdate Enum

Each table has the ValidTimeStateUpdateMode property. The value of the property is an element of the ValidTimeStateUpdate enum. The value affects only what happens when an update occurs to a ValidFrom or ValidTo field.

The names and meanings of the ValidTimeStateUpdate enum elements are as follows:

  - Correction – The ValidFrom or ValidTo values of existing rows must be modified to keep the date-effective data valid after the update\_recordset statement is completed.

  - CreateNewTimePeriod – A new record is inserted into the table to maintain the validity of the date-effective data after the update\_recordset statement is completed.

  - EffectiveBased – Forces the update process to switch to CreateNewTimePeriod for each row that spans the current date-time; otherwise, it forces the update process to switch to Correction.

## See also

[Valid Time State Tables and Date Effective Data](valid-time-state-tables-and-date-effective-data.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

