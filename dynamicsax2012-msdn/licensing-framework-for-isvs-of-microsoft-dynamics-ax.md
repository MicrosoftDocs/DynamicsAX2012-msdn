---
title: Licensing Framework for ISVs of Microsoft Dynamics AX
TOCTitle: Licensing Framework for ISVs of Microsoft Dynamics AX
ms:assetid: 21487574-1169-4969-be7e-badeb5c25c67
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/JJ677284(v=AX.60)
ms:contentKeyID: 49384054
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Licensing Framework for ISVs of Microsoft Dynamics AX [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

Independent software vendors (ISVs) can use the SysDictLicenseCode class to manage their licensing requirements for custom modules that they sell.

In versions after Microsoft Dynamics AX 2009, the system no longer enables ISVs to enforce licensing requirements based on the number of concurrent users.

## History

In Microsoft Dynamics AX, discussions of ISV license tracking or enforcement can involve the following three kinds of comparisons:

  - The maximum number of users specified in a Microsoft license compared to the maximum number specified in an ISV license.

  - The number of concurrent users presently logged on to Microsoft Dynamics AX compared to the maximum number of users specified in a license.

  - The current date compared to the expiration date specified in licenses.

The following table discusses the license tracking and enforcement models that are available in various versions of Microsoft Dynamics AX.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Version</p></th>
<th><p>Discussion</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Microsoft Dynamics AX 2009</p></td>
<td><p>The system tracks concurrent users. The counts are compared to maximum values that are stored in the license files that are issued by Microsoft. If the count of concurrent users exceeds the maximum, warnings are shown or other actions are taken by the system.</p>
<p>The system also takes action if a necessary license has expired.</p>
<p>The system relies on this concurrent users model, and ISVs can also rely on this model.</p></td>
</tr>
<tr class="even">
<td><p>Microsoft Dynamics AX 2012,<br />
and<br />
 Microsoft Dynamics AX 2012 Feature Pack</p></td>
<td><p>The system no longer uses the concurrent users license count model. Microsoft licenses now have their maximum user count set to 30,000. Any ISV licenses that have a lower value cause warnings to show.</p>
<p>Instead of testing concurrent users, the system now uses the named-user licensing model. The system has access to the list of named users, but ISVs do not.</p>
<p>Licenses can still expire.</p></td>
</tr>
<tr class="odd">
<td><p>Microsoft Dynamics AX 2012 R2</p></td>
<td><p>The system uses the named-user licensing model. The ISV licensing model no longer relies on the concurrent user model, and no enforcement is done based on concurrent user counts. Instead the system now makes it possible for ISVs to leverage information from named-user licensing model.</p>
<p>New methods are available on the SysDictLicenseCode class that read the latest calculated counts of user licenses. The information enables ISVs to use the named-user licensing model.</p>
<p>ISVs can use information from the named-user licenses to implement any licensing algorithm they prefer.</p>
<p>Licenses can still expire.</p></td>
</tr>
</tbody>
</table>


## Methods on the SysDictLicenseCode Class

The following table describes the methods on the SysDictLicenseCode class that ISVs can use to enforce licensing.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Method</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>public server static container <br />
 <br />
 <strong>getCurrentUserLicenseCount</strong> <br />
 <br />
 (UserLicenseType _userLicenseType)</p></td>
<td><p>For the input type of user license, returns a container that has the following information:</p>
<ul>
<li><p>The count of users that are associated with the license type.</p></li>
<li><p>The latest date when the count of users was recalculated by the batch job.</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>public static int <br />
 <br />
 <strong>getISVUserLicenseCount</strong> <br />
 <br />
 (LicenseCodeId _licenseCodeId)</p></td>
<td><p>For the input ISV license code, returns the count that are specified in the ISV license file.</p></td>
</tr>
</tbody>
</table>


## Batch Job Mechanisms

Every week the system runs the batch job named **Named user license count report**. The job might be visible only when it is running. The batch job recalculates the named-user license counts. The job maintains historical data for each run.

For the latest run of the batch job, the data includes the user names. But for historical data only the counts are kept.

The SysUserLicenseMinor class contains the logic that calculates the license counts.

If the batch job has never run, the getCurrentUserLicenseCount method on the SysDictLicenseCode class would return 0 for the count and null for the date of latest recalculation. ISVs can decide how they want their custom modules to react in that situation.

Suppose the batch job runs every week but then skips one or more weeks. The getCurrentUserLicenseCount would return a date that is older than one week. ISVs can decide how they want their custom modules to react in that situation.

You can view the historical data from the batch job at  
 **System administration** \> **Reports** \> **Licensing** \> **Named User License Counts**.

## Trust and Verification

Microsoft relies on the named-user licensing model, but does not disable any modules when licensing requirements are not being met. Instead, Microsoft trusts customers to buy new user licenses when the usage exceeds the purchased allotment. You can see the usage report by running the **Named User License Counts** report.

ISVs can choose how their custom modules react when an insufficient number of user licenses have been purchased. One ISV might decide to show a warning message. Another ISV might have the logic branch around major functionality in its custom code.

### ![JJ677284.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "JJ677284.collapse_all(en-us,AX.60).gif")White Papers about Licensing

For more information about licensing, see the following white papers:

  - [Microsoft Dynamics AX 2012 Licensing Guide](http://download.microsoft.com/download/8/0/e/80e99b9e-9694-41a7-9bd9-bf37fa44da99/dynamics_ax_2012_licensing_guide-customeredition.pdf)

  - [Microsoft Dynamics AX 2012 6.1 Licensing Guide](http://www.microsoft.com/en-us/download/details.aspx?id=29859)

  - [Microsoft Dynamics AX 2012 6.1 Security Roles & Licensing](http://go.microsoft.com/fwlink/?linkid=228370)

## See also

[Define or edit entry point permissions](https://msdn.microsoft.com/en-us/library/hh859725\(v=ax.60\))

[License code and configuration key reference](https://msdn.microsoft.com/en-us/library/hh378074\(v=ax.60\))

[Naming Conventions: License Codes](naming-conventions-license-codes.md)

[SysDictLicenseCode](https://msdn.microsoft.com/en-us/library/gg947521\(v=ax.60\))

[UserLicenseType Enumeration](https://msdn.microsoft.com/en-us/library/hh151301\(v=ax.60\))

[LicenseCodeId Extended Data Type](https://msdn.microsoft.com/en-us/library/gg839332\(v=ax.60\))

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

