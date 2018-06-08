---
title: 'How to: Use the #localmacro and #globalmacro Directives'
TOCTitle: 'How to: Use the #localmacro and #globalmacro Directives'
ms:assetid: 254777bf-e1b0-4e26-98f4-9dd5908470b4
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc197110(v=AX.60)
ms:contentKeyID: 35241669
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Use the \#localmacro and \#globalmacro Directives 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The \#localmacro directive is a good choice when you want a macro to have a value that is several lines long, or when your macro value contains a closing parenthesis. The \#localmacro directive is a good choice when you want your macro value to be lines of X++ or SQL code.


> [!NOTE]
> <P>The #localmacro directive can be written as #macro. However, #localmacro is the recommended term. Both macros have the same behavior.</P>



## Prerequisites

For this topic, you must understand the information in [How to: Use Parameters with Macros](how-to-use-parameters-with-macros.md).

## Using \#localmacro

The following code sample shows how to use the \#localmacro directive. It demonstrates that the \#undef directive does not affect \#localmacro macros. It also shows that \#if tests cannot determine whether a \#localmacro macro has been defined.

    static void LocalMacroJob(Args _args)
    {
        ;
        #localmacro.LMacReportLog
            print("%1  --LM, print.");
            info("%1  --LM, Infolog.");
        #endmacro
    
        #LMacReportLog(g11: Hello World )
    
        #if.LMacReportLog
            info("The # IF LMacReportLog is true");
        #endif
    
        #undef.LMacReportLog
    
        #LMacReportLog(g22: Greetings World)
    
        #localmacro.LMacReportLog
        #endmacro // No lines for value before this end.
    
        #LMacReportLog(g33: Bye Bye) // Not present in the output.
        pause;
    
    /*************  Actual Infolog output
    Message (03:10:17 pm)
    g11: Hello World   --LM, Infolog.
    g22: Greetings World  --LM, Infolog.
    *************/
    }

## Differences Between \#define and \#localmacro

There are differences between \#define and \#localmacro.

### ![Cc197110.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc197110.collapse_all(en-us,AX.60).gif")Termination Syntax

The main difference between a \#define macro and a \#localmacro macro is in how their syntax is terminated. The terminators are as follows:

  - \#define – is terminated by– )

  - \#localmacro – is terminated by– \#endmacro

\#localmacro is a better choice for macros with multiple line values. Multiple line values are typically lines of X++ or SQL code. X++ and SQL contain lots of parentheses, and these would prematurely terminate a \#define.

Both \#define and \#localmacro can be declared and terminated on either a single line or on subsequent lines. In practice, the \#define is terminated on the same line that it is declared on. In practice, the \#localmacro is terminated on a subsequent line.

### ![Cc197110.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc197110.collapse_all(en-us,AX.60).gif")\#if and \#undef Do Not Apply to \#localmacro

By using the \#if directive, you can test whether a macro name is declared with the \#define directive. However, you cannot test whether the macro name is declared with the \#localmacro directive.

Only macros declared by using the \#define directive are affected by the \#undef directive.

### ![Cc197110.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc197110.collapse_all(en-us,AX.60).gif")Redefining a \#localmacro By Using \#define

In a \#define directive, you can specify a name that is already in scope as a \#localmacro. The effect is to discard the \#localmacro and create a \#define macro.

This also applies to the opposite sequence, which means that a \#localmacro can redefine a \#define.

## Avoid Using \#globalmacro

A \#localmacro (that has both a macro name and a value) always overrides a previous \#localmacro that has the same name. However, you cannot always be sure whether the override occurs when you use \#globalmacro. For this reason we recommend that you do not use \#globalmacro.

This same problem occurs with [\#globaldefine](how-to-use-the-sharpglobaldefine-directive-to-avoid-overwriting.md).

### ![Cc197110.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc197110.collapse_all(en-us,AX.60).gif")Code Sample Comparing \#globalmacro and \#localmacro

The following X++ code sample shows that \#localmacro overrides a \#globalmacro of the same macro name, but that \#globalmacro does not override \#localmacro.

    static void GlobalMacroNotOverrideJob(Args _args)
    {
        ;
        //---------  LGMa ,  L then G  ---------
    
        #localmacro.LGMa
            info("LGMa: Loc 11");
        #endmacro
    
        #globalmacro.LGMa
            info("LGMa: Glob 12");
        #endmacro
    
        #LGMa
    
        //---------  LGMb ,  G then L  ---------
    
        #globalmacro.LGMb
            info("LGMb: Glob 24");
        #endmacro
    
        #localmacro.LGMb
            info("LGMb: Loc 25");
        #endmacro
    
        #LGMb
    
    /****************  Actual Infolog output
    Message (06:39:42 am)
    LGMa: Loc 11
    LGMb: Loc 25
    ****************/
    }

### ![Cc197110.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc197110.collapse_all(en-us,AX.60).gif")No Special Precedence Between Macro and Define Directives

Where both macro names and values are supplied, the \#globalmacro directive cannot override the \#define directive. Also, the \#globaldefine directive cannot override the \#localmacro directive.

## See also

[Macros in X++](macros-in-x.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

