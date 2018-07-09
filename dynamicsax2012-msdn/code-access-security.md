---
title: Code Access Security
TOCTitle: Code Access Security
ms:assetid: 09299e91-5b73-4cf5-a17e-f1f39b6bae76
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Bb190039(v=AX.60)
ms:contentKeyID: 35240335
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Code Access Security 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Code Access Security (CAS) helps protect APIs that have potential security risks when the APIs are running on the server.

CAS-enabled APIs called on the server require the use of a permission class—one of the classes derived from CodeAccessPermission. If permission to use the API is not asserted, the following error is generated:

Request for the permission of type '%1' failed.

This error is also generated if permission is asserted, but the code is running on the client. Permission is required only for CAS-enabled APIs that run on the server. The string supplied in the error message is the name of one of the following permission classes:

  - ExecutePermission

  - FileIoPermission

  - InteropPermission

  - RunAsPermission

  - SkipAOSValidationPermission

  - SqlDataDictionaryPermission

  - SqlStatementExecutePermission

  - SysDatabaseLogPermission

For a list of CAS-enabled APIs, see [Secured APIs](secured-apis.md).

You can CAS-enable your own APIs. For more information, see [How to: Secure an API on the AOS](how-to-secure-an-api-on-the-aos.md).

## Call a CAS-enabled API

1.  Declare a variable for the relevant permission class.

2.  Create a new instance of the class.

3.  Request permission by using the assert method on the permission class.

4.  Revert the assertion (to limit the scope of the permission) after the CAS-enabled API has been used; optional. Permission is automatically reverted when the method finishes executing.

### ![Bb190039.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Bb190039.collapse_all(en-us,AX.60).gif")Example

```X++
    {
        DictClass dictClass;
        anytype   retVal;
        str       resultOutput;
        // Variable for the permission class.
        ExecutePermission perm;
        ;
        
        perm = new ExecutePermission();
     
        // Grants permission to execute the DictClass.callObject method.
        // DictClass.callObject is protected by code access security.
        perm.assert();
     
        dictClass = new DictClass(classidget(infolog));
        if (dictClass != null)
        {
            retVal       = dictClass.callObject("toString", infolog);
            resultOutput = strfmt("Return value is %1", retVal);
            print resultOutput;
            pause;
        }
        
        // Closes the code access permission scope.
        CodeAccessPermission::revertAssert();
    }
```

## See also

[CodeAccessPermission Class](https://msdn.microsoft.com/en-us/library/gg803417\(v=ax.60\))

[ExecutePermission Class](https://msdn.microsoft.com/en-us/library/gg839532\(v=ax.60\))

[FileIOPermission Class](https://msdn.microsoft.com/en-us/library/gg839563\(v=ax.60\))

[InteropPermission Class](https://msdn.microsoft.com/en-us/library/gg921452\(v=ax.60\))

[RunAsPermission Class](https://msdn.microsoft.com/en-us/library/gg926091\(v=ax.60\))

[SkipAOSValidationPermission Class](https://msdn.microsoft.com/en-us/library/gg957747\(v=ax.60\))

[SqlDataDictionaryPermission Class](https://msdn.microsoft.com/en-us/library/gg947234\(v=ax.60\))

[SqlStatementExecutePermission Class](https://msdn.microsoft.com/en-us/library/gg947244\(v=ax.60\))

[SysDatabaseLogPermission Class](https://msdn.microsoft.com/en-us/library/gg945593\(v=ax.60\))

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

