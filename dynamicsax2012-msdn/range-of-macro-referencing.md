---
title: Range of Macro Referencing
TOCTitle: Range of Macro Referencing
ms:assetid: 1059706d-2ef0-4d21-8055-2f76244d7ff8
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc197108(v=AX.60)
ms:contentKeyID: 35240537
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Range of Macro Referencing 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The range in which a macro can be referenced depends on where the macro is defined. In a class, macros that are defined in the parent class can be referenced, but macros defined in a child class cannot be referenced.

## Prerequisites

For this topic, you must understand the information in the following topics:

  - [How to: Use the \#undef Directive](how-to-use-the-sharpundef-directive.md)

  - [How to: Test a Macro Value](how-to-test-a-macro-value.md)

## Sequence of Precompiler Actions

When the precompiler handles a child class, the precompiler first traces the inheritance chain to the most ascendant class. The precompiler processes all the directives from the class declaration part of the ascendant class. It stores all the macros and their values in its internal tables.

The precompiler handles the next class in the inheritance chain the same way. The result of the directives in each class declaration are applied to the internal tables that are already populated from directives that were found earlier in the inheritance chain.

When the precompiler reaches the target child class, it again handles the class declaration part. However, it next handles each method in a series of separate operations. The precompiler updates its internal tables in a way that the state of the tables can be restored as they were before processing of the current method began. After the first method is handled, the internal tables are restored before the next method is handled.

### ![Cc197108.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc197108.collapse_all(en-us,AX.60).gif")The Method is All Contents of the Node

In this context, a method is defined as the contents of a method node in the Application Object Tree (AOT). In the AOT, you can expand the **Classes** node, expand a class node, right-click a method node, and then select **Edit**. Then you can add a line for \#define.MyMacro("abc") before the method declaration. The precompiler treats this \#define directive as part of the method, even though the \#define occurs outside the {} block of the method.

## Class Inheritance and Macro Reference Range

You can paste the pieces of the following X++ code sample into the AOT under the **Classes** or **Jobs** node, and then run the job. This demonstrates the range of macro referencing in class inheritance scenarios.

The primary line to notice in the job's output is the line labeled CGrandchild5\_h. It shows that a macro defined in a grandparent class can be referenced in a method of the grandchild class.

Another important line in the output is labeled CBase1\_k. This line shows that a macro defined in a method is not available in other methods.

### ![Cc197108.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc197108.collapse_all(en-us,AX.60).gif")The Parent/Child/Grandchild Classes

The following three classes are in an inheritance chain:

  - The Base Class

  - The Mid-Level Inheritance Class

  - The Grandchild class

#### ![Cc197108.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc197108.collapse_all(en-us,AX.60).gif")The Base Class

The base class defines several macros in its class declaration. Its descendant classes reference these macros.

The base class also defines a macro inside one of its methods. A second method in this class determines the macro is defined out of range and cannot be referenced in the second method.

The \#undef.MacroRange333 in the method UseOtherMethodMacro affects the availability of macro MacroRange333 in the rest of that method. Descendant classes can still reference MacroRange333.
```X++  
    public class ClassInheritanceOfMacrosCBase1
    {
        //   Unless disturbed by other directives, these macros can
        // be referenced by method in this class in child classes.
        #define.MacroRangeA
        #define.MacroRangeB(22)
        #define.MacroRange333(333)
    
        static void UseMacros()
        {
            //   This method shows that a macro that is defined
            // in the class declaration is in range in every
            // method in that class.
            //   This method also contains a define for macro
            // MacroDefInMethodD, and tests outside this
            // method determine the macro is not in range.
            ;
            info("CBase1_a: #MacroRangeB == " + int2str(#MacroRangeB));
            #define.MacroDefInMethodD // Cannot be referenced in other methods.
        }
    
        static void UseOtherMethodMacro()
        {
            //   This method shows that the macro MacroDefInMethodD
            // that was defined in another method in this class
            // cannot be referenced in this method.
            //   This method contains an #undef of MacroRange333,
            // yet descendant classes can still reference this macro.
            ;
            #ifnot.MacroDefInMethodD
                info("CBase1_k: This means MacroDefInMethodD is in not range here.");
            #endif
            #undef.MacroRange333
        }
    }
```
#### ![Cc197108.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc197108.collapse_all(en-us,AX.60).gif")The Mid-Level Inheritance Class

The mid-level inheritance class undefines the macro MacroRangeA that is defined in its parent class. This makes the macro unavailable to any class that extends the present class.

The present class also redefines the macro MacroRangeB that is defined in its parent class. This changes the value of the macro (from positive to negative).
```X++  
    public class ClassInheritanceOfMacrosCMid3 extends
            ClassInheritanceOfMacrosCBase1
    {
        //   This class declaration makes the macro MacroRangeA
        // unavailable to methods in this class and child classes.
        //   This class declaration also redefines MacroRangeB for
        // this class and child classes.
        #undef.MacroRangeA // Makes unavailable to child classes.
        #define.MacroRangeB(-22) // Redefining with a different value.
    
        static void UseMacros()
        {
            //   This method shows that the value for #MacroRangeB comes
            // from its redefinition in this class, instead of from
            // the definition in the parent class.
            ;
            info("CMid3_c: #MacroRangeB == " + int2str(#MacroRangeB)
                + " (Is now negative due to later redefinition.)");
        }
    }

```

#### ![Cc197108.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc197108.collapse_all(en-us,AX.60).gif")The Grandchild Class

The grandchild class uses \#ifnot to demonstrate that it cannot access the MacroRangeA macro that its grandparent class defines. The reason is that the mid-level class undefined the macro.

The grandchild class also demonstrates that it can access the macro MacroRange333 that its grandparent class defines.

```X++  
    public class ClassInheritanceOfMacrosCGrandchild5 extends
            ClassInheritanceOfMacrosCMid3
    {
        static void UseMacros()
        {
            //   This method shows that the #undef in the parent
            // class overwrites the #define in the grandparent class.
            //   This method also shows that a macro defined in the
            // grandparent class is in range in methods on this class.
            ;
            #ifnot.MacroRangeA
                info("CGrandchild5_f: MacroRangeA is no longer defined, due to #undef in child class CMid3.");
            #endif
    
            info("CGrandchild5_h: #MacroRange333 == " + int2str(#MacroRange333)
                + " (Defined in grandparent class CBase1.)");
        }
    }
```

### ![Cc197108.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc197108.collapse_all(en-us,AX.60).gif")A Job to Run the Inheritance Test

The following X++ job calls the demonstration methods of the parent/child/grandchild classes, and displays the results.

The **Infolog** output from a job run is given in a comment box in the code.
```X++  
    static void JobClassesCC(Args _args)
    {
        ;
        ClassInheritanceOfMacrosCBase1 ::UseMacros();
        ClassInheritanceOfMacrosCBase1 ::UseOtherMethodMacro();
        ClassInheritanceOfMacrosCMid3 ::UseMacros();
        ClassInheritanceOfMacrosCGrandchild5 ::UseMacros();
    
    /****************  Actual output
    Message (08:10:59 am)
    CBase1_a: #MacroRangeB == 22
    CBase1_k: This means MacroDefInMethodD is not in range here.
    CMid3_c: #MacroRangeB == -22 (Is now negative due to later redefinition.)
    CGrandchild5_f: MacroRangeA is no longer defined, due to #undef in child class CMid3.
    CGrandchild5_h: #MacroRange333 == 333 (Defined in grandparent class CBase1.)
    ****************/
    }
```

## See also

[Macros in X++](macros-in-x.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

