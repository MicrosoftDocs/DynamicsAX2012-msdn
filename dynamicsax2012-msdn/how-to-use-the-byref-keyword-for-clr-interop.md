---
title: 'How to: Use the byref Keyword for CLR Interop'
TOCTitle: 'How to: Use the byref Keyword for CLR Interop'
ms:assetid: 8e10a325-401f-4e17-b910-0be0afeade16
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc603944(v=AX.60)
ms:contentKeyID: 35246463
ms.date: 05/18/2015
mtps_version: v=AX.60
dev_langs:
- csharp
---

# How to: Use the byref Keyword for CLR Interop 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

In X++, you use the byref keyword when you call a .NET Framework method that takes parameters by reference.

For more information about how the byref keyword works with value types and reference types, see [Understanding the X++ Keyword byref for CLR Interop](understanding-the-x-keyword-byref-for-clr-interop.md).

## Code Samples

The following C\# and X++ code samples work together to show when and how to use the byref keyword.


> [!NOTE]
> <P>For information about establishing a reference in Microsoft Dynamics AX for an assembly DLL you compile from C#, see <A href="how-to-compile-and-run-x-that-calls-clr-managed-assemblies.md">How to: Compile and Run X++ that Calls CLR Managed Assemblies</A>.</P>



### ![Cc603944.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc603944.collapse_all(en-us,AX.60).gif")C\# Called Method

The following C\# code sample shows a method that takes parameters by reference. Note the C\# keywords ref and out, which both mean pass by reference.

``` csharp
using System;
namespace DotNetNamespace {
public class DotNetClass {

static public void CalledCSharp // Method.
        (
        int iLengthOfOldPrefix         // by value
        ,string sWhole                 // by value
        ,ref string sNewPrefixPlusName // by reference
        ,out string sDiscardedPrefix   // by reference
        )
{
    sNewPrefixPlusName = sNewPrefixPlusName
        + sWhole.Substring(iLengthOfOldPrefix);
    sDiscardedPrefix = sWhole.Substring
        (0, iLengthOfOldPrefix);
}}}
```

### ![Cc603944.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc603944.collapse_all(en-us,AX.60).gif")X++ Caller Job

The following X++ code sample shows how to use the byref keyword to call the example C\# method CalledCSharp.

    static void JobByrefCallerXpp(Args _args)
    {
        int iLengthOfOldPrefix;
        str sWhole;
        str sNewPrefix;
    
        str sNewPrefixPlusName
            ,sDiscardedPrefix;
        ;
    
        iLengthOfOldPrefix = 5; // 'Foods' is 5 characters.
        sWhole = "Foods: triangle, square, circle.";
        sNewPrefix = "Shapes";
    
        sNewPrefixPlusName = sNewPrefix;
    
        DotNetNamespace.DotNetClass::CalledCSharp
            (
            iLengthOfOldPrefix
            ,sWhole
            ,byref sNewPrefixPlusName
            ,byref sDiscardedPrefix
            );
    
        info("sNewPrefixPlusName = " + sNewPrefixPlusName);
        info("sDiscardedPrefix = " + sDiscardedPrefix);
    
    /*****  Infolog actual output.
    Message (07:24:21 pm)
    sNewPrefixPlusName = Shapes: triangle, square, circle.
    sDiscardedPrefix = Foods
    *****/
    }

## See also

[.NET Interop from X++](net-interop-from-x.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

