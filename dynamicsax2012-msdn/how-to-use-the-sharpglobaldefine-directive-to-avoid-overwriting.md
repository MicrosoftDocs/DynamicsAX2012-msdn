---
title: 'How to: Use the #globaldefine Directive to Avoid Overwriting'
TOCTitle: 'How to: Use the #globaldefine Directive to Avoid Overwriting'
ms:assetid: dba5130a-74f2-4e92-80af-4dc1414c57d5
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc197124(v=AX.60)
ms:contentKeyID: 35252075
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Use the \#globaldefine Directive to Avoid Overwriting [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The \#globaldefine directive is similar to the \#define directive. The difference is that \#define directives generally take precedence over \#globalmacro directives. This is true regardless of which directive occurs first in the X++ code.

A \#globaldefine never overwrites a \#define directive that has both a macro name and a value. A \#globaldefine can overwrite another \#globaldefine.

A \#define directive that has only a name does not overwrite a \#globalmacro that has both a name and a value.


> [!TIP]
> <P>It is recommended that you use #define, and that you do not use #globaldefine. Use of #globaldefine can create uncertainty that makes code difficult to maintain.</P>



## Prerequisites

For this topic, you must understand the information in [How to: Test a Macro Value](how-to-test-a-macro-value.md).

## Code Sample for \#globaldefine

The following code sample shows a difference in the behavior of \#define and \#globaldefine. Following the code sample is a table explaining the conclusions from the output. The primary test case in the code sample is labeled 12.

```X++
    static void InteractDefineGlobalJob(Args _args)
    {
        ;
        // Pairs of #define - #globaldefine directives (same macro names).
        #define.11_DEFINEvalue_GLOBALnoval("11__DEFINE.")
        #globaldefine.11_DEFINEvalue_GLOBALnoval
    
        #define.12_DEFINEnoval_GLOBALvalue
        #globaldefine.12_DEFINEnoval_GLOBALvalue("12_GLOBAL.")
    
        #define.13_DEFINEvalue_GLOBALvalue("13__DEFINE.")
        #globaldefine.13_DEFINEvalue_GLOBALvalue("13_GLOBAL.")
    
        // Pairs of #globaldefine - #define directives.
        #globaldefine.27_GLOBALvalue_DEFINEnoval("27_GLOBAL.")
        #define.27_GLOBALvalue_DEFINEnoval
    
        #globaldefine.28_GLOBALnoval_DEFINEvalue
        #define.28_GLOBALnoval_DEFINEvalue("28__DEFINE.")
    
        #globaldefine.29_GLOBALvalue_DEFINEvalue("29_GLOBAL.")
        #define.29_GLOBALvalue_DEFINEvalue("29__DEFINE.")
    
        // Pairs of same directive types.
        #define.50_DEFINEvalue_DEFINEnoval("50__DEFINE 1.")
        #define.50_DEFINEvalue_DEFINEnoval
    
        #globaldefine.64_GLOBALvalue_GLOBALnoval("64_GLOBAL 1.")
        #globaldefine.64_GLOBALvalue_GLOBALnoval
    
        #globaldefine.65_GLOBALnoval_GLOBALvalue
        #globaldefine.65_GLOBALnoval_GLOBALvalue("65_GLOBAL 2.")
    
        #globaldefine.66_GLOBALvalue_GLOBALvalue("66_GLOBAL 1.")
        #globaldefine.66_GLOBALvalue_GLOBALvalue("66_GLOBAL 2.")
    
        // Infolog outputs.
    
        info(#11_DEFINEvalue_GLOBALnoval);
        info(#12_DEFINEnoval_GLOBALvalue);
        info(#13_DEFINEvalue_GLOBALvalue);
    
        info(#27_GLOBALvalue_DEFINEnoval);
        info(#28_GLOBALnoval_DEFINEvalue);
        info(#29_GLOBALvalue_DEFINEvalue);
    
        info(#50_DEFINEvalue_DEFINEnoval);
    
        info(#64_GLOBALvalue_GLOBALnoval);
        info(#65_GLOBALnoval_GLOBALvalue);
        info(#66_GLOBALvalue_GLOBALvalue);
    
    /*****************************  Actual Infolog output
    Message (09:31:26 pm)
    11__DEFINE.
    12_GLOBAL.
    13__DEFINE.
    27_GLOBAL.
    28__DEFINE.
    29__DEFINE.
    50__DEFINE 1.
    64_GLOBAL 1.
    65_GLOBAL 2.
    66_GLOBAL 2.
    *****************************/
    }
```

### ![Cc197124.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc197124.collapse_all(en-us,AX.60).gif")Explanation of Outputs and Conclusions

The following table explains the test case outcomes from the previous code sample. The explanations document the behavior of \#globalmacro.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Test case</p></th>
<th><p>Explanation</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>13 and 29</p></td>
<td><p>Shows that #define usually takes precedence over #globaldefine, regardless of which directive occurs first in the X++ code.</p>
<p>Test case 12 shows this is not always true.</p></td>
</tr>
<tr class="even">
<td><p>12</p></td>
<td><p>Shows that #globaldefine overwrites #define when #globaldefine is giving a value to an existing macro that has no value.</p>
<p>Test cases 13 and 29 are more common and realistic.</p></td>
</tr>
<tr class="odd">
<td><p>50 and 64</p></td>
<td><p>Shows that a #globaldefine that has a name but no value does not overwrite a #globaldefine that has both a name and a value. The same is true between a pair of #define directives.</p>
<p>This resembles test case 12.</p></td>
</tr>
<tr class="even">
<td><p>65 and 66</p></td>
<td><p>Shows that a #globaldefine that has both a name and a value overwrites a previous #globaldefine.</p></td>
</tr>
</tbody>
</table>


## Different from \#if Test Approach

The exact semantics of \#globaldefine cannot be achieved through \#if test directives. By using \#if tests you can avoid overwriting a \#define and a \#globaldefine. But \#if tests cannot distinguish between \#define and \#globaldefine macros.

The following code sample is the closest you can come to achieving the \#globaldefine semantic with other directives such as \#if.

```X++
static void IfNotDefineNestGlobalJob (Args _args)
    {
        ;
        #undef.MaybeMac
    
        #ifnot.MaybeMac
            #define.MaybeMac(4444) // Works.
        #endif
    
        #if.MaybeMac
            info(int2str(#MaybeMac));
        #endif
    
    /**********************  Actual Infolog output
    Message (07:43:32 pm)
    4444
    **********************/
    }
```

## See also

[Macros in X++](macros-in-x.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

