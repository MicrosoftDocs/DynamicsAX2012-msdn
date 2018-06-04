---
title: Cross-Company Data Modification Using X++
TOCTitle: Cross-Company Data Modification Using X++
ms:assetid: ad8c30ee-9871-4a0e-bd62-f369dc88f5a7
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc617093(v=AX.60)
ms:contentKeyID: 35249724
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Cross-Company Data Modification Using X++ 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

You can use a while select crossCompany statement for cross-company data modification. You may need to use this statement because you cannot use the crossCompany keyword in X++ SQL statements that modify data nor can you use sub-select commands embedded in data modification statements. You can issue a while select crossCompany statement first, and then use the populated table buffer to drive data modification commands. The changeCompany keyword is a central part of this technique.

## Data Modification Options

In X++, you can modify data with either SQL statements or with methods on a table buffer. The SQL statements are best for modifying a set of rows with one command. The methods are used to modify one row per call.

The SQL data modification statements are:

  - delete\_from

  - insert\_recordset

  - update\_recordset

The data modification methods on a table buffer variable are inherited from the xRecord class. These methods are:

  - delete

  - insert

  - update

All of these options can be used in cross-company data modification processing.

## delete\_from Command

In X++ code, you can delete data on a cross-company basis, even though you cannot use the crossCompany keyword on the delete\_from statement. The following code example shows one way you can do this.

    static void JobCCDel( Args _args )
    {
        Table21 tab21a , tab21b;
        ;
        ttsBegin;
        while select
            crossCompany
                minof( ratingNum )
                , dataAreaId
            from
                tab21a
            group by
                dataAreaId
        {
            changeCompany( tab21a .dataAreaId )
            {
                tab21b = null;
                delete_from tab21b
                    where tab21b .ratingNum == tab21a .ratingNum;
            }
        }
        ttsCommit;
    }

## insert Method

The following X++ code example shows how to use the cross-company feature for inserting data, even though the crossCompany keyword cannot be used on the insert\_recordset command.

    static void JobCCIns( Args _args )
    {
        Table21 tab21;
        Table22 tab22;
        ;
        ttsBegin;
        while select
            crossCompany
                actionDate , name , dataAreaId
            from
                tab21
            where
                tab21 .actionDate > str2Date( '1998-01-22' , 321 )
        {
            changeCompany( tab21 .dataAreaId )
            {
                tab22 = null;
                tab22 .actionDate = tab21 .actionDate;
                tab22 .name = tab21 .name;
                tab22 .insert();
            }
        }
        ttsCommit;
    }

## update\_recordset with forUpdate on select

This X++ example uses the forUpdate keyword on the while select crossCompany statement. Only one table buffer variable is declared. This example also uses the update method on the table buffer.

    static void JobCCForUpdMethod( Args _args )
    {
        Table21 tab21;
        ;
        ttsBegin;
        while select
            forUpdate crossCompany
                countOfReviews
            from
                tab21
        {
            changeCompany( tab21 .dataAreaId )
            {
                tab21 .countOfReviews = tab21 .countOfReviews + 2;
                tab21 .update();
            }
        }
        ttsCommit;
    }

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

