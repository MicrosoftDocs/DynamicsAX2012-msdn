---
title: Overview of Security Policies for Table Records
TOCTitle: Overview of Security Policies for Table Records
ms:assetid: c726332f-48a4-4b00-a9ef-441e7e3b970e
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh272123(v=AX.60)
ms:contentKeyID: 36536909
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Overview of Security Policies for Table Records [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Security policies enable developers and administrators to block access to subsets of data rows in tables. A policy is roughly similar to a where clause in an SQL select statement. A security permission increases the access a user has to data, but a security policy decreases access to data.

In the Application Object Tree (AOT), policies are displayed under **Security** \> **Policies**.

Security policies are enforced in the Application Object Server (AOS). All access mechanisms that route through the AOS are subject to policy enforcement. These access mechanisms include forms, Enterprise Portal webpages, SSRS reports, and calls from class methods.

## An Extensible Data Security Model

Microsoft Dynamics AX uses an extensible data security (XDS) model. XDS extends data security from a single table to the tables and views that contain related data.

Security policies are part of an overall extensible data security model. The conceptual model in the following illustration shows the influence of context on security policies.

![AOTXDSConceptualModel](images/Hh272123.AOTXDSConceptualModel(en-us,AX.60).jpg "AOTXDSConceptualModel")

**The conceptual model of extensible data security**

The following table defines the concepts of the XDS model.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Concept</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Constrained tables and views</p></td>
<td><p>A security policy could constrain the data access of the <strong>SalesTable</strong> to only those records that have one particular <strong>CustAccount</strong> foreign key value. You can define constrained tables and views in the AOT at <strong>Security</strong> &gt; <strong>Policies</strong> &gt; YourPolicy &gt; <strong>Constrained Tables</strong>.</p></td>
</tr>
<tr class="even">
<td><p>Primary table</p></td>
<td><p>You can use a primary table to secure the content of the related constrained table. For example, in a policy that secures all sales orders based on the <strong>CustGroup</strong> foreign key value, the <strong>Customer</strong> table would be the primary table.</p></td>
</tr>
<tr class="odd">
<td><p>Policy query</p></td>
<td><p>You can define a policy query by specifying a value for the <strong>Query</strong> property in the AOT at <strong>Security</strong> &gt; <strong>Policies</strong> &gt; YourPolicy. You can use a policy query to secure the constrained tables specified in a given security policy. The query selects data from a primary table. The values in that data are then used to restrict the data returned from the constrained table.</p></td>
</tr>
<tr class="even">
<td><p>Context</p></td>
<td><p>A policy context controls the circumstances under which a given policy applies. The policy is not enforced unless the context is set.</p>
<p>The types of policy contexts are as follows:</p>
<ul>
<li><p><strong>Role context</strong> – can enable policies that are based on the roles to which the user is assigned.</p></li>
<li><p><strong>Application context</strong> – can enable policies that are based on information which is set by the application.</p></li>
</ul>
<p>For more information about policy contexts, see <a href="security-policies-properties.md">Security Policies Properties</a>.</p></td>
</tr>
</tbody>
</table>


## See also

[Security Policies Properties](security-policies-properties.md)

[Walkthrough: Creating a Simple Default Security Policy](walkthrough-creating-a-simple-default-security-policy.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

