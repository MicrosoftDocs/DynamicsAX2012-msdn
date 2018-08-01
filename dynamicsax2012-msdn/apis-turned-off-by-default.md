---
title: APIs Turned Off by Default
TOCTitle: APIs Turned Off by Default
ms:assetid: 9223d6fd-e233-4f1c-a9da-7e2faf20db71
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa661241(v=AX.60)
ms:contentKeyID: 35247447
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# APIs Turned Off by Default [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Certain kernel APIs are turned off by default. To enable these APIs, an administrator must manually turn on the appropriate configuration key.

If these kernel APIs are enabled, they can be used to call into Microsoft Dynamics AX from dangerous, external code. If you decide to enable these APIs, you should threat model the code first to identify potential threats.

The following table lists the APIs and their corresponding configuration keys:

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>API</p></th>
<th><p>Configuration Key</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg912635(v=ax.60)">PipeClient Class</a></p></td>
<td><p>Pipe Client API configuration key (SysAPIPipeClient)</p></td>
</tr>
<tr class="even">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg837485(v=ax.60)">DDEClient Class</a></p></td>
<td><p>Dynamic Data Exchange API configuration key (SysAPIDDE)</p></td>
</tr>
<tr class="odd">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg837497(v=ax.60)">DDEServer Class</a></p></td>
<td><p>Dynamic Data Exchange API configuration key (SysAPIDDE)</p></td>
</tr>
<tr class="even">
<td><p><a href="https://msdn.microsoft.com/en-us/library/gg837506(v=ax.60)">DDETopic Class</a></p></td>
<td><p>Dynamic Data Exchange API configuration key (SysAPIDDE)</p></td>
</tr>
</tbody>
</table>


## See also

[X++ Security](x-security.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

