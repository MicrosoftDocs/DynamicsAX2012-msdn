---
title: 'Naming Conventions: Methods'
TOCTitle: Naming Conventions for Methods
ms:assetid: e5365e4b-152c-4be7-b15e-54b3e9b2cc20
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa880770(v=AX.60)
ms:contentKeyID: 35253199
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Naming Conventions: Methods [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Write a clear, descriptive name for your method. If one cannot be found, consider splitting it up.

Use the [general name standards](naming-conventions.md), and the following preferred names for methods.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Name</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>check*</p></td>
<td><p>A Boolean method that checks a condition. If the condition is not fulfilled, it must put a warning on the Infolog, and return false.</p></td>
</tr>
<tr class="even">
<td><p>exist</p></td>
<td><p>Returns a Boolean that is true if a record with the supplied key exists, see <a href="static-exist-method-design-pattern.md">static exist Method Design Pattern</a>.</p>
<p>Typical use: Table static method.</p></td>
</tr>
<tr class="odd">
<td><p>find</p></td>
<td><p>Returns a record indicated by the supplied key.</p>
<p>Typical use: Table static method.</p></td>
</tr>
<tr class="even">
<td><p>find*</p></td>
<td><p>Finds a record in the table (where the method is declared). The postfix is the name of the field which is used for accessing the table, or a logical name for more fields.</p>
<p>Typical use: Table static method.</p></td>
</tr>
<tr class="odd">
<td><p>initFromTableName</p></td>
<td><p>This buffer is initialized with values from the buffer supplied.</p>
<p>One argument, which is a buffer of the same type as that named in the method.</p>
<p>Typical use: Table instance method.</p></td>
</tr>
<tr class="even">
<td><p>initParm</p></td>
<td><p>Used for methods that set member variables. If the method only sets some of the variables, indicate this in a prefix to the name, for example initParmVersDate.</p></td>
</tr>
<tr class="odd">
<td><p>is*</p></td>
<td><p>A Boolean method that will check some condition. If the condition is not fulfilled, it must return false. is* cannot change the method. Information must not be sent to the Infolog.</p></td>
</tr>
<tr class="even">
<td><p>parmMemberVariableName</p></td>
<td><p>Methods used for setting and getting the value of a member variable as a part of an object initialization. The method should have the same name as the variable, prefixed with parm.</p></td>
</tr>
<tr class="odd">
<td><p>set*</p></td>
<td><p>Used for methods that set value(s) in the object. The name must make it clear that the method also sets the state of some other global members. set* methods should be void or Boolean, signaling the result of the set.</p></td>
</tr>
<tr class="even">
<td><p>updateFieldName</p>
<p>createFieldName</p></td>
<td><p>If a method updates or creates a record, reflect that in the name, rather than calling the method set FieldName.</p></td>
</tr>
<tr class="odd">
<td><p>validate*</p></td>
<td><p>Same as check*.</p></td>
</tr>
</tbody>
</table>



> [!NOTE]
> <P>Methods that have the names listed in the preceding table must carry out the tasks described, and must not have any additional functionality. For example, there must be no assignments in a validate, check*, or is* method.</P>



## See also

[Best Practices for Methods](best-practices-for-methods.md)

[Best Practices for Parameters](best-practices-for-parameters.md)

[Best Practices for Table Methods](best-practices-for-table-methods.md)

[Best Practices for Local Functions](best-practices-for-local-functions.md)

[Best Practices for Method Modifiers](best-practices-for-method-modifiers.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

