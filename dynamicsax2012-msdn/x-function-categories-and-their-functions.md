---
title: X++ Function Categories and their Functions
TOCTitle: X++ Function Categories and their Functions
ms:assetid: 10e068e3-e67c-41c3-84d7-c376a8373611
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Dd252591(v=AX.60)
ms:contentKeyID: 35240551
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# X++ Function Categories and their Functions 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

This topic lists every X++ built-in function by category.

## Descriptions of Categories

The following table lists only the categories of X++ functions. Each category is described. These categories help people to understand the many functions, but the categories do not represent any formal construct in Microsoft Dynamics AX.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Category</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Business</p></td>
<td><p>Functions that input financial data and calculate formulas.</p></td>
</tr>
<tr class="even">
<td><p>Compiler Verified</p>
<p>(also named Intrinsic)</p></td>
<td><p>Functions that have their input value verified by the compiler. If the input value is not found to match any existing object in the Application Object Tree (AOT), the compiler issues an error.</p>
<p>The inputs to these functions must be literals, because the compiler cannot determine the value that a variable contains at run time.</p></td>
</tr>
<tr class="odd">
<td><p>Container</p></td>
<td><p>Functions that operate on the container data type of X++.</p></td>
</tr>
<tr class="even">
<td><p>Convert</p></td>
<td><p>Functions that translate data of one type into data of another type.</p></td>
</tr>
<tr class="odd">
<td><p>Date</p></td>
<td><p>Functions that operate on the date data type.</p></td>
</tr>
<tr class="even">
<td><p>Enum</p></td>
<td><p>Functions that operate on enum objects.</p></td>
</tr>
<tr class="odd">
<td><p>Math</p></td>
<td><p>Functions that perform mathematical calculations.</p></td>
</tr>
<tr class="even">
<td><p>Miscellaneous</p></td>
<td><p>Functions that do not belong to any specific category.</p></td>
</tr>
<tr class="odd">
<td><p>Reflection</p></td>
<td><p>Functions that access the metadata about objects and return other metadata about them.</p></td>
</tr>
<tr class="even">
<td><p>Session</p></td>
<td><p>Functions that change or report on the context of the current user connection.</p></td>
</tr>
<tr class="odd">
<td><p>String</p></td>
<td><p>Functions that operate on the str data type.</p></td>
</tr>
</tbody>
</table>


## Categorization of X++ Functions

The following table lists the X++ functions that belong in each previous category.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Category</p></th>
<th><p>X++ function</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Business</p></td>
<td><ul>
<li><p>cTerm</p></li>
<li><p>ddb</p></li>
<li><p>dg</p></li>
<li><p>fv</p></li>
<li><p>idg</p></li>
<li><p>intvMax</p></li>
<li><p>intvName</p></li>
<li><p>intvNo</p></li>
<li><p>intvNorm</p></li>
<li><p>pmt</p></li>
<li><p>pt</p></li>
<li><p>pv</p></li>
<li><p>rate</p></li>
<li><p>sln</p></li>
<li><p>syd</p></li>
<li><p>term</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Compiler Verified</p>
<p>(also named Intrinsic)</p></td>
<td><ul>
<li><p>attributeStr</p></li>
<li><p>classNum</p></li>
<li><p>classStr</p></li>
<li><p>configurationKeyNum</p></li>
<li><p>configurationKeyStr</p></li>
<li><p>datasetStr</p></li>
<li><p>enumNum</p></li>
<li><p>enumStr</p></li>
<li><p>evalBuf</p></li>
<li><p>extendedTypeNum</p></li>
<li><p>extendedTypeStr</p></li>
<li><p>fieldNum</p></li>
<li><p>fieldPName</p></li>
<li><p>fieldStr</p></li>
<li><p>formControlStr</p></li>
<li><p>formStr</p></li>
<li><p>identifierstr</p></li>
<li><p>indexNum</p></li>
<li><p>indexStr</p></li>
<li><p>licenseCodeNum</p></li>
<li><p>licenseCodeStr</p></li>
<li><p>literalStr</p></li>
<li><p>menuItemActionStr</p></li>
<li><p>menuItemDisplayStr</p></li>
<li><p>menuItemOutputStr</p></li>
<li><p>menuStr</p></li>
<li><p>methodStr</p></li>
<li><p>perspectiveNum</p></li>
<li><p>perspectiveStr</p></li>
<li><p>queryDataSourceStr</p></li>
<li><p>queryStr</p></li>
<li><p>reportStr</p></li>
<li><p>resourceStr</p></li>
<li><p>runBuf</p></li>
<li><p>securityKeyNum</p></li>
<li><p>securityKeyStr</p></li>
<li><p>ssrsReportStr</p></li>
<li><p>staticMethodStr</p></li>
<li><p>tableCollectionStr</p></li>
<li><p>tableFieldGroupStr</p></li>
<li><p>tableMethodStr</p></li>
<li><p>tableNum</p></li>
<li><p>tablePName</p></li>
<li><p>tableStaticMethodStr</p></li>
<li><p>tableStr</p></li>
<li><p>varStr</p></li>
<li><p>webActionItemStr</p></li>
<li><p>webDisplayContentItemStr</p></li>
<li><p>webFormStr</p></li>
<li><p>webletItemStr</p></li>
<li><p>webMenuStr</p></li>
<li><p>webOutputContentItemStr</p></li>
<li><p>webPageDefStr</p></li>
<li><p>webReportStr</p></li>
<li><p>webSiteDefStr</p></li>
<li><p>webSiteTempStr</p></li>
<li><p>webStaticFileStr</p></li>
<li><p>webUrlItemStr</p></li>
<li><p>webWebpartStr</p></li>
<li><p>workflowApprovalStr</p></li>
<li><p>workflowCategoryStr</p></li>
<li><p>workflowTaskStr</p></li>
<li><p>workflowTemplateStr</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Container</p></td>
<td><ul>
<li><p>conDel</p></li>
<li><p>conFind</p></li>
<li><p>conIns</p></li>
<li><p>conLen</p></li>
<li><p>conNull</p></li>
<li><p>conPeek</p></li>
<li><p>conPoke</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Convert</p></td>
<td><ul>
<li><p>any2Enum</p></li>
<li><p>any2Date</p></li>
<li><p>any2Guid</p></li>
<li><p>any2Int</p></li>
<li><p>any2Int64</p></li>
<li><p>any2Real</p></li>
<li><p>any2Str</p></li>
<li><p>char2Num</p></li>
<li><p>Date2Num</p></li>
<li><p>Date2Str</p></li>
<li><p>Datetime2Str</p></li>
<li><p>formattedStr2Num</p></li>
<li><p>guid2Str</p></li>
<li><p>int2Str</p></li>
<li><p>int642Str</p></li>
<li><p>num2Char</p></li>
<li><p>num2Date</p></li>
<li><p>num2Str</p></li>
<li><p>str2Enum</p></li>
<li><p>str2Date</p></li>
<li><p>str2Datetime</p></li>
<li><p>str2Guid</p></li>
<li><p>str2Int</p></li>
<li><p>str2Int64</p></li>
<li><p>str2Num</p></li>
<li><p>str2Time</p></li>
<li><p>time2Str</p></li>
<li><p>uint2Str</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Date</p></td>
<td><ul>
<li><p>dayName</p></li>
<li><p>dayOfMth</p></li>
<li><p>dayOfWk</p></li>
<li><p>dayOfYr</p></li>
<li><p>endMth</p></li>
<li><p>maxDate</p></li>
<li><p>mkDate</p></li>
<li><p>mthName</p></li>
<li><p>mthOfYr</p></li>
<li><p>nextMth</p></li>
<li><p>nextQtr</p></li>
<li><p>nextYr</p></li>
<li><p>prevMth</p></li>
<li><p>prevQtr</p></li>
<li><p>prevYr</p></li>
<li><p>timeNow</p></li>
<li><p>today</p></li>
<li><p>wkOfYr</p></li>
<li><p>year</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Enum</p></td>
<td><ul>
<li><p>enum2Str</p></li>
<li><p>enumCnt</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Math</p></td>
<td><ul>
<li><p>abs</p></li>
<li><p>acos</p></li>
<li><p>asin</p></li>
<li><p>atan</p></li>
<li><p>corrFlagGet</p></li>
<li><p>corrFlagSet</p></li>
<li><p>cos</p></li>
<li><p>cosh</p></li>
<li><p>decRound</p></li>
<li><p>exp</p></li>
<li><p>exp10</p></li>
<li><p>frac</p></li>
<li><p>log10</p></li>
<li><p>logN</p></li>
<li><p>power</p></li>
<li><p>round</p></li>
<li><p>sin</p></li>
<li><p>sinh</p></li>
<li><p>tan</p></li>
<li><p>tanh</p></li>
<li><p>trunc</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Miscellaneous</p></td>
<td><ul>
<li><p>beep</p></li>
<li><p>classIdGet</p></li>
<li><p>dimOf</p></li>
<li><p>getPrefix</p></li>
<li><p>max</p></li>
<li><p>maxInt</p></li>
<li><p>min</p></li>
<li><p>minInt</p></li>
<li><p>newGuid</p></li>
<li><p>setPrefix</p></li>
<li><p>sleep</p></li>
<li><p>systemDateget</p></li>
<li><p>systemDateset</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>Reflection</p></td>
<td><ul>
<li><p>fieldId2Name</p></li>
<li><p>fieldId2PName</p></li>
<li><p>fieldName2Id</p></li>
<li><p>indexId2Name</p></li>
<li><p>indexName2Id</p></li>
<li><p>refPrintAll</p></li>
<li><p>tableId2Name</p></li>
<li><p>tableId2PName</p></li>
<li><p>tableName2Id</p></li>
<li><p>typeOf</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Session</p></td>
<td><ul>
<li><p>curExt</p></li>
<li><p>curUserId</p></li>
<li><p>getCurrentPartition</p></li>
<li><p>getCurrentPartitionRecId</p></li>
<li><p>SessionId</p></li>
<li><p>funcName</p></li>
<li><p>prmIsDefault</p></li>
<li><p>runAs</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>String</p></td>
<td><ul>
<li><p>match</p></li>
<li><p>strAlpha</p></li>
<li><p>strCmp</p></li>
<li><p>strColSeq</p></li>
<li><p>strDel</p></li>
<li><p>strFind</p></li>
<li><p>strFmt</p></li>
<li><p>strIns</p></li>
<li><p>strKeep</p></li>
<li><p>strLen</p></li>
<li><p>strLine</p></li>
<li><p>strLTrim</p></li>
<li><p>strLwr</p></li>
<li><p>strNFind</p></li>
<li><p>strPoke</p></li>
<li><p>strPrompt</p></li>
<li><p>strRem</p></li>
<li><p>strRep</p></li>
<li><p>strRTrim</p></li>
<li><p>strScan</p></li>
<li><p>strUpr</p></li>
<li><p>subStr</p></li>
</ul></td>
</tr>
</tbody>
</table>


## See also

[X++ Functions](x-functions.md)

[Functions](https://msdn.microsoft.com/en-us/library/aa856741\(v=ax.60\))

[Intrinsic Functions](intrinsic-functions.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

