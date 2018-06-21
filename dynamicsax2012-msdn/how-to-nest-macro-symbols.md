---
title: 'How to: Nest Macro Symbols'
TOCTitle: 'How to: Nest Macro Symbols'
ms:assetid: 115f0928-b716-4650-97d1-70cb455cfa8f
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc197109(v=AX.60)
ms:contentKeyID: 35240554
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Nest Macro Symbols [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

You can nest precompiler definition directives inside an outer definition directive. The main definition directives are \#define and \#localmacro.

The cases for which this topic provides code samples are as follows:

  - Transitive Substitution in X++ – A \#define macro can have the symbol for another macro as its value. Transitive substitution of the symbol occurs in X++ code.

  - No Transitive Substitution in Directives – An \#if directive test of a macro value does not perform substitutions.

  - Macro Within a Macro – A \#define directive can be given inside a \#localmacro directive, or a \#localmacro can be inside a \#define.

## Prerequisites

For this topic, you must understand the information in [How to: Use the \#localmacro and \#globalmacro Directives](how-to-use-the-sharplocalmacro-and-sharpglobalmacro-directives.md).

## Transitive Substitution in X++

In the following code sample, the value of the first \#define variable includes a symbol (\#D) of the second \#define variable. This works even though the expansion symbol \#D occurs before macro D is defined.

    static void NestMacroJobA1(Args _args)
    {
        ;
        #define.Cd("Cd +: # D == " + #D)
    
        // If not commented out, this next code line would cause the
        // error message "The macro does not exist.", because
        // #D in the value of #Cd cannot be expanded before it is defined.
        //info(#Cd);
    
        #define.D("D")
        info(#Cd);
    
    /************  Actual Infolog output
    Message (10:42:13 am)
    Cd +: # D == D
    ************/
    }

## No Transitive Substitution in Directives

This section shows where a macro symbol substitution is attempted in the value of another macro.

### ![Cc197109.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc197109.collapse_all(en-us,AX.60).gif")No Transitive Substitution in \#if Directives

The following code sample tries to determine whether two macro variables have the same value, without specifying what that value might be. The output shows that this determination cannot be made..

    static void NestMacroJobA2(Args _args)
    {
        ;
        #define.A1(5)
        #define.A2(5)
    
        info("Status: A1==" + int2Str(#A1) + " , A2==" + int2Str(#A2));
    
        #if.A1(#A2)
            info("Yes, symbol substitution does work on # IF test.  Unexpected.");
        #endif
    
        #ifNOT.A1(#A2)
            info("No, symbol substitution does not work on # IF test.");
        #endif
    
    /************  Actual Infolog output
    Message (11:27:38 am)
    Status: A1==5 , A2==5
    No, symbol substitution does not work on # IF test.
    ************/
    }

### ![Cc197109.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc197109.collapse_all(en-us,AX.60).gif")No Transitive Substitution in \#defInc Directives

The following code sample shows that the \#defInc directive does not lead to transitive substitution of symbol values. For more information about the \#defInc directive, see [How to: Use the \#defInc and \#defDec Directives](how-to-use-the-sharpdefinc-and-sharpdefdec-directives.md).

After the \#defInc.E2 directive, the subsequent output value for \#E2 shows the value for E2 is converted to zero (0) by \#defInc.E2 before it is incremented to one (1). Before the conversion, the value of E2 was the three characters \#E2. The output for test case 36 shows the value has been converted to 1.

    static void NestMacroJobA4(Args _args)
    {
        ;
        #define.E1(5)
        #define.E2(#E1)
    
        info("11:  # E1 == " + int2Str(#E1));
        info("12:  # E2 == " + int2Str(#E2));
    
        #defInc.E1
        info(" -------");
    
        info("23: After Inc.E1,  # E1 == " + int2Str(#E1));
        info("24: After Inc.E1,  # E2 == " + int2Str(#E2));
    
        #defInc.E2
        info(" -------");
    
        info("35: After Inc.E2,  # E1 == " + int2Str(#E1));
        info("36: After Inc.E2,  # E2 == " + int2Str(#E2));
    
    /************  Actual Infolog output
    Message (02:39:41 pm)
    11:  # E1 == 5
    12:  # E2 == 5
     -------
    23: After Inc.E1,  # E1 == 6
    24: After Inc.E1,  # E2 == 6
     -------
    35: After Inc.E2,  # E1 == 6
    36: After Inc.E2,  # E2 == 1
    ************/
    }

## Macro Within a Macro

A \#define directive can be given inside a \#localmacro directive, and a \#localmacro can be inside a \#define. This is shown in the following code sample.

    static void NestMacroJobB5(Args _args)
    {
        int iTest = 31;
        ;
        //-------------  J  ---------------
        #localmacro.LocMacOuterJL
            #define.DefinInnerJD(5)
        #endmacro
    
        #LocMacOuterJL
        info("J: Directive nesting works if 5 appears: # DefinInnerJD == "
                + int2Str(#DefinInnerJD));
    
        //-------------  K  ---------------
        #define.DefinOuterKD(#localmacro.LocMacInnerKL ++iTest; #endmacro)
        ++iTest; // Result is 32.
        #DefinOuterKD
        #LocMacInnerKL
        info("K: Directive nesting works if 33 appears: iTest == "
                + int2Str(iTest));
    
    /**************  Actual Infolog output
    Message (11:21:02 am)
    J: Directive nesting works if 5 appears: # DefinInnerJD == 5
    K: Directive nesting works if 33 appears: iTest == 33
    **************/
    }

## See also

[Macros in X++](macros-in-x.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

