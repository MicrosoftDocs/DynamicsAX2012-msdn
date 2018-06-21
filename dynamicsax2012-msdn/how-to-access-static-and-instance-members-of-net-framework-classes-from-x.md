---
title: 'How to: Access Static and Instance Members of .NET Framework Classes from X++'
TOCTitle: 'How to: Access Static and Instance Members of .NET Framework Classes from X++'
ms:assetid: e863724b-9187-4703-b119-4e327a9498d1
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc641200(v=AX.60)
ms:contentKeyID: 35253226
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Access Static and Instance Members of .NET Framework Classes from X++ [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

In Microsoft Dynamics AX, the X++ syntax for calling .NET Framework methods is different for calling static methods than it is for calling instance methods. In both cases, the dot character (.) is used to delimit all the namespaces of the fully qualified type name. However, for calling static .NET Framework methods, you must use a double colon (::) between the class name and the method name. This is consistent with the double colon that you use when you call static methods that are written in X++.


> [!WARNING]
> <P>Starting in Microsoft Dynamics AX 2012 you rarely need to include a semicolon before the first statement in your X++ methods. However, you need the semi-colon in X++ methods that call static methods in the .NET Framework.</P>



## Sample of Static and Instance Method Calls into .NET

In the following X++ code sample, the static and instance method calls are as follows:

  - Static: System.Convert::ToString

  - Instance: netString.Substring

<!-- end list -->

    static void JobStaticInstanceSyntax95(Args _args)
    {
        System.Int32 netInt;
        System.String netString;
        str xppString;
        ;
        netInt = 123456;
    
        // static
        netString = System.Convert::ToString(netInt);
    
        // instance
        netString = netString.Substring(3,2);
    
        xppString = netString;
        info(xppString);
    
    /***** Actual infolog output
    Message (05:58:20 am)
    45
    *****/
    }

## See also

[.NET Interop from X++](net-interop-from-x.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

