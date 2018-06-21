---
title: Best Practices for Class Declarations
TOCTitle: Class Declarations
ms:assetid: c193e441-c405-4aa7-b965-e3da20989c65
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa864036(v=AX.60)
ms:contentKeyID: 35250086
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Best Practices for Class Declarations [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

## Class Properties

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
<td><p>Name</p></td>
<td><p>Prefix: Module short name, for example InventUpdate.</p>
<p>Infix: Logical description of action performed or type of contents, for example InventUpdate.</p>
<p>Follow the general <a href="naming-conventions.md">Naming Conventions</a>.</p>
<p>Avoid naming classes that are the basis for a subsystem hierarchy with a Base suffix if the class is intended for use in public APIs. This practice follows the design guidelines for the .NET Framework. For more information, see <a href="http://go.microsoft.com/fwlink/?linkid=202927">Base Classes for Implementing Abstractions</a>.</p>
<p>If you try to create a class with a name that has already been used for a class in the previous version of Microsoft Dynamics AX, you will get an error. <img src="images/Aa872655.ErrorIcon(AX.60).gif" title="Error icon" alt="Error icon" /></p></td>
</tr>
</tbody>
</table>


## Class Declaration Layout

\[public\] \[final\] class ClassName \[extends SuperClassName\] \[implements interface1\[, interface2 ..\]\]

## Object Member Variables

Object member variables are variables in the class declaration. Create them only if the variable cannot be created in a method. Object member variables must be the variables holding the state of the object.


> [!TIP]
> <P>Do not create object member variables that do not hold the state of the object. Pass these values as arguments.</P>
> <P>Do not create an object member only because a variable of that type and name is needed in more than one method in the object. Create the variable in each place it is needed. <SPAN id=rx81unusedvar></SPAN></P>



## Clean Up Unused Variables

Clean up unused variables in your class declaration. Right-click the class in the application object tree (AOT) and choose **Add-Ins** \> **Check Best Practices**. ![Error icon](images/Aa872655.ErrorIcon(AX.60).gif "Error icon")

## Class-Wide Constants

If you have to declare some constants that will be used in more than one method in the class or its subclasses, declare these constants in the class declaration (by using the \#define technique).

## See also

[Best Practices for Constructors](best-practices-for-constructors.md)

[Best Practice for Destructors (finalize)](best-practice-for-destructors-finalize.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

