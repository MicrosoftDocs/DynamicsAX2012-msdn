---
title: 'Best Practices: Avoiding Potential Security Issues'
TOCTitle: 'Best Practices: Avoiding Potential Security Issues'
ms:assetid: 3b82ba8b-366d-4dfb-84b3-6603e880c3b0
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa625308(v=AX.60)
ms:contentKeyID: 35242907
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Best Practices: Avoiding Potential Security Issues [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Some of the X++ APIs may have potential security issues. For example, they might allow unauthorized access to the database or the Application Object Tree (AOT), if used in a nonsecure manner.

If a call to one of these potentially unsafe APIs generates a Best Practices error, this indicates that you should assess the security implications of using the method. You may need to apply Code Access Security by using one of the classes derived from [CodeAccessPermission](https://msdn.microsoft.com/en-us/library/gg803417\(v=ax.60\)), and/or take other mitigating actions, such as validating user input.

When you are satisfied that the security implications of using the class have been investigated and mitigated, you can turn off the best practice error by adding the following comment above the call to the method.

// BP Deviation documented

There is more information about the mitigations for each potentially unsafe API in the Help topics for the classes you received the error message for.

For more information about the APIs protected by Code Access Security, see [Secured APIs](secured-apis.md).

Microsoft Dynamics AX conducts a best practices check of the XML comments to be sure that you provide documentation in the appropriate tags. For information about how to set the options for best practice checks, see [Best practice parameters](best-practice-parameters.md).

## Best Practice Checks

The following table lists the best practices error messages and how to fix the errors.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Message</p></th>
<th><p>Message type</p></th>
<th><p>How to fix the error or warning</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TwC: Validate data displayed in form is fetched using record level security. Dangerous API %1 used.</p></td>
<td><p>Error</p></td>
<td><p>Assess the security implications of using the method. You may need to apply Code Access Security by using one of the classes derived from <a href="https://msdn.microsoft.com/en-us/library/gg803417(v=ax.60)">CodeAccessPermission Class</a>. For information about record level security, see <a href="record-level-security.md">Record Level Security</a>. For more information about security, see <a href="http://go.microsoft.com/fwlink/?linkid=108580">Writing Secure X++ Code</a>.</p></td>
</tr>
</tbody>
</table>


## See also

[Best Practices Checks](best-practices-checks.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

