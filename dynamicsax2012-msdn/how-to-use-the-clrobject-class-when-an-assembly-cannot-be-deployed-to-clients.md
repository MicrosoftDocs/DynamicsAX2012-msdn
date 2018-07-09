---
title: 'How to: Use the CLRObject Class when an Assembly cannot be Deployed to Clients'
TOCTitle: 'How to: Use the CLRObject Class when an Assembly cannot be Deployed to Clients'
ms:assetid: 70b933e8-dda9-4a71-9c8d-ef02fa16cb72
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh538480(v=AX.60)
ms:contentKeyID: 39508913
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Use the CLRObject Class when an Assembly cannot be Deployed to Clients 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

You can use the CLRObject system class of Microsoft Dynamics AX when your X++ code must call .NET Framework assemblies that are not available on your local development computer.

The syntax for using the CLRObject class is standard for X++. However, the X++ compiler treats the CLRObject class as a late-bound mechanism. The X++ compiler does not check to see whether objects of type CLRObject truly have methods by the names used in your code. Instead, name checking occurs later during run time. This enables you to write X++ code that calls classes that are in assemblies which the compiler cannot access.

Your company might have a license agreement that restricts installation of a third party assembly to only the Application Object Server (AOS) hard drive. The CLRObject class can be useful in such situations, but only if the X++ code is configured to run on the server only. For more information about how to ensure your X++ code runs on the AOS and not on the client, see [Application Object RunOn Property Overview](application-object-runon-property-overview.md).

## CLRObject Code Example

The following code example is an X++ job that shows the technique for using the CLRObject class.
```X++  
    static void ClrObjectXppJob(Args _args)
    {
        str sExcepMesg;
        CLRObject clrObj2;
    
        clrObj2 = new CLRObject(
            "System.ApplicationException",
            "Testing CLRObject 52." // This one parameter matches a constructor signature.
            );
        sExcepMesg = clrObj2.get_Message(); // Calls the Message property by its CIL name.
        
        info(sExcepMesg);
    }
    /*** Infolog display
    Message (03:02:07 pm)
    Testing CLRObject 52.
    ***/
```
## See also

[CLRObject Class](https://msdn.microsoft.com/en-us/library/gg803404\(v=ax.60\))

[Deployment Overview of .NET Assemblies for Interop](deployment-overview-of-net-assemblies-for-interop.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

