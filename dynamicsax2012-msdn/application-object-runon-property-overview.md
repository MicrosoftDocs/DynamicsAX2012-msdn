---
title: Application Object RunOn Property Overview
TOCTitle: Application Object RunOn Property Overview
ms:assetid: 24d191d3-888c-4d9b-9204-f3a3cae64679
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa634829(v=AX.60)
ms:contentKeyID: 35241638
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Application Object RunOn Property Overview 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

In Microsoft Dynamics AX, application objects such as reports, tables, and methods can run on the application object server (AOS) or the client. An object can also have the RunOn property value set to Called from. Objects set to Called from can run from either the client or server, depending on where the object is called from. This topic describes the RunOn property, tiers that class objects can run on, and hints about using AOSRunMode.

## Application Object Tiers

The following table describes tiers that application objects run on.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Object</p></th>
<th><p>RunOn property</p></th>
<th><p>Comments</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Class</p></td>
<td><p>Client</p>
<p>Server</p>
<p>Called from</p></td>
<td><p>Specify the tier by setting the class RunOn property.</p></td>
</tr>
<tr class="even">
<td><p>Class instance method</p></td>
<td><p>Client</p>
<p>Server</p>
<p>Called from</p></td>
<td><p>The RunOn property value is the same as the class.</p></td>
</tr>
<tr class="odd">
<td><p>Class static method</p></td>
<td><p>Client</p>
<p>Server</p>
<p>Called from</p></td>
<td><p>You can override the RunOn property value by using server or client modifiers in the method declaration. For more information, see <a href="how-to-run-a-class-on-the-aos.md">How to: Run a Class on the AOS</a>.</p></td>
</tr>
<tr class="even">
<td><p>Form</p></td>
<td><p>Client</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>Report</p></td>
<td><p>Called from</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>Table</p></td>
<td><p>Called from</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>Table instance method</p></td>
<td><p>Called from</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>Table static method</p></td>
<td><p>Called from</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>Table kernel method (update, insert, and so on)</p></td>
<td><p>Called from (unless overridden)</p></td>
<td><p>You can override the table Called from RunOn property value by using server or client modifiers in the method declaration.</p></td>
</tr>
<tr class="even">
<td><p>Job</p></td>
<td><p>Client</p></td>
<td><p></p></td>
</tr>
</tbody>
</table>


## AOSRunMode Hints

The RunOn property value Called from is the default value for a class. It is a best practice to document that a method should run as Called from by including the following AOSRunMode hint above the code for the method.

//AOSRunMode::CalledFrom

The AOSRunMode hint helps to determine whether methods on the class are set to Called from by design or because you have not decided which tier the method should run on.

A best practice warning is generated if a method set to client makes a call to the AOS, or a method set to server makes a call to the client. If this call is required, you can suppress the best practice warning by using an AOSRunMode hint, as shown in the following code example.

// AOSRunMode:: \<tier\>

The value of \<tier\> can be server, client, or calledFrom and set to the same RunOn property value as the method. For example, a main method that runs on the server and needs to make a call to the client could use the following code.

    // AOSRunMode::server.
    public static server void main (Args args)
    {
        // ToDo Add method code here.
    }

A best practice warning is generated if the AOSRunMode hint tier does not match the method tier, as shown in the following code example.

    // AOSRunMode::client.
    public static server void main (Args args)
    {
        // ToDo Change the AOSRunMode hint to server.
    }

## See also

[AOS Overview](aos-overview.md)

[How to: Run a Class on the AOS](how-to-run-a-class-on-the-aos.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

