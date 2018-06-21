---
title: Using Optional Parameters
TOCTitle: Using Optional Parameters
ms:assetid: 321a02a8-9862-448e-aa1a-bec8b5b9d138
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa635503(v=AX.60)
ms:contentKeyID: 35241989
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Using Optional Parameters [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

It is possible to initialize parameters in the method declaration. This makes the parameter an optional parameter. If no value is supplied in the method call, the default value is used.

## Code Example 1: Function used as the Default

The following methods are considered to be members of the MyClass1 class, which includes the field member birthDate.

    public class MyClass1  // classDeclaration
    {
        date birthDate;
    }

Next, the class contains a constructor that takes a date type as a parameter. That value is assigned to the field member birthDate.

    void new(date _date)
    {
        birthDate = _date;
    }

Next is the CalculateAgeAsOfDate method, for which the following are true:

  - The method references the birthDate field.

  - The method has an optional parameter. In this example, the default value is the return value of a function.

  - The method is called by the Main method.

<!-- end list -->

    public real CalculateAgeAsOfDate  // X++
            ( date _calcToDate = today() )  // Parameter is optional for callers.
    {
        return (_calcToDate - birthDate) / 365;
    }

Next is the Main method which calls the CalculateAgeAsOfDate method twice.

    static public void Main(Args _args)
    {
        MyClass1 mc = new MyClass1(13\5\2010);   // birthDate is initialized.
    
        // Optional parameter's default is used.
        print "Age in years: " + num2str(mc.CalculateAgeAsOfDate(),2,0,0,0);
    
        // January 2, 2044  is the parameter value for _date.
        print "Age in years: " + num2str(mc.CalculateAgeAsOfDate(2\1\2044),2,0,0,0);
    
        pause;
    }

## Code Example 2: Invalid Sequence of Parameters

All required parameters must be listed before the first optional parameter. In the following invalid example, the required parameter \_i3 is listed after the optional parameter \_i2.

    static public int AddThreeIntsA  // Invalid X++, does not compile.
            (int _i1,
             int _i2 = 3,
             int _i3)  // Required parameter cannot follow an optional parameter.
    {
        return _i1 + _i2 + _i3;
    }

## Code Example 3: Cannot Skip to Second Optional Parameter

When calling a method, the caller cannot override the default value of the final optional parameter unless the caller also overrides the default values of every other optional parameter.

In the following example, the first method has two optional parameters. The second method is a caller of the first method. The caller wants to override only the \_i3 default value, but the compiler requires that all prior optional parameters also be overridden in the call.

    static public int AddThreeIntsB
            (int _i1,
             int _i2 = 2,
             int _i3 = 3)
    {
        return _i1 + _i2 + _i3;
    }

Next, the second method has a commented section showing the failed attempt to accept the default of the first optional parameter \_i2 while trying to override the final optional parameter \_i3.

    static public void Main(Args _args)
    { 
        // No way to skip the first optional parameter (so it can default)
        // while also specifying the value of the second optional parameter.
        //
        //print MyClass1::AddThreeIntsB(1, , 99);  // Would fail to compile in X++.
    
    
        // Settle for overriding both optional parameters.
        //
        print MyClass1::AddThreeIntsB(1, 2, 99);
        pause;
    }

## See also

[Declaration of Methods](declaration-of-methods.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

