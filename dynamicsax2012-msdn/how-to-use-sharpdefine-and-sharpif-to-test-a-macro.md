---
title: 'How to: Use #define and #if to Test a Macro'
TOCTitle: 'How to: Use #define and #if to Test a Macro'
ms:assetid: 968bd331-30d3-4d67-83df-fd408a2feb12
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc197117(v=AX.60)
ms:contentKeyID: 35247637
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Use \#define and \#if to Test a Macro [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

A macro is a variable known to the precompiler. The variable can have a value that is a sequence of characters, but it is not required to have a value. The \#define directive tells the precompiler to create the macro variable, including an optional value. The \#if directive tests whether the variable is defined, and optionally, whether it has a specific value.

The value of a macro variable can be written into the X++ code at any location, by giving the name of the macro with the \# character added as a prefix.

All precompiler directives and symbols begin with the \# character. All of the directives and symbols are handled and removed before the resulting X++ code is given to the X++ compiler.

## Defining and Testing a Macro

In the following code sample, a macro named MyMacro is defined. It is not given a value in the \#define.MyMacro definition line. Therefore it behaves as if the value is a zero-length sequence of characters.

The \#if.MyMacro statement tests whether MyMacro is defined. Because MyMacro is defined, the lines of code before the first \#endif are included in the X++ code at the test location.

Near the end of the X++ code there is an \#ifnot.MyMacro test. Because MyMacro is defined, that test is false and no lines are written into the X++ code.

After the precompile phase ends for this job, the MyMacro definition goes out of scope and is no longer known to the system.

### ![Cc197117.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc197117.collapse_all(en-us,AX.60).gif")Code Sample

    static void SimpleDefineIfJob(Args _args)
    {
        str sTest = "Initial value.";
        ;
        #define.MyMacro // MyMacro is now defined.
    
        #if.MyMacro
            sTest = "Yes, MyMacro is defined.";
            info(sTest);
        #endif
    
        // Notice the non-code sentence line causes no X++ compiler error,
        // because the X++ compiler never sees it.
        #ifnot.MyMacro
            The X++ compiler would reject this sentence.
            sTest = "No, MyMacro is not defined.";
            info(sTest);
        #endif
    
    /********** Actual output
    Message (03:46:20 pm)
    Yes, MyMacro is defined.
    **********/
    }

## See also

[Macros in X++](macros-in-x.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

