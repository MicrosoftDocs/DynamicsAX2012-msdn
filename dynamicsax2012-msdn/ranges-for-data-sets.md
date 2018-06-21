---
title: Ranges for Data Sets
TOCTitle: Ranges for Data Sets
ms:assetid: a24ad8b0-0f59-4ced-a091-3695158949a6
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc634424(v=AX.60)
ms:contentKeyID: 35245559
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Ranges for Data Sets [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

A data set, typically used to access data for Enterprise Portal, can have one or more data sources from which data is accessed. You can use X++ code to add a range that restricts the data that is accessed by the data source. The code that adds the range must be written correctly so that only the data in the range is accessed.

## Adding a Range

To add a range for the data source that is used by a data set, you must override the init method for the data source. In this method, create a QueryBuildRange object that defines the range and specifies the values allowed. To prevent the range from being changed or removed, set the range status to hidden. This last step is very important to prevent data outside the range from being accessed.

The following example sets a range for the ContactPerson data source in the EPCustTableInfo data set. The range prevents rows from being accessed that have empty values in the ContactPerson or CustAccount fields. The status of the range is set to hidden to make sure that the range cannot be changed or deleted.

    public void init()
    {
        QueryBuildRange    rangeCustAccount;
        super();
    
        rangeCustAccount = this.query().dataSourceTable(tablenum(ContactPerson)).addRange(fieldnum(ContactPerson, CustAccount));
        rangeCustAccount.value(SysQuery::valueNotEmptyString());
        rangeCustAccount.status(RangeStatus::Hidden);
    }

## See also

[Data Access Overview](data-access-overview.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

