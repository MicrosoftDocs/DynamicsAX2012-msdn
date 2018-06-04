---
title: Method Access Control
TOCTitle: Method Access Control
ms:assetid: 7e48ea21-074a-4d95-b1bd-fb400437de38
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa676482(v=AX.60)
ms:contentKeyID: 35246120
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Method Access Control 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

In X++, you use the accessor keywords public, protected, and private to control whether the methods in other classes can call the methods on your class. The accessor keywords on methods also interact with the rules for class inheritance. The following table describes the accessor keywords you use with methods.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>public</p></td>
<td><p>Methods that are declared as public can be called from anywhere the class is accessible. In addition, a public method can be overridden by a subclass, unless the method is declared as final.</p></td>
</tr>
<tr class="even">
<td><p>protected</p></td>
<td><p>Methods that are declared as protected can be called only from the following:</p>
<ul>
<li><p>From methods in the class.</p></li>
<li><p>From methods in a subclass of the class that contains the protected method.</p>
<p>Methods that are protected can be overridden in subclasses.</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p>private</p></td>
<td><p>Methods that are declared as private can be called only from methods in the class where the private method is declared. No private method can be overridden in a subclass.</p>
<p>When you create a new method, the default accessor keyword that appears in the code editor is private. This is the most conservative default for maximum security.</p></td>
</tr>
</tbody>
</table>



> [!NOTE]
> <P>In the Application Object Tree (AOT), all classes under <STRONG>AOT</STRONG> &gt; <STRONG>Classes</STRONG> are public. Explicit use of the public keyword is recommended in the <STRONG>classDeclaration</STRONG> code block for each class, but the class is public even if the public keyword is omitted.</P>



## Static and Instance Methods

The accessor keywords on methods never restrict call between two methods that are in the same class. This is true regardless of which of the two methods are static or non-static.

In a static method, calls to the new constructor method are valid even if the new constructor method is decorated with the private modifier. The syntax for these calls requires the use of the new keyword of X++. The code in a static method must construct an instance object of its own class before the code can call any instance methods on the class.

## Increase Access When Overriding

When a method is overridden in a subclass, the overriding method must be at least as accessible as the overridden method. For example, the following X++ compiler rules apply to overriding a protected method in a subclass:

  - A public method in a superclass can be overridden only by a public method in the subclass.

  - In a subclass, a public method or a protected method can override a protected method of the superclass.

  - In a subclass, a private method cannot override a protected method of the superclass.

## Design Pattern of private new

All application classes are under **AOT** \> **Classes**. Every application class has the constructor method named new, even if the class has no **new** node in the AOT. If the class has no explicit **new** node, the implicit new method is public.

A design pattern that is sometimes used in Microsoft Dynamics AX is to declare the explicit new constructor method as private. Then a public static method is added to call the new method. The static method can restrict or control the call the new method based on various conditions, if necessary.

## See also

[Method Modifiers](method-modifiers.md)

[Declaration of Methods](declaration-of-methods.md)

[Declaration of Classes](declaration-of-classes.md)

[Methods in X++](methods-in-x.md)

[X++ Keywords](x-keywords.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

