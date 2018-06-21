---
title: Methods in X++
TOCTitle: Methods in X++
ms:assetid: 6faffa71-f7fb-4973-91ab-51c4e669e74f
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa673265(v=AX.60)
ms:contentKeyID: 35244864
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Methods in X++ [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The following blocks of code are standard for X++ application classes:

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Code block type</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>classDescription declaration block</p></td>
<td><p>Contains class modifiers such as public, private, and extends.</p>
<p>Also contains the field members for objects that are constructed from this class. IntelliSense can display a list of the members when you type the X++ keyword this.</p></td>
</tr>
<tr class="even">
<td><p>new method</p></td>
<td><p>The <a href="constructors.md">constructor</a>. This method can be called only by using the new keyword. The syntax is typically similar to:<br />
 myClassInstance = new MyClass();</p>
<p>Derived classes can call the new method of their constructor by calling super method reference.</p></td>
</tr>
<tr class="odd">
<td><p>finalize method</p></td>
<td><p>The <a href="destructors.md">destructor</a> method.</p>
<p>However, in X++ this is a destructor only by convention. The finalize method is not called automatically by the system during garbage collection.</p></td>
</tr>
</tbody>
</table>


Additional methods for a class fall into the following types:

  - Instance methods

  - Static methods

  - Main methods


> [!NOTE]
> <P>Methods can be created on many kinds of items in the AOT other than just classes. The list includes the following:</P>
> <UL>
> <LI>
> <P>Maps</P>
> <LI>
> <P>Views</P>
> <LI>
> <P>Data Sets</P>
> <LI>
> <P>Forms</P>
> <LI>
> <P>Queries</P></LI></UL>



## Instance Methods

Instance methods, or object methods, are embedded in each object that is created from the class. They are called by using the following syntax:

objectHandleName.methodName();

You must instantiate the object before you can use the method.


> [!WARNING]
> <P>If you later convert an instance method to a static method, you must restart the Microsoft Dynamics AX client for the compiler to note the change. Once you have converted the instance method to a static method, you can no longer call this method from the instance of the class -- only the class itself. Static methods are discussed in the next section.</P>



## Static Methods

Static methods, or class methods, belong to a class and are created by using the keyword static. They are called by using the following syntax:

ClassName::methodName();

You do not need to instantiate an object before you use static methods. Static methods are widely used in Microsoft Dynamics AX to work with data that is stored in tables.


> [!NOTE]
> <P>It is not possible to use member variables in a static method.</P>



For more information, see [Static Methods](static-methods.md).

## Main Methods

A main method is a class method that is executed directly from a menu option.

static void main (Args \_args)   
 {   
     // Your X++ code here.   
 }

The method should only create an instance of the object and then call the necessary member methods. The \_args parameter allows you to transfer data to the method.

For more information, see [Activating a class from a menu item](how-to-access-a-class-from-a-menu.md).

## See also

[Declaration of Methods](declaration-of-methods.md)

[Method Modifiers](method-modifiers.md)

[Overriding a Method](overriding-a-method.md)

[Best Practices for Methods](best-practices-for-methods.md)

[Table Methods](https://msdn.microsoft.com/en-us/library/aa625830\(v=ax.60\))

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

