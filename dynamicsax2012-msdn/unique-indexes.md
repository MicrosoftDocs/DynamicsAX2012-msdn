---
title: Unique Indexes
TOCTitle: Unique Indexes
ms:assetid: ec66c909-34f2-45ce-9b75-6af64aa10f6e
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa884122(v=AX.60)
ms:contentKeyID: 35253236
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Unique Indexes 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

This topic describes the best practices related to unique indexes.

## Unique Indexes and RecID

If a table is not given a unique index (because there is no key in the application), the system will create a unique index to get a key. The index will consist of the fields in the shortest index definition, measured in bytes, appended with the RecId.

You can make any index unique by appending the RecId to the index.

Create an index on RecId only if you need it. For example, if the RecId field is used for lookup operations. A best practice warning appears if you create an index on RecId![Warning icon](images/Aa658028.WarningIcon(en-us,AX.60).gif "Warning icon") without using RecId for any explicit lookup operation. A best practice warning appears if RecId is used for a lookup when no index has been created on RecId.![Warning icon](images/Aa658028.WarningIcon(en-us,AX.60).gif "Warning icon")

If needed, create a unique index by setting the CreateRecIdIndex property to Yes. The default is to set it to No, to save disk space and insert/update time. 

## Adding or Changing Unique Indexes

If you add a new unique index to a table, or change an existing one, it will cause problems for users when they upgrade to a new version of Microsoft Dynamics AX. This will cause a best practice error. ![Error icon](images/Aa872655.ErrorIcon(AX.60).gif "Error icon")

This error can be fixed by implementing an upgrade script called AllowDup TablenameIndexname, or DeleteDup TablenameIndexname as a pre-synchronization upgrade job. For example, if the new unique index on MyTable is called NewUniqueIndex, the script should be called AllowDupMyTableNewUniqueIndex or DeleteDupMyTableNewUniqueIndex.

### ![Aa884122.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa884122.collapse_all(en-us,AX.60).gif")"AllowDup" scripts

Use this to temporarily disable the unique index. When you have removed conflicting fields, you need to run an upgrade script to re-enable the unique index.

"AllowDup" scripts should contain the following code.

    {
    DictIndex  dictIndex = new DictIndex(
        tablenum(TableName),
        indexnum(TableName, IndexName));
        ;
    
        ReleaseUpdateDB::indexAllowDup(dictIndex);
    }

### ![Aa884122.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa884122.collapse_all(en-us,AX.60).gif")"DeleteDup" scripts

Use this to delete all conflicting fields.

"DeleteDup" scripts should contain the following code.

    {
        ;
        ReleaseUpdateDB::deleteDuplicatesUsingIds(
            tablenum(TableName),
            fieldnum(TableName, UniqueIndexField));
    }

## See also

[Best Practices for Indexes](best-practices-for-indexes.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

