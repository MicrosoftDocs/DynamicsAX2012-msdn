---
title: X++ Language Syntax is Stricter in Microsoft Dynamics AX 2012
TOCTitle: X++ Language Syntax is Stricter in Microsoft Dynamics AX 2012
ms:assetid: 52e99f3e-8e76-4144-bbbd-5c5f21644329
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg845659(v=AX.60)
ms:contentKeyID: 35244323
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# X++ Language Syntax is Stricter in Microsoft Dynamics AX 2012 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Starting in Microsoft Dynamics AX 2012, the syntax rules for X++ are stricter than in previous versions of the product. This topic describes the syntax changes.

## Table of X++ Syntax Changes

The following table displays a list of syntax changes that start in Microsoft Dynamics AX 2012.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Area</p></th>
<th><p>Syntax rule</p></th>
<th><p>Before Microsoft Dynamics AX 2012</p></th>
<th><p>Starting with Microsoft Dynamics AX 2012</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Escape</p></td>
<td><p>The backslash character \ is rejected by the compiler for unrecognized escapes</p></td>
<td><p>The compiler used to accept &quot;31\12\2002&quot;, but during run time the literal string was interpreted as a different value.</p></td>
<td><p>Now the following X++ statement is rejected by the compiler:</p>
<p>str myDateString = &quot;31\12\2002&quot;;</p>
<p>The proper syntax is &quot;31\\12\\2002&quot;.</p></td>
</tr>
<tr class="even">
<td><p>Exceptions</p></td>
<td><p>Retry is no longer allowed outside of a catch block</p></td>
<td><p>It was possible to write the retry keyword outside of a catch block. This caused the program to end when the retry was reached during runtime.</p></td>
<td><p>Now retry can occur only inside a catch block. For more information, see <a href="exception-handling-with-try-and-catch-keywords.md">Exception Handling with try and catch Keywords</a>.</p></td>
</tr>
<tr class="odd">
<td><p>Exceptions</p></td>
<td><p>Now you can throw and catch only int values</p></td>
<td><p>It was possible to throw scalar expressions like strings and dates, such as throw &quot;hello world&quot;;, and get no compile error. At runtime this was catch-able by a catch block that was not decorated with any specific value, such as catch {print(&quot;Catch worked.&quot;);}.</p></td>
<td><p>Now the only expression you can put on the throw keyword is an int.</p>
<p>Often the best thing to throw is Global::error(&quot;Explanation&quot;);. Often the best thing to catch is an element of the Exception enum. For more information, see <a href="exception-handling-with-try-and-catch-keywords.md">Exception Handling with try and catch Keywords</a>.</p></td>
</tr>
<tr class="even">
<td><p>Inheritance</p></td>
<td><p>Downcasting can now be explicit.</p>
<div class="mtps-table">
<div class="mtps-row">
<img src="images/Aa589339.alert_note(en-us,AX.60).gif" title="Note" alt="Note" class="note" /><strong>Note</strong>
</div>
<div class="mtps-row">
<br />
It is good programming practice to avoid implicit downcasts.<br />
</div>
</div></td>
<td><p>It was possible to assign a base object to a derived object with the simple assignment operator, which is the equals sign (=). The compiler accepted these assignments, but during run time any misuse of an improper downcast assignment caused an error.</p></td>
<td><p>Now all downcasts can be explicit. This is accomplished with the new as expression operator. Explicit downcasting with the as keyword is illustrated by the following code example, in which ThingClass extends Object:</p>
<p><br />
 ThingClass myThing = new ThingClass(); <br />
 Object myObject = myThing; <br />
 myThing = myObject as ThingClass; // Explicit downcast, good.</p>
<p>For more information, see <a href="expression-operators-is-and-as-for-inheritance.md">Expression Operators: Is and As for Inheritance</a>.</p></td>
</tr>
<tr class="odd">
<td><p>Inheritance</p></td>
<td><p>Override of a base method cannot be less accessible than the base method</p></td>
<td><p>It was possible to have a base method be decorated with protected and yet have an override of that method be private.</p></td>
<td><p>Now when a base method is protected, the override method must be either protected or public, and the override method cannot be private. For more information, see <a href="method-access-control.md">Method Access Control</a>.</p></td>
</tr>
<tr class="even">
<td><p>Inheritance</p></td>
<td><p>Override of a base method must have the exact same return type and parameter signature as the base method</p></td>
<td><p>Suppose a base class had a method that inputs a parameter of the Common table, which is the base of all tables. In a derived class it was possible to override the method to instead input MyTable.</p></td>
<td><p>Now the parameter signatures of the base method and its override method must match exactly. Also, the return types must match exactly. For more information, see <a href="overriding-a-method.md">Overriding a Method</a>.</p></td>
</tr>
<tr class="odd">
<td><p>Interfaces</p></td>
<td><p>Implementation of an interface method must match the parameter signature exactly</p></td>
<td><p>Suppose an interface had a method that input a parameter of an int. In a class that implements the interface, it was possible to write the method with a parameter of a str.</p></td>
<td><p>Now the parameter signatures of the method must exactly match between the interface and the implementation of the method on a class. Also, the return types must match exactly. For more information, see <a href="interfaces-overview.md">Interfaces Overview</a>.</p></td>
</tr>
<tr class="even">
<td><p>Interfaces</p></td>
<td><p>A non-abstract base class that implements an interface cannot rely on a derived class for that implementation</p></td>
<td><p>When a base class implements an interface, it was possible for the class to not implement the methods of the interface if a derived class implemented the methods. The only limitation was that the new constructor method could not be called on the class.</p></td>
<td><p>Now the compiler requires that every class that implements an interface must have or inherit a complete implementation of every method of the interface. For more information, see <a href="x-csharp-comparison-object-oriented-programming.md">X++, C# Comparison: Object Oriented Programming</a>.</p></td>
</tr>
<tr class="odd">
<td><p>Modifiers</p></td>
<td><p>The static modifier should not be applied to an interface</p></td>
<td><p>It was possible to write static interface IMyInterface {}, but the static modifier had no effect because it makes no sense in this context.</p></td>
<td><p>Sometime after Microsoft Dynamics AX 2009 the X++ compiler might stop allowing the static modifier on interface declarations. For more information, see <a href="interfaces-overview.md">Interfaces Overview</a>.</p></td>
</tr>
<tr class="even">
<td><p>Modifiers</p></td>
<td><p>The static modifier must not be applied to the new constructor</p></td>
<td><p>It was possible to apply the static modifier to the declaration of the new constructor method. This caused new MyClass(); to behave as a null operation. Instead, the statement MyClass::new(); would call the static new method, but that would not construct an object.</p></td>
<td><p>Now the compiler issues an error when the static modifier is applied to the new method. For more information, see <a href="constructors.md">Constructors</a>.</p></td>
</tr>
<tr class="odd">
<td><p>Modifiers</p></td>
<td><p>Use an explicit access modifier on each method</p></td>
<td><p>In the past the menu item of <strong>AOT</strong> &gt; <strong>Classes</strong> &gt; MyClass &gt; <strong>New Method</strong> created the method without any access modifier. This meant that the method was implicitly public, although some X++ developers might not have been fully aware of the default. This created extra work later when a developer needed to modify the code in the method, because the developer had to research everywhere that the method might be called from.</p></td>
<td><p>Now the <strong>New Method</strong> menu item explicitly includes the private keyword in its automatic declaration of the new method. The developer can type in a different modifier if appropriate. For more information, see <a href="method-modifiers.md">Method Modifiers</a>.</p></td>
</tr>
<tr class="even">
<td><p>Parameters</p></td>
<td><p>Parameters given in a call to a new constructor method must match the parameters on the new constructor method</p></td>
<td><p>It was possible to pass in multiple parameters on call to a new constructor method even when the new method was declared to input no parameters.</p></td>
<td><p>Now the call to the new method must exactly match the declared parameter signature of the new method. For more information, see <a href="creating-a-subclass.md">Creating a Subclass</a>.</p></td>
</tr>
<tr class="odd">
<td><p>Parameters</p></td>
<td><p>Parameters with default values must come after all parameters that do not have default values</p></td>
<td><p>It was possible to declare a method that takes in two parameters, and have only the first parameter offer a default value. There was no purpose to this. There was no way to accept the default of the first parameter because the call must specify a value for the second parameter and cannot omit the first parameter.</p></td>
<td><p>Now in the declaration of a method, any parameter that offers a default value must come after all the parameters that do not. For more information, see the following topics:</p>
<ul>
<li><p><a href="using-optional-parameters.md">Using Optional Parameters</a></p></li>
<li><p><a href="best-practices-for-parameters.md">Best Practices for Parameters</a></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Parameters</p></td>
<td><p>Override of a method must have the same default parameters as the overridden method</p></td>
<td><p>It was possible to declare a method as public void myMethod(int i=22){} and the override as public void myMethod(){}. But if the override method was called as derivedObject(333); an error occurred.</p></td>
<td><p>Now the override method must list the same parameter types in the same sequence that they are declared in the overridden method. For more information, see <a href="overriding-a-method.md">Overriding a Method</a>.</p></td>
</tr>
<tr class="odd">
<td><p>Preprocessor</p></td>
<td><p>A TODO in a comment must be the first non-whitespace in the first line of the comment</p></td>
<td><p>The X++ preprocessor used to detect the TODO keyword in a multi-line /* ... */ task comment even when the TODO appeared after other text after the first comment line.</p></td>
<td><p>Now the X++ preprocessor detects the TODO keyword only if TODO appears on the first line of the comment, and as the first non-whitespace in the comment. For more information, see <a href="todo-comments-for-x-developer-tasks.md">TODO Comments for X++ Developer Tasks</a>.</p></td>
</tr>
</tbody>
</table>


## See also

[X++ Syntax](x-syntax.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

