---
title: Syntax for Attribute Classes
TOCTitle: Syntax for Attribute Classes
ms:assetid: 2130208b-9e50-4313-9f12-bc6903f11e41
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg844185(v=AX.60)
ms:contentKeyID: 35241550
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Syntax for Attribute Classes 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

An attribute class is any non-abstract class that inherits from the SysAttribute class. An attribute class can extend directly from the SysAttribute class, or it can extend from any descendent of the SysAttribute class.

The SysAttribute class cannot be used as an attribute because it is declared abstract.

## Syntax for Defining an Attribute Class

The following example shows the declaration and design of an ordinary attribute class that you could create.
```X++
    public class PracticeAttribute extends SysAttribute
    {
        // Fields in the classDeclaration.
        StartEnd startEndEnum;
        str reason;
    
        // Constructor.
        public void new(StartEnd _startEndEnum, str _reason)
        {
            startEndEnum  = _startEndEnum;
            reason = _reason;
        }
    
        // Other methods can go here.
    }
```
## Syntax for Decorating a Class

The following example shows a class and a method that are decorated with the PracticeAttribute given in the previous example.
```X++
    [PracticeAttribute(StartEnd::End, "Use the RegularClass class at the end.")]
    public class RegularClass
    {
        [PracticeAttribute(Startend::Start, "Use the rehearse method at the start.")]
        public int rehearse()
        {
            // Logic goes here.
        }
        // More fields and methods belong here.
    }
```
If the constructor of the attribute takes no parameters, the parentheses for the parameters are optional. The attribute decoration could be \[ AnotherAttribute \] without parentheses.

## The Attribute Constructor and its Role

You can enable your attribute class to store tailored metadata each time it is used to decorate a class, by having its constructor take parameters. The parameters for the constructor must be literals of the primitive types, such as int or enum or str.

The X++ compiler does not construct an instance of the attribute class. It stores the name of the attribute class, plus the literal values for its constructor. Therefore, if the logic in an attribute constructor would throw an exception, the exception would not be found by decorating a class with the attribute. The exception would be found later when a process looks at a class to see the attribute it is decorated with. That is when the attribute is constructed.

## Naming Convention

All attribute classes in Microsoft Dynamics AX have the suffix Attribute in their name. The Attribute suffix is the name convention that we recommend, but it is not a system requirement.

A few classes that were added in early versions of Microsoft Dynamics AX might have the Attribute suffix even though they are not attribute classes.


> [!TIP]
> <P>You can determine whether a class extends directly from SysAttribute by looking at <STRONG>AOT</STRONG> &gt; <STRONG>Classes</STRONG> &gt; TheClassName &gt; <STRONG>classDeclaration</STRONG> &gt; <STRONG>Edit</STRONG>. There you can see whether the code includes extends SysAttribute. Or the class might extend from another class that directly extends SysAttribute.</P>



## See also

[Attributes on X++ Types and Methods](attributes-on-x-types-and-methods.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

