---
title: Best Practices Checks
TOCTitle: Best Practices Checks
ms:assetid: d7ad995f-2404-4b7e-bfe0-94d35052b961
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa874347(v=AX.60)
ms:contentKeyID: 35252064
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Best Practices Checks [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Check your own code and application objects for compliance with the best practices for Microsoft Dynamics AX.

1.  Select **Tools** \> **Options**.

2.  Click the Development area, in the toolbar, click the **Best practices** button.

3.  In the **Warning level** list, select the checks that you want to perform.

This will mean that best practices are checked when you compile or check in an object.

You can also check best practices for one or more nodes in the Application Object Tree (AOT): right-click the node, and then select **Add-Ins** \> **Check Best practices**.

In this guide, conformances that can be checked this way are marked with these symbols: ![Error icon](images/Aa872655.ErrorIcon(AX.60).gif "Error icon"), ![Warning icon](images/Aa658028.WarningIcon(en-us,AX.60).gif "Warning icon"), ![Information icon](images/Aa658028.InfoIcon(en-us,AX.60).gif "Information icon"). Approximately 25 percent of the Best Practices that are described in this guide can be checked by the tool.

## Results

Results are displayed in an **Infolog**, with the following severity code:

  - ![Information icon](images/Aa658028.InfoIcon(en-us,AX.60).gif "Information icon") Information: Things that might be nice to know (shown in blue).

  - ![Warning icon](images/Aa658028.WarningIcon(en-us,AX.60).gif "Warning icon") Warnings: Things that you should strongly consider fixing (shown in yellow).

  - ![Error icon](images/Aa872655.ErrorIcon(AX.60).gif "Error icon") Errors: Things that should definitely be fixed (shown in red).

If you double-click on an error message, this will open the code editor.

## Fix the Problems

It should be a goal to remove as many of the warnings and errors as possible, with the focus on increasing the quality of the solution (not just to reduce the number of errors in the **Infolog**).


> [!NOTE]
> <P>You cannot check code that causes a Best Practice error into the version control system.</P>



The Best Practices checks cannot give anything more than a good guess or an idea. Although you must fix Best Practice errors, in some other cases your own solutions will be better. As a guideline, this might occur for 5 percent of Best Practice warnings.

## Disable Individual Warnings and Errors

You can stop a particular piece of code from causing a best practice warning or error in two ways:

  - By using a BP Deviation documented comment

  - By using the SysBPCheckIgnore macro


> [!WARNING]
> <P>You should not disable an error or warning message unless the code needs to violate the best practice rule for a known reason.</P>



### ![Aa874347.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa874347.collapse_all(en-us,AX.60).gif")Use a "BP Deviation documented" Comment

You can disable certain warnings caused by a best practice deviation in a particular piece of X++ code. The warning is "disabled" by decreasing the severity to an Information message.

To prevent a piece of code from causing a warning, add a comment above the line of code causing the problem, with the text:

//BP Deviation documented

### ![Aa874347.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa874347.collapse_all(en-us,AX.60).gif")Use the SysBPCheckIgnore Macro

You can stop a piece of code from causing a particular best practice error or warning by adding the following line of code to the SysBPCheckIgnore macro:

c+=\[\[\# BPErrorCode ,@" AOTLocation "\]\];

You do this in situations where:

  - BPErrorCode is the error code for the warning/error as listed in the SysBPCheck macro.

  - AOTLocation is the location of the object causing the error, in the Application Object Tree (AOT).

For example, to disable an error message caused by renaming a class to ProjTransCostForecast, you would write:

c+=\[\[\#BPErrorObjectNameConflict,@"\\Classes\\ProjTransCostForecast"\]\];

After you have edited the SysBPCheckIgnore macro, you need to recompile the SysBPCheck class, and then exit Microsoft Dynamics AX. When you restart Microsoft Dynamics AX, the error or the warning will be suppressed.

## See also

[Best Practices for Microsoft Dynamics AX Development](best-practices-for-microsoft-dynamics-ax-development.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

