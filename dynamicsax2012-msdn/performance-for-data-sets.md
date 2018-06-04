---
title: Performance for Data Sets
TOCTitle: Performance for Data Sets
ms:assetid: 53699483-d8b3-43c9-b181-3267384bc81c
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc570815(v=AX.60)
ms:contentKeyID: 35245330
ms.date: 11/07/2012
mtps_version: v=AX.60
---

# Performance for Data Sets 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

When using data sets to work with data for Enterprise Portal, you should watch for situations that could affect the performance of your Enterprise Portal application.

## Insert Operation Performance

When a data set is used to insert a new row into a data source, all the rows for the data source are retrieved before the new row is inserted. If the table for the data source contains many rows, this can significantly affect performance.

## Improving Insert Operation Performance

To improve the performance of the insert operation for a data set, add an init method to each data source for the data set. Code in this method will control the range of rows the data source is accessing.

The init method must detect when an insert operation is being performed. If one is, a query should be applied that restricts the rows that are read from the table for the data source. When the insert operation occurs, the performance will not be affected because no rows are retrieved.

For Enterprise Portal, the action being performed is specified by a parameter passed on the URL for the page that is performing the action. The [EPFormAction Enumeration](https://msdn.microsoft.com/en-us/library/gg864534\(v=ax.60\)) defines the actions that can be performed. You will use this parameter to find whether an insert operation is being performed.

To find the action being performed, add a definition for the formAction variable to the class declaration for your data set.

    public class DataSetRun extends ObjectRun
    {
        EPFormAction formAction;
    }

In the init method for the data set, add code that retrieves the value that specifies the action that is being performed. The following example shows how to do this.

    public void init()
    {
        super();
        
         // Retrieve the action that is being performed.
        if (this.args().parmEnumType() == enumnum(EPFormAction))
            formAction = this.args().parmEnum();
        
    }

In the init method for the data source in the data set, add code that examines the action being performed. If it is an insert action, a range should be applied. The following example examines the formAction class variable to find what action is being performed. If an insert action is being performed, a range is applied that will limit the records accessed.

    public void init()
    {
        QueryBuildRange rangeRecId;
        #define.invalidRecId(0)
    
        super();
    
        if(formAction == EPFormAction::CreateMode)
        {
            // To improve performance, add a range that accesses no rows.
            rangeRecId = this.query().dataSourceTable(tablenum(RCMRooms)).addRange(fieldnum(FCMRooms, RecId));
            rangeRecId.value(SysQuery::value(#invalidRecId));
            rangeRecId.status(RangeStatus::Hidden);
        }
    }

## See also

[Passing Parameters to Pages](passing-parameters-to-pages.md)

