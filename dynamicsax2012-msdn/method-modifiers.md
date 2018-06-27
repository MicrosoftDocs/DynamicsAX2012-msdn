---
title: Method Modifiers
TOCTitle: Method Modifiers
ms:assetid: fa777ae5-56e6-4851-a99e-004196c27549
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa891619(v=AX.60)
ms:contentKeyID: 35254191
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Method Modifiers 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

There are several modifiers that can be applied to [method declarations](declaration-of-methods.md). Some of the modifiers can be combined (for example, final static).

The following table describes the method modifier keywords of the X++ language.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Modifier</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>abstract</p></td>
<td><p>The method is declared but not implemented in a parent class. The method must be overridden in subclasses.</p>
<p>If you try to create an object from a subclass where one or more of the abstract methods belonging to the parent class have not been overridden, you will get a compiler error.</p>
> [!note]  
> <P>Classes can also be abstract. Sometimes a class represents an abstract concept, but it should not be instantiated: Only subclasses should be instantiated. Such base classes can be declared abstract. Consider the case where the programmer wants to model the concept of an account. Accounts are abstract—only derived classes (ledger accounts and so on) exist in the real world. This would be a clear case for declaring the Account class abstract.</P>
</td>
</tr>
<tr class="even">
<td><p>client</p></td>
<td><p>Establishes the location where the method is to be executed (on the client).</p>
<p>Can only be used on static methods. If the method is not static, specify the location by using the class property RunOn.</p></td>
</tr>
<tr class="odd">
<td><p>display</p></td>
<td><p>Indicates that the method's return value is to be displayed on a form or a report. The value cannot be altered in the form or report.</p>
<p>The return value is typically a calculated value, for example, a sum.</p>
<p>For more information about the display and edit modifiers, see <a href="using-the-display-method-modifier.md">Using the display Method Modifier</a>.</p></td>
</tr>
<tr class="even">
<td><p>edit</p></td>
<td><p>Indicates that the method's return type is to be used to provide information for a field that is used in a form. The value in the field can be edited.</p></td>
</tr>
<tr class="odd">
<td><p>final</p></td>
<td><p>Indicates that the method cannot be <a href="overriding-a-method.md">overridden</a> in any class that derives from its class.</p></td>
</tr>
<tr class="even">
<td><p>public</p></td>
<td><p>Methods that are declared as public are accessible anywhere the class is accessible and can be overridden by subclasses. Methods that have no access modifier are implicitly public.</p></td>
</tr>
<tr class="odd">
<td><p>protected</p></td>
<td><p>Methods that are declared as protected can only be called from methods in the class and in subclasses that extend the class where the method is declared.</p></td>
</tr>
<tr class="even">
<td><p>private</p></td>
<td><p>Methods that are declared as private can be called only from methods in the class where the private method is declared.</p></td>
</tr>
<tr class="odd">
<td><p>server</p></td>
<td><p>Establishes the location where the method is to be executed (on the server).</p>
<p>Can only be used on static methods. If the method is not static, you need to specify the location using the class property RunOn.</p></td>
</tr>
<tr class="even">
<td><p>static</p></td>
<td><p>Specifies that the method is a class method and does not operate on an object.</p>
<p>static methods cannot refer to instance variables and are invoked by using the class name rather than on an instance of the class (MyClass::aStaticProcedure()).</p>
<p>For more information, see <a href="static-methods.md">Static Methods</a>.</p></td>
</tr>
</tbody>
</table>


## See also

[Declaration of Methods](declaration-of-methods.md)

[Best Practices for Method Modifiers](best-practices-for-method-modifiers.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

