---
title: 'How to: Secure an API on the AOS'
TOCTitle: 'How to: Secure an API on the AOS'
ms:assetid: 3b9b815d-56a4-44b3-b2f7-0880dfad7571
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa625357(v=AX.60)
ms:contentKeyID: 35242914
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Secure an API on the AOS [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

In Microsoft Dynamics AX, you can make an API more secure by extending the [CodeAccessPermission Class](https://msdn.microsoft.com/en-us/library/gg803417\(v=ax.60\)). A class that is derived from the CodeAccessPermission class determines whether code accessing an API is trusted by checking for the appropriate permission. This topic describes how to implement the CodeAccessPermission class for APIs that must run on the Application Object Server (AOS).

You should secure an API that executes on the AOS because it has the potential to be exploited maliciously. Malicious code running in a shared server environment can cause extensive damage.

To secure an API, you must call the assert method in the derived class prior to invoking the API. Otherwise, an exception is thrown. For information, see [Secured APIs](secured-apis.md) and [Code Access Security](code-access-security.md).

### To secure an API on the AOS

1.  Derive a class that cannot be extended from the CodeAccessPermission class.
    
    \-or-
    
    Use one of the following derived classes that ship with Microsoft Dynamics AX and skip to step 6.
    
      - [ExecutePermission Class](https://msdn.microsoft.com/en-us/library/gg839532\(v=ax.60\))
    
      - [FileIOPermission Class](https://msdn.microsoft.com/en-us/library/gg839563\(v=ax.60\))
    
      - [InteropPermission Class](https://msdn.microsoft.com/en-us/library/gg921452\(v=ax.60\))
    
      - [RunAsPermission Class](https://msdn.microsoft.com/en-us/library/gg926091\(v=ax.60\))
    
      - [SkipAOSValidationPermission Class](https://msdn.microsoft.com/en-us/library/gg957747\(v=ax.60\))
    
      - [SqlDataDictionaryPermission Class](https://msdn.microsoft.com/en-us/library/gg947234\(v=ax.60\))
    
      - [SqlStatementExecutePermission Class](https://msdn.microsoft.com/en-us/library/gg947244\(v=ax.60\))
    
      - [SysDatabaseLogPermission Class](https://msdn.microsoft.com/en-us/library/gg945593\(v=ax.60\))

2.  Create a method that returns the class parameters. For more information, see [Accessor Methods](accessor-methods.md).

3.  Create a constructor for all of the class parameters that store permission data.

4.  To determine whether the permissions required to invoke the API that you are securing exist, override the [CodeAccessPermission.isSubsetOf](https://msdn.microsoft.com/en-us/library/gg803424\(v=ax.60\)) method to compare the derived permission class to CodeAccessPermission. The following code example shows how to override the [CodeAccessPermission.isSubsetOf Method](https://msdn.microsoft.com/en-us/library/gg803424\(v=ax.60\)) to determine whether permissions stored in the current object exist in \_target.
    
        public boolean isSubsetOf(CodeAccessPermission _target)
        {
            SysTestCodeAccessPermission sysTarget = _target;
            return this.handle() == _target.handle();
        }

5.  Override the [CodeAccessPermission.copy](https://msdn.microsoft.com/en-us/library/gg803415\(v=ax.60\)) method to return a copy of an instance of the class created in step 1. This helps to prevent the class object from being modified and passed to the API being secured.

6.  Call the [CodeAccessPermission.demand](https://msdn.microsoft.com/en-us/library/gg803416\(v=ax.60\)) method before executing the API functionality that you are securing. The method checks the call stack to determine whether the permission required to invoke the API has been granted to the calling code.

## See also

[Exception Handling with try and catch Keywords](exception-handling-with-try-and-catch-keywords.md)

[Code Access Security](code-access-security.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

