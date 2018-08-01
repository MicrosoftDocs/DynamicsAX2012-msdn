---
title: 'How to: Test a Macro Value'
TOCTitle: 'How to: Test a Macro Value'
ms:assetid: 660df237-5f28-493d-ac08-418dc4e182a4
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc197115(v=AX.60)
ms:contentKeyID: 35244689
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Test a Macro Value [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

You can test a macro to see whether it has a value. You can also test to see whether its value is equal to a specific sequence of characters. These tests enable you to conditionally include lines of code in your X++ program.

## Prerequisites

For this topic, you must understand the information in [How to: Use a Macro Value](how-to-use-a-macro-value.md).

## Testing Whether a Macro has a Value

There is no way you can test whether a defined macro has a value. You can only test whether a specific value matches the value of a macro.


> [!TIP]
> <P>Any macro name that you define should always have a value, or it should never have a value. When you alternate between these modes, your code becomes difficult to understand. For macros that have a value, you can vary the value when you see fit.</P>



In the following code sample, two \#if tests are run to determine whether the macro MyIntMacro exists. The \#if.MyIntMacro() test is true. This syntax behaves the same as \#if.MyIntMacro.
```X++  
    static void TestMacroValue6Job(Args _args)
    {
        ;
        #define.MyIntMacro(66)
    
        // #if tests.
    
        #if.MyIntMacro()
            info("A: " + int2str(#MyIntMacro));
        #endif
    
        #if.MyIntMacro(66)
            info("B: " + int2str(#MyIntMacro));
        #endif
    
        // #ifNOT tests.
    
        #ifNOT.MyIntMacro(7777)
            info("C: " + int2str(#MyIntMacro));
        #endif
    
        #ifNOT.No_Such_Macro_Name(66)
            info("D: " + int2str(#MyIntMacro));
        #endif
    
    /****************  Actual output
    Message (11:24:47 am)
    A: 66
    B: 66
    C: 66
    D: 66
    ****************/
    }
```
## Testing a Macro Value for Equality

The following code sample shows the \#if.DebugMacro(heavy) directive that tests the value of the DebugMacro macro. If the value is the five character sequence heavy, then the test is true.
```X++  
    static void TestMacroSpecificValue8Job(Args _args)
    {
        ;
        // Uncomment either one of these defines, or neither.
        //#define.DebugMacro(light) // This line for: light debugging.
        #define.DebugMacro(heavy) // This line for: heavy debugging.
    
        #if.DebugMacro
            info("Starting the job.");
        #endif
    
        #if.DebugMacro(heavy)
            info("UTC == "
                + DateTimeUtil ::toStr
                    (DateTimeUtil::utcNow()
                    )
                );
        #endif
    
        // Do something useful here.
    
    /**********  Actual output
    Message (01:58:12 pm)
    Starting the job.
    UTC == 2007-12-05T21:58:12
    **********/
    }
```
## See also

[Macros in X++](macros-in-x.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

