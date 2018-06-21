---
title: 'How to: Use the #macrolib Directive for AOT Macro Libraries'
TOCTitle: 'How to: Use the #macrolib Directive for AOT Macro Libraries'
ms:assetid: 25dbc19c-8ac1-4b3c-af9b-6d50a5dbf692
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc197112(v=AX.60)
ms:contentKeyID: 35241675
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Use the \#macrolib Directive for AOT Macro Libraries [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

In the Application Object Tree (AOT) under the **Macros** node, there are many library nodes that contain sets of macro directives. Both \#define and \#localmacro often appear in the contents of these macro libraries.

You can use the \#macrolib.MyAOTMacroLibrary to include the contents of an AOT macro library in your X++ code.


> [!NOTE]
> <P>The directive #macrolib.MyAOTMacroLibrary can also be written as #MyAOTMacroLibrary. The #macrolib prefix is recommended because it is never ambiguous to a person who later reads the code.</P>



## Prerequisites

For this topic, you must understand the information in [How to: Use the \#localmacro and \#globalmacro Directives](how-to-use-the-sharplocalmacro-and-sharpglobalmacro-directives.md).

## Using a System Provided Macro Library from the AOT

Microsoft Dynamics AX has an AOT macro library that is named **Event**. This macro library contains the directive \#define.DefaultEventPollFrequency(15). The following code sample shows that the \#macrolib.Event directive makes the macro \#DefaultEventPollFrequency available.

    static void SystemProvidedMacroLibraryJob(Args _args)
    {
        ;
        #macrolib.Event // Contains: #define.DefaultEventPollFrequency(15)
    
        info("# DefaultEventPollFrequency == "
                + int2str(#DefaultEventPollFrequency));
    
    /***************  Actual Infolog output
    Message (06:31:26 pm)
    # DefaultEventPollFrequency == 15
    ***************/
    }

## \#if and \#undef Do Not Apply to \#macrolib

The \#if and \#undef directives do not apply to \#macrolib names. However, they do apply to \#define directives that are the contents of a \#macrolib macro.

## Precedence Between \#macrolib and \#define When the Same Name is Used

The following code example shows what happens when you write a \#define for a name that is already the name of a node in the AOT under **Macros**. For this example, the AOT has a node under Macros that is named MacLib23, and its contents are one \#define as follows:

    #define.DefinInMacLib23("_This is inside AOT macrolib MacLib23.")

After a \#macrolib directive is issued for MacLib23, \#define and \#undef directives have no effect on the \#macrolib macro (see output \_BB). However, a \#define in the contents of a \#macrolib macro can be overwritten by a subsequent \#define or \#undef in the code (see output \_DD).

    static void PrecedenceMacrolibDefineJob(Args _args)
    {
        ;
        #define.MacLib23("_11:  Plain #define value for MacLib23, same name as the AOT macrolib macro.")
        info("_AA: " + #MacLib23);
    
        #macrolib.MacLib23
        info("_BB: " + #DefinInMacLib23); // Defined inside the macrolib macro.
    
        info("_CC: " + #MacLib23); // Output shows plain #define, not the macrolib macro contents.
    
        #define.DefinInMacLib23("_33:  Plain #define in the job code, overwrite of same macro name defined inside the macrolib macro.")
        info("_DD: " + #DefinInMacLib23);
    
    /***************************  Actual Infolog output
    Message (10:53:13 am)
    _AA: 11:  Plain #define value for MacLib23, same name as the AOT macrolib macro.
    _BB: This is inside AOT macrolib MacLib23.
    _CC: 11:  Plain #define value for MacLib23, same name as the AOT macrolib macro.
    _DD: 33:  Plain #define in the job code, overwrite of same macro name defined inside the macrolib macro.
    ***************************/
    }

## Creating a Macro Library in the AOT

The following steps describe how you can create your own macro library in the AOT.

### To create your own macro library in the AOT

1.  Right-click the **Macros** node, and then select **New Macro**.  
    An editor window appears.

2.  Type \#define.BestShape(circle).

3.  Click the save icon (or press CTRL+S).

## See also

[Macros in X++](macros-in-x.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

