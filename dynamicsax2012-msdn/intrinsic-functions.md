---
title: Intrinsic Functions
TOCTitle: Intrinsic Functions
ms:assetid: 407c83d7-4a0a-4c16-b9bd-e8783e73d837
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa626893(v=AX.60)
ms:contentKeyID: 35242945
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Intrinsic Functions 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Intrinsic functions are metadata assertion functions. They take arguments that represent entities in the Application Object Tree (AOT), and validate these arguments at compile time. They have no effect at run time. Intrinsic functions are a subgroup of the [X++ system functions](https://msdn.microsoft.com/en-us/library/aa856741\(v=ax.60\)), and typically have names ending in Num or Str, for example: classNum and formStr.

Intrinsic functions should be used wherever possible in X++ code to make the code resilient to changes to the metadata stored in the AOT.

You will get a best practice warning if you use the for identifierStr function. This is because no existence checking is carried out for identifierStr. Try to use a more specific intrinsic function if one is available.

The following list contains the intrinsic functions in MorphX.

## Validation of Table Metadata

  - tableCollectionStr

  - tableFieldGroupStr

  - tablePName

  - tableNum

  - tableMethodStr

  - tableStaticMethodStr

  - tableStr

## Validation of Field Metadata

  - fieldNum

  - fieldPname

  - fieldStr

## Validation of Index Metadata

  - indexNum

  - indexStr

## Validation of Data Type Metadata

  - enumCnt

  - enumNum

  - enumStr

  - extendedTypeNum

  - extendedTypeStr

  - typeId

## Validation of Configuration Key Metadata

  - configurationKeyNum

  - configurationKeyStr

## Validation of License Metadata

  - licenseCodeNum

  - licenseCodeStr

## Validation of Class Metadata

  - classNum

  - classStr

  - methodStr

  - staticMethodStr

## Validation of Form, Report, Query, and Menu Metadata

Where possible, use the AutoDeclaration property on controls.

  - formStr


> [!NOTE]
> <P>In forms, control::&nbsp;controlName returns the ID of the control.</P>



  - formControlStr

  - menuItemActionStr

  - menuItemDisplayStr

  - menuItemOutputStr

  - menuStr

  - reportStr

  - queryStr

  - queryDataSourceStr

## Validation of Web Metadata

  - webActionItemStr

  - webDisplayContentItemStr

  - webletItemStr

  - webOutputContentItemStr

  - webpageDefStr

  - webReportStr

  - websiteDefStr

  - websiteTempStr

  - webStaticFileStr

  - webUrlItemStr

  - webWebpartStr

## Other

  - identifierStr

  - literalStr

  - maxDate

  - maxInt

  - minDate

  - minInt

  - resourceStr

  - varStr

## See also

[Functions](https://msdn.microsoft.com/en-us/library/aa856741\(v=ax.60\))

[X++ Function Categories and their Functions](x-function-categories-and-their-functions.md)

[Global Class](https://msdn.microsoft.com/en-us/library/gg836018\(v=ax.60\))

[DateTimeUtil Class](https://msdn.microsoft.com/en-us/library/gg837448\(v=ax.60\))

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

