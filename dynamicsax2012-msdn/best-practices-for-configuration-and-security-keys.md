---
title: Best Practices for Configuration and Security Keys
TOCTitle: Configuration and Security Keys
ms:assetid: 1c07bfa9-3ddd-40ce-8f6d-f6238414a510
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa590456(v=AX.60)
ms:contentKeyID: 35241420
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Best Practices for Configuration and Security Keys [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Configuration keys determine which features are turned on during the installation.


> [!NOTE]
> <P>Security keys are obsolete in Microsoft Dynamics AX 2012 and only exist to use for reference during a code upgrade. There is a new security framework, which is called role-based security. For more information on the new security framework, see <A href="role-based-security-in-the-aot-for-developers.md">Role-based Security in the AOT for Developers</A>.</P>



## Configuration Keys

Configuration keys should be defined so that the installation can be set up with only the features needed for each particular installation. By disabling configuration keys, administrators can reduce the potential surface of attack, thereby helping to increase the security of their Microsoft Dynamics AX installation.

Configuration keys are often arranged in hierarchies of functionality, mirroring the hierarchies of functionality in the application.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Property</p></th>
<th><p>Rules</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span id="rx392name"></span> Name</p></td>
<td><p>Follow the standard <a href="naming-conventions.md">Naming Conventions</a>.</p>
<p>If you attempt to create a configuration key by using a name that has already been used for a configuration key in Microsoft Dynamics AX, an error will occur. <img src="images/Aa872655.ErrorIcon(AX.60).gif" title="Error icon" alt="Error icon" /></p></td>
</tr>
</tbody>
</table>

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

