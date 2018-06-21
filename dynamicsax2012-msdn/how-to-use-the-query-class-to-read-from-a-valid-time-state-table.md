---
title: 'How to: Use the Query Class to Read From a Valid Time State Table'
TOCTitle: 'How to: Use the Query Class to Read From a Valid Time State Table'
ms:assetid: 1b2b9398-64a4-4c75-aeee-b38269427b2e
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg844050(v=AX.60)
ms:contentKeyID: 35241411
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Use the Query Class to Read From a Valid Time State Table [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

You can use the Query class to read rows from a valid time state table. Methods such as validTimeStateDateRange enable this functionality.

For more information about valid time state tables, see [Valid Time State Tables and Date Effective Data](valid-time-state-tables-and-date-effective-data.md).

## Valid Time State Methods on the Query Class

 The following methods on the [Query](https://msdn.microsoft.com/en-us/library/gg913387\(v=ax.60\)) class enable you to read from a valid time state table. These methods give you the same control that the validTimeState [keyword](x-keywords.md) gives to you in an X++ select statement:

  - validTimeStateAsOfDate

  - validTimeStateAsOfDateTime

  - validTimeStateDateRange

  - validTimeStateDateTimeRange

## Code Example

The following code example uses the Query class to read all of the rows from a valid time state table. Pay attention to the validTimeStateDateRange method.

If you want to run the following code example, you must first run the code examples in the topic [Effects of Valid Time State Tables on Read and Write Operations](effects-of-valid-time-state-tables-on-read-and-write-operations.md).

    static void QueryVtsJob60(Args _args)  // X++ job, under AOT > Jobs.
    {
        TabEmplProjVts xEP;
        Query qry;
        QueryRun qRun;
        QueryBuildDataSource qBDSource;
        str sDisplay;
        int iTableNumEP = tableNum(TabEmplProjVts);
        date dateMinimum = 1\1\1900,
            dateMaximum = 31\12\2154;
        
        qry = new Query();
        qry.validTimeStateDateRange(dateMinimum, dateMaximum);
        qBDSource = qry.addDataSource(iTableNumEP);
        qBDSource.addOrderByField(fieldNum(TabEmplProjVts, EmplID));
        qBDSource.addOrderByField(fieldNum(TabEmplProjVts, ProjID));
        qBDSource.addOrderByField(fieldNum(TabEmplProjVts, ValidFrom));
        qRun = new QueryRun(qry);
    
        while (qRun.next())
        {
            xEP = qRun.get(iTableNumEP);
            sDisplay = xEP.EmplID
                + " , " + xEP.ProjID
                // Or use the enums DateFormat, DateDay, DateMonth
                // and DateYear for parameter values into date2str.
                + " .  " + date2str(xEP.ValidFrom, 321, 2,3,2,3,4)
                + " -- " + date2str(xEP.ValidTo, 321, 2,3,2,3,4)
                + " .  " + xEP.EPPrimaryKey;
            Global::info(sDisplay);
        }
    }

### ![Gg844050.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg844050.collapse_all(en-us,AX.60).gif")Infolog Display

In the following output, you can see that the retrieved rows include a variety of date ranges, even for the same pairs of employee plus project. The varied date ranges displayed in the output indicate that the validTimeStateDateRange method did override the default of the current system date. For instance, no single date can retrieve the rows that have key61 and key62.

Message (02:31:03 pm)   
 em21 , pr44 . 2000-01-01 -- 2003-12-31 . key61   
 em21 , pr44 . 2004-01-01 -- 2039-12-31 . key62   
 em22 , pr44 . 2001-01-01 -- 2005-12-31 . key63   
 em22 , pr44 . 2009-01-01 -- 2038-12-31 . key64   
 em22 , pr45 . 1910-02-13 -- 1924-03-14 . key65   
 em22 , pr45 . 1936-05-16 -- 1948-06-17 . key66   
 em22 , pr45 . 2111-07-18 -- 2119-08-19 . key67

## See also

[Queries in the AOT for Data Access](queries-in-the-aot-for-data-access.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

