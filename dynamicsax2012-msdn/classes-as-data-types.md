---
title: Classes as Data Types
TOCTitle: Classes as Data Types
ms:assetid: f1a4424e-9277-499c-ae04-c0d22708ecce
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa886489(v=AX.60)
ms:contentKeyID: 35253385
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Classes as Data Types 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Every application class in the Application Object Tree (AOT) under the **Classes** node is a data type in X++. You can declare variables of these types in your X++ code. You can construct instances of a class and assign the instances to variables. The instances are also known as objects.

## Class Elements in the AOT

Under most class nodes there are two special nodes, and these are described in the following table.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Node name</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>classDeclaration</strong></p></td>
<td><p>Contains the X++ class keyword. It can also have additional keywords such as extends to modify the class.</p>
<p>This node can also contain declarations of member variables. The member variables cannot be initialized to a value in classDeclaration. The member variables cannot be static. In the following example the variables m_priority and m_rectangle are members of the class.</p>
<p>public class YourDerivedClass extends YourBaseClass <br />
 { <br />
     int m_priority; <br />
     Rectangle m_rectangle; <br />
 }</p></td>
</tr>
<tr class="even">
<td><p><strong>new</strong></p></td>
<td><p>Contains X++ logic that is run when the new operator is used to create an instance of the class. The logic in the new method might construct an object, and assign the object to a variable that is declared in the classDeclaration. Each class is limited to only one new method. However, in the new method you often should call the new method of the base class, and you do so by calling super().</p>
<p>The following example is the new method for the YourDerivedClass class in the previous classDeclaration example. In this new method, the X++ code constructs an instance of the Rectangle class. The instance is assigned to the m_rectangle variable.</p>
<p>void new(int _length, int _width) <br />
 { <br />
     this.m_rectangle = new Rectangle(_length, _width); <br />
 }</p>
<p>The this keyword is optional, although in practice it sometimes enables IntelliSense to be more helpful.</p></td>
</tr>
</tbody>
</table>


## Garbage Collection

During run time, most objects eventually no longer have any variable pointing to them. The system scans for such objects and erases them from memory. This makes the memory space available for other uses.

The Object class has a method named finalize. However, the finalize method is not a destructor. The Microsoft Dynamics AX system never calls the finalize method, even when an object is garbage collected.

## System Classes

In the AOT under **System Documentation** \> **Classes** you can see a list of the kernel or system classes. System classes are not written in X++, and you cannot see their source code. You cannot add any system classes.

System classes usually have a new method, but they do not have a classDeclaration node. Every application class implicitly extends the Object system class.

Some system classes are extended by an application class of nearly the same name. For instance, xClassFactory is extended by ClassFactory. In such cases you should not use the system class. For more information, see [Substitute Application Classes for System Classes](substitute-application-classes-for-system-classes.md).

## See also

[Classes in X++](classes-in-x.md)

[Primitive Data Types](primitive-data-types.md)

[Composite Data Types](composite-data-types.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

