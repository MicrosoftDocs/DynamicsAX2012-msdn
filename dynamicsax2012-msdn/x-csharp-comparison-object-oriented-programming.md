---
title: 'X++, C# Comparison: Object Oriented Programming'
TOCTitle: 'X++, C# Comparison: Object Oriented Programming'
ms:assetid: a1a5d850-438a-4385-ba70-71b581d9ccf6
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Dd261515(v=AX.60)
ms:contentKeyID: 35248308
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# X++, C\# Comparison: Object Oriented Programming [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The object oriented programming (OOP) principles of X++ differ from C\#.

## Conceptual Comparisons

The following table compares the implementation of OOP principles between Microsoft Dynamics AX X++ and C\#.

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Feature</p></th>
<th><p>X++</p></th>
<th><p>C#</p></th>
<th><p>Comments</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Casting</p></td>
<td><p>Starting with Microsoft Dynamics AX 2012 the X++ language has the keywords is and as, which are used to make downcasts safe and explicit.</p>

> [!note]  
> <P>In Microsoft Dynamics AX 2012 the X++ language does not require the use of the as keyword when you downcast a base class variable to a derived class variable. However, we recommend that all downcast statements use the as keyword.</P>

</td>
<td><p>An object can be cast either up or down the inheritance path. Downcasts require the as keyword.</p></td>
<td><p>For more information about the X++ keywords is and as, see <a href="expression-operators-is-and-as-for-inheritance.md">Expression Operators: Is and As for Inheritance</a>.</p></td>
</tr>
<tr class="even">
<td><p>Local functions</p></td>
<td><p>A method can contain a declaration and code body for zero or more local functions. Only that method can have calls to the local function.</p></td>
<td><p>C# 3.0 supports lambda expressions, which have some similarity to anonymous functions and local functions. Lambda expressions are often used with delegates.</p></td>
<td><p>For more information about local functions in X++, see <a href="local-functions.md">Local Functions</a>.</p></td>
</tr>
<tr class="odd">
<td><p>Method overloading</p></td>
<td><p>Method overloading is not supported. A method name can occur only one time per class.</p></td>
<td><p>Method overloading is supported. A method name can occur multiple times in one class, with different parameter signatures in each case.</p></td>
<td><p>X++ does support optional parameters on methods. Optional parameters can partially mimic method overloading. For more information, see the row for optional parameters in this table.</p></td>
</tr>
<tr class="even">
<td><p>Method overriding</p></td>
<td><p>Method overriding is supported. A derived class can have a method by the same name as in the base class, as long as the parameter signature is the same in both cases. The only exception is that the overriding method can add a default value to a parameter.</p></td>
<td><p>Method overriding is supported. The virtual keyword must be applied to a method before the method can be overridden in a derived class.</p></td>
<td><p>The concept of overriding a method includes the method name, its parameter signature, and its return type. The concept of method overriding does not apply if the base method and the overriding method differ in any of these aspects.</p></td>
</tr>
<tr class="odd">
<td><p>Optional parameters</p></td>
<td><p>A parameter declaration can be followed by a default value assignment. The method caller has the option of passing a value for that parameter, or ignoring the parameter to accept the default value. This feature mimics method overloading because two calls to the same method name can pass different numbers of parameters.</p>
<p>Each parameter that has a default value must follow the last parameter that does not have a default value.</p></td>
<td><p>Optional parameters are supported by the params keyword. Even without the params keyword, from the point of view of the caller, method overloading can provide partially similar functionality.</p></td>
<td><p>For more information, see <a href="parameters-and-scoping.md">Parameters and Scoping</a> and <a href="using-optional-parameters.md">Using Optional Parameters</a>.</p></td>
</tr>
<tr class="even">
<td><p>Single inheritance</p></td>
<td><p>You can derive your X++ class from another X++ class by using the extends keyword in the <strong>classDeclaration</strong> node of your class, in the AOT. No class implicitly derives directly from another class. If you want your class to directly derive from the Object class, you must use the extends keyword. You can specify only one class on the extends keyword.</p>

> [!caution]  
> <P>When you modify an X++ base class that other classes derive from, you must recompile that base class using the <strong>Compile forward</strong>. This option ensures that the derived classes are also recompiled. To ensure the derived classes are also recompiled, right-click the base class node, and then click <strong>Add-Ins</strong> &gt; <strong>Compile forward</strong>. The alternative of clicking <strong>Build</strong> &gt; <strong>Compile</strong> (or pressing the F7 key) is sometimes insufficientfor a base class change.</P>

<p>A class can implement zero to many interfaces.</p>
<p>An X++ table implicitly inherits from the Common table, and from the xRecord class.</p></td>
<td><p>C# uses the extends keyword to derive from another class. All .NET Framework classes implicitly derive from the System.Object class, unless they explicitly derive from another class.</p></td>
<td><p>For more information about X++ interfaces, see <a href="interfaces-overview.md">Interfaces Overview</a>.</p></td>
</tr>
</tbody>
</table>


## Keyword Comparisons

The following table lists the OOP-related keywords in X++. The usage of each keyword is compared between X++ and C\#.

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Keyword</p></th>
<th><p>X++</p></th>
<th><p>C#</p></th>
<th><p>Comments</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>abstract</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p>No difference.</p></td>
</tr>
<tr class="even">
<td><p>class</p></td>
<td><p>The modifiers public and private are ignored on class declarations.</p>
<p>There is no concept of a namespace grouping of classes. There are no dots (.) in any class names.</p></td>
<td><p>The modifiers public and private can be used to modify class declarations. C# also has the keyword internal, which relates to how classes are grouped together in assembly files.</p></td>
<td><p>There is no concept of a protected class, only protected members of a class.</p></td>
</tr>
<tr class="odd">
<td><p>extends</p></td>
<td><p>A class declaration can inherit from another class by using the extends keyword.</p></td>
<td><p>A colon (:) is used where the keywords extends and implements are used in X++.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>final</p></td>
<td><p>A final method cannot be overridden in a derived class. A final class cannot be extended.</p></td>
<td><p>The keyword sealed on a class means the same thing that final means on an X++ class.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>implements</p></td>
<td><p>A class declaration can implement an interface by using the implements keyword.</p></td>
<td><p>(See extends.)</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>interface</p></td>
<td><p>An interface can specify methods that the class must implement.</p></td>
<td><p>An interface can specify methods that the class must implement.</p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p>new</p></td>
<td><p>The new keyword is used to allocate a new instance of a class. Then the constructor is automatically called.</p>
<p>Each class has exactly one constructor, and the constructor is named new. You can decide what parameters the constructor should input.</p></td>
<td><p>The new keyword is used to create a new instance of a class. Then the constructor is automatically called.</p>
<p>Constructor methods themselves are not named new, they have the same name as the class.</p>

> [!note]  
> <P>The new keyword can also be used on a method, to modify the way in which the method overrides the same method in the base class.</P>

</td>
<td><p>Both X++ and C# assume a default constructor for classes that have no constructor explicitly written in their code.</p></td>
</tr>
<tr class="even">
<td><p>null</p></td>
<td><p></p></td>
<td><p></p></td>
<td><p>No difference.</p></td>
</tr>
<tr class="odd">
<td><p>private and protected</p></td>
<td><p>The private and protected keywords can be used to modify the declaration of a class member.</p></td>
<td><p>The private and protected keywords can be used to modify the declaration of a class member.</p></td>
<td><p>For more information, see <a href="method-access-control.md">Method Access Control</a>.</p></td>
</tr>
<tr class="even">
<td><p>public</p></td>
<td><p>A method that is not modified with public, protected, or private has the default access level of public.</p></td>
<td><p>A method that is not modified with public, protected, or private has the default access level of private.</p></td>
<td><p>(For more information, see private.)</p></td>
</tr>
<tr class="odd">
<td><p>static</p></td>
<td><p>A method can be static, but a field cannot.</p></td>
<td><p>Both methods and fields can be static.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>super</p></td>
<td><p>The super keyword is used in a derived class to access the same method on its base class.</p>
<p>void method2()</p>
<p>{</p>
<p>;</p>
<p>// Call method2 method</p>
<p>// on the base class.</p>
<p>super();</p>
<p>}</p></td>
<td><p>The base keyword is used in a derived class to access various methods in its base class.</p>
<p>void method2()</p>
<p>{</p>
<p>// Call methods on</p>
<p>// the base class.</p>
<p>base.method2();</p>
<p>base.method3();</p>
<p>}</p></td>
<td><p>In C#, there is special syntax for using base to call the base constructor.</p></td>
</tr>
<tr class="odd">
<td><p>this</p></td>
<td><p>For a call from one instance method to another on the same object, a qualifier for the called method is required. The keyword this is available as a qualifier for the current object.</p></td>
<td><p>For a call from one instance method to another on the same object, a qualifier for the called method is not required. However, the this keyword is available as a qualifier for the current object. In practice, the keyword this can be helpful by displaying IntelliSense information.</p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p>finalize</p></td>
<td><p>The Object class contains the finalize method. The finalize method is not final, and it can be overridden.</p>
<p>The finalize method appears to resemble the System.Object.Finalize method in C#, but in X++ the finalize method has no special meaning of any kind.</p>
<p>An object is automatically removed from memory when the last reference to the object stops referencing the object. For example, this can happen when the last reference goes out of scope or is assigned another object to reference.</p></td>
<td><p>The methods Finalize and Dispose are common on some types of classes.</p>
<p>The garbage collector calls the Finalize and Dispose methods when it destroys and object.</p></td>
<td><p>In C#, the System.GC.Collect method in the .NET Framework can be called to start the garbage collector. There is no similar function in X++ because X++ uses a deterministic garbage collector.</p></td>
</tr>
<tr class="odd">
<td><p>main</p></td>
<td><p>Classes that are invoked from a menu have their main method called by the system.</p></td>
<td><p>Classes that are invoked from a command line console have their Main method called by the system.</p></td>
<td><p></p></td>
</tr>
</tbody>
</table>


## See also

[X++, C\# Comparisons](x-csharp-comparisons.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

