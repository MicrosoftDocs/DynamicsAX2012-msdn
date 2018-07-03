---
title: Operators for CLR Primitive Types
TOCTitle: Operators for CLR Primitive Types
ms:assetid: 0a9f44d8-a82c-4a13-9d38-d1285d16e85c
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc581728(v=AX.60)
ms:contentKeyID: 35240354
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Operators for CLR Primitive Types 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

In X++, when you work with .NET common language runtime (CLR) primitive data types, you can use the equal sign (=) assignment operator. However, no other operators can be used between two CLR primitives. For instance, you cannot use the comparison operators, such as == or \>. Also, you cannot use bitwise operators, such as & or |.

You cannot use a comparison operator with CLR primitive or value types because they are represented as reference types or objects in the system. A System.Int32 is an object that is converted to a value type temporarily during assignment statements. A System.Int32 remains a reference type when it is used with a comparison operator. Comparison operators such as \>= are designed for use between value types.

## Code Sample

The following code sample shows that the X++ operator \>= cannot be used meaningfully between two System.Int32 variables. The sample also shows that the .NET Framework has methods that provide the functionality of the comparison operators. The method System.Int32.CompareTo is shown.

```X++
    static void JobOperatorsForNet(Args _args)
    {
        System.Int32 netInt99
            ,netInt8;
        int xppCompare;
        ;
        netInt99 = 99;
        netInt8 = 8;
    
        // Attempt with the >= operator.
    
        if (netInt99 >= netInt8)
        {
            info("Unexpected.");
        }
        else
        {
            info("This proves the X++ >= operator cannot be used"
                + " meaningfully between two .NET Int32 variables.");
        }
    
        // System.Int32.CompareTo method.
    
        xppCompare = netInt99.CompareTo(netInt8);
        if (0 < xppCompare)
        {
            info(strfmt(
                "xppCompare is %1, which means 99 > 8.  Good."
                , xppCompare));
        }
        else if (0 == xppCompare)
        {
            info(strfmt(
                "xppCompare is %1, which means 99 == 8.  Unexpected."
                , xppCompare));
        }
        else // (0 > xppCompare)
        {
            info(strfmt(
            "xppCompare is %1, which means 99 < 8.  Unexpected."
            , xppCompare));
        }
    
    /***** Output
    Message (11:50:53 am)
    This proves the X++ >= operator cannot be used
      meaningfully between two .NET Int32 variables.
    xppCompare is 1, which means 99 > 8.  Good.
    *****/
    }
```

## See also

[.NET Interop from X++](net-interop-from-x.md)

[Null Values for Data Types](null-values-for-data-types.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

