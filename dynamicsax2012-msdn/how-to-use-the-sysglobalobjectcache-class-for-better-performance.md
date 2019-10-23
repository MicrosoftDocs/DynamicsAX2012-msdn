---
title: 'How to: Use the SysGlobalObjectCache Class for Better Performance'
TOCTitle: 'How to: Use the SysGlobalObjectCache Class for Better Performance'
ms:assetid: 5da40ac1-02e8-4708-a99d-ff661a903e89
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh608239(v=AX.60)
ms:contentKeyID: 39555628
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Use the SysGlobalObjectCache Class for Better Performance 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

You can use the SysGlobalObjectCache system class to improve the performance of database access. An instance of the SysGlobalObjectCache class provides access to the system global object cache. Access to the global cache improves performance in scenarios where the same record is retrieved repeatedly. In comparison, repeated X++ SQL select statements to retrieve the same record from the database are inefficient and are a burden to the Application Object Server (AOS).

A SysGlobalObjectCache object that is running in the AOS uses the same cache that is shared by all client sessions that are connected to that AOS.

Every record that is inserted into SysGlobalObjectCache is shared across multiple sessions that are in the same process. If an entry is inserted on the AOS, then all the sessions on the same AOS have access to the entry in the cache. However, any cache entries inserted on the AOS will not be automatically sent to the clients connected to that AOS. The entries will also not be sent to another AOS that is part of the deployment.

If an entry is inserted on the client, the client session has access to the cache and the entry is also sent to the AOS. In this case, any sessions connected to the AOS can also find the same entry in the cache on the AOS.

We recommended that any code that searches for an entry in the cache should always handle the case where the cache entry might not be present in the cache. This is demonstrated in the following code sample. The code calls find, and if the entry is not found, it inserts the entry into the cache. Since multiple sessions share the same cache, there is no guarantee that the cache will have the entry, even if the session had inserted an entry in the cache.

Note that the cache is partitioned. This means that an entry that is inserted in a particular partition cannot be accessed from other partitions.

Do not use SysGlobalObjectCache for values that are table buffers, the tables have the **CacheLookup** property set to **EntireTable**.


> [!NOTE]
> <P>Do not confuse the SysGlobalObjectCache object with the SysGlobalCache object. Instances of the SysGlobalCache class have access to a cache that is dedicated to one client session only.</P>



## Maintenance of the Cache

The Microsoft Dynamics AX system does not automatically remove outdated data from the system global object cache. Instead, your application code must perform maintenance operations on the cache. This is one reason why use of the cache is appropriate only for data that is rarely updated.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Method</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>clear</p></td>
<td><p>An instance method that clears the cache for one scope.</p></td>
</tr>
<tr class="even">
<td><p>clearAllCaches</p></td>
<td><p>A static method that clears the entire cache for all scopes.</p></td>
</tr>
<tr class="odd">
<td><p>remove</p></td>
<td><p>An instance method that removes one key within one scope. The value associated with the key is also removed.</p></td>
</tr>
</tbody>
</table>


### ![Hh608239.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Hh608239.collapse_all(en-us,AX.60).gif")Least Recently Used

The system global object cache has a maximum size that you can configure. For information about how to configure client and server cache sizes, see [Single-record Caching](single-record-caching.md).

When the cache is full and another item is inserted, the least recently used (LRU) item in the cache is erased from the cache.

## Scopes within the Cache

The system global object cache can be used to store many types of data concurrently. The cache might hold data about physical installations per state or other geographic region. Concurrently the cache might also hold data about commerce laws in those same regions. There is a risk that the keys from these two data domains might accidentally match, causing a data error.

The solution is for your organization to use well planned values for the scope parameter of the insert method of the SysGlobalObjectCache class:

public void insert(   
     GlobalObjectCacheScope  scope,   
     container               key,   
     container               value)

Two inserts of the same key value do not affect each other if they are associated to different scope values. All operations on individual cached keys are partitioned by scope.

### ![Hh608239.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Hh608239.collapse_all(en-us,AX.60).gif")Technique for Subscope Groups

You can design the keys of cache items to informally partition items within a single scope. The key for an item in the system global object cache is a container. All of the following are keys are valid and unique, but the second bullet shows two keys that are informally grouped together in a subscope that is named CommerceLaw:

  - \[2\] and \[5\]

  - \["CommerceLaw",2\] and \["CommerceLaw",5\]

In the preceding list, the key \["CommerceLaw",5\] is a container with two elements. Keys are limited to a maximum of five items. Also, keys cannot contain other containers or table buffers. The container for a value parameter is not subject to these limitations.

The clear method can operate on one scope, but it cannot operate on just one subscope group such as "CommerceLaw".

## Scenario

Suppose that many clients are concurrently active in the Microsoft Dynamics AX installation. Several clients must access the data records for the most active customers. The X++ SQL select statements from these clients contain where clause criteria that test a field on a table. The criteria narrow the count of returned records to either zero or one. Various clients are repeatedly selecting the same records for the most active customers.

In this scenario, a best practice is for each client to obtain the record for a customer from the cache. If the cache returns the record, processing continues as normal. But if the cache does not have the customer record, the code should issue the X++ SQL select statement to obtain the record, and then add the record to the cache. Finally, continue as normal.

## Code Example

The following X++ method constructs an object from the SysGlobalObjectCache class. The object has access to the cache. The method asks the object for the customer record. If the object cannot return the record, the method queries the database for the record, and then asks the object to add the record to the cache.
```X++  
    // X++ method, in class AaaTestSysGlobalObjectCache.
    public CustBankAccountId getCustBankAccountId
            (CustAccount _edtCustAccount,               // EDT
            GlobalObjectCacheScope _sScopeTestCache3Job // EDT
            )
    {
            // Tables.
        // This test table named MyCustTable has its property
        // CacheLookup = None, and it has no indexes on its
        // fields AccountNum and BankAccount.
        MyCustTable tabMyCustTable;
            // Classes.
        SysGlobalObjectCache sgoc2;
            // Extended Data Types.
        CustBankAccountId edtCustBankAccountId;
            // Primitives.
        container cnResult;
        str sCacheGroup = "_edtCustAccount";
    
        sgoc2 = new SysGlobalObjectCache();
    
        cnResult = sgoc2.find
            (  _sScopeTestCache3Job,  // Scope.
               [
                    sCacheGroup,  // Group, freeform string which names the group within the cache.
                    _edtCustAccount           // Key.
               ]  // X++ syntax for a container, [ ].
            );
    
        if ( cnResult == conNull() )
        {
            info(strFmt("Key not found in cache: %1", _edtCustAccount));
    
            // Object not found in the cache, so get the object by the
            // usual X++ SQL means.  Then insert the object into the cache.
            //
            SELECT BankAccount
                from tabMyCustTable
                where
                    tabMyCustTable.AccountNum == _edtCustAccount;
    
            edtCustBankAccountId = tabMyCustTable.BankAccount;
            cnResult = [ edtCustBankAccountId ];
    
            sgoc2.insert
                (  _sScopeTestCache3Job,
                   [
                        sCacheGroup,
                        _edtCustAccount
                   ],
                   cnResult  // Value, corresponding to the given Key & Group.
                );
        }
        else    // Key is found in the cache, and is in the cnResult container.
        {
            info(strFmt("Key is found in cache!: %1", _edtCustAccount));
            
            edtCustBankAccountId = conPeek(cnResult, 1);
        }
    
        return edtCustBankAccountId;
    }
    // For testing, see the following job TestCache3Job.
```
### ![Hh608239.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Hh608239.collapse_all(en-us,AX.60).gif")X++ Job to Run the Test

The following X++ job calls the previous method. The second call with the parameter value 1102 is satisfied by the cache.
```X++  
    static void TestCache3Job(Args _args) // X++ job.
    {
            // Classes.
        SysGlobalObjectCache sgoc2;
        AaaTestSysGlobalObjectCache aaaTest;
            // Extended Data Types.
        GlobalObjectCacheScope sTestCache3Job = "sTestCache3Job";
        CustBankAccountId edtCustBankAccountId;
            // Primitives.
        container cnResult;
    
    
        sgoc2 = new SysGlobalObjectCache();
        sgoc2.clear(sTestCache3Job);
        
        aaaTest = new AaaTestSysGlobalObjectCache();
    
    
        edtCustBankAccountId = aaaTest.getCustBankAccountId("1102", sTestCache3Job);
        info(strFmt("A, Key == 1102, Value == : %1 %2", edtCustBankAccountId, "\r\n"));
    
        edtCustBankAccountId = aaaTest.getCustBankAccountId("0000", sTestCache3Job);
        info(strFmt("B, Key == 0000, Value == : %1 %2", edtCustBankAccountId, "\r\n"));
    
        edtCustBankAccountId = aaaTest.getCustBankAccountId("1102", sTestCache3Job);
        info(strFmt("C, Key == 1102, Value == : %1 %2", edtCustBankAccountId, "\r\n"));
    
    
        sgoc2.clear(sTestCache3Job);
    }
    /*****  Infolog display.
    Message (05:07:57 pm)
    
    Key not found in cache: 1102
    A, Key == 1102, Value == : 1234 a 
    
    Key not found in cache: 0000
    B, Key == 0000, Value == :  
    
    Key is found in cache!: 1102
    C, Key == 1102, Value == : 1234 a 
    *****/
```
## See also

[SysGlobalObjectCache](https://msdn.microsoft.com/en-us/library/gg926679\(v=ax.60\))

[SysGlobalCache](https://msdn.microsoft.com/en-us/library/gg929594\(v=ax.60\))

[Using Global Variables](using-global-variables.md)

[Set-based Caching](set-based-caching.md)

[Manipulation of Data in Tables](manipulation-of-data-in-tables.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

