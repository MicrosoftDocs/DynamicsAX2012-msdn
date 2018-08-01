---
title: RunBase Framework
TOCTitle: RunBase Framework
ms:assetid: bfe9d616-9db5-431f-a5f4-9f42d1d1b1ae
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa863262(v=AX.60)
ms:contentKeyID: 35250076
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# RunBase Framework [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The RunBase framework provides a standardized approach to creating processes and batch jobs in Microsoft Dynamics AX. The framework must be used for every job-style function in the application.

The framework is implemented by the RunBase application class and supplies many features, which include the following:

  - Query

  - Dialog, with persistence of the last values entered by the user

  - Validate

  - Batch execution for users to schedule jobs. This functionality uses the [RunBaseBatch](https://msdn.microsoft.com/en-us/library/gg822687\(v=ax.60\)) class) and the pack and unpack methods with versioning.

  - Progress bar

  - Run

  - Client/server-optimized

Following are descriptions of some of the most important RunBase methods.

## new Method

Always call super() in the new method.

The new method must not be too slow for your needs (it is periodically called for administrative purposes).

## description Method

You must create a static description method that returns a class description—the class's role in the UI.

The description method must have the RunAs property set to Called or the equivalent behavior. If the class is defined as client or server, define the method as client server.

For example:

client server static ClassDescription description()

{

return "@SYS54106";

}

## run Method

The RunBase.run method is the central method of the class. The job is done in the run method.

Skeleton:

```X++
    void run()
    {
        // Local declarations.
        try
        {
            this.progressInit
            ttsBegin;
            // Reset the variables that were changed in the transaction.
            ...
            // Do the job.
            while select forUpdate myTrans...
            {
                progress.incCount();
                progress.setText
                ...
                ...
            ttsCommit;
        }
        catch (Exception::Deadlock)
        {
            retry;
        }
    }
```

## pack and unpack Methods

For information about the pack and unpack methods, see the [pack-unpack design pattern](pack-unpack-design-pattern.md).

## RunBaseReport.initQuery Method

Place code that modifies the RunBase query in the [RunBaseReport.initQuery](https://msdn.microsoft.com/en-us/library/gg823055\(v=ax.60\)) method. The [RunBaseReport.initQueryRun](https://msdn.microsoft.com/en-us/library/gg823056\(v=ax.60\)) method calls initQuery.

If the query in a RunbaseReport depends on values from the dialog, call this.initQueryRun after the data is moved from the fields to the variables.

### ![Aa863262.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa863262.collapse_all(en-us,AX.60).gif")Example

```X++
private boolean getFromDialog()
{
    ;
    perDate = dialogDate.value();
    this.initQueryRun();
    return super();
}
 
```

The initQueryRun method in the previous code calls initQuery.

```X++
    private Query initQuery()
    {
        query query = super();
        queryBuildRange qbr;
        ;
        qbr = query.dataSourceTable(
            tableNum(InventTrans)).findRange(
                fieldNum(InventTrans,DatePhysical));
        if (!qbr)
        {
            qbr = query.dataSourceTable(
                tableNum(InventTrans)).addRange(
                    fieldNum(InventTrans,DatePhysical));
        }
        qbr.value(SySQuery::range(prevYr(PerDate),PerDate));
        qbr = query.dataSourceTable(
            tableNum(InventTrans)).findRange(
                fieldNum(InventTrans,DateFinancial));
        if (!qbr)
        {
            qbr = query.dataSourceTable(
                tableNum(InventTrans)).addRange(
                    fieldNum(InventTrans,dateFinancial));
        }
        qbr.value(SysQuery::value(perDate+1) 
        + '..' + ',' + sysQuery::valueEmptyString());
        return query;
    }
```

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

