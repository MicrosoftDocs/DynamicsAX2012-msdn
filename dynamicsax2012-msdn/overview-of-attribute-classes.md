---
title: Overview of Attribute Classes
TOCTitle: Overview of Attribute Classes
ms:assetid: ce06a4b1-2ae1-4250-8114-8e662bc61b6a
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg864301(v=AX.60)
ms:contentKeyID: 35251708
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Overview of Attribute Classes [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

In X++, any class that inherits from the SysAttribute class is called an attribute. The purpose of an attribute is to represent or store metadata about types and methods. An attribute can be attached to the definition of the following items:

  - Interface

  - Class

  - Method
    
      - Method on an interface
    
      - Method on a class
    
      - Method on a table

The system provides several attributes, including the SysObsoleteAttribute class. One use of the SysObsoleteAttribute class is to tell the X++ compiler that the compile should fail if a particular method is called in the source code. The X++ compiler rejects the compile, and it displays the specific message that is stored in this use of the attribute.

## SysObsoleteAttribute

The system provides several attributes, including the [SysObsoleteAttribute](https://msdn.microsoft.com/en-us/library/gg962438\(v=ax.60\)) class. One use of the SysObsoleteAttribute class is to tell the X++ compiler that it should fail if a particular method is called in the source code. The X++ compiler rejects the compile, and it displays the specific message that is stored in this use of the attribute. The SysObsoleteAttribute class can also be used to tell the compiler to issue warning messages instead of errors.

### ![Gg864301.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg864301.collapse_all(en-us,AX.60).gif")Code Example

    // X++
    [SysObsoleteAttribute("The Automobile class might be a better choice for faster performance.", false)]
    class Bicycle
    {
        // Members of the Bicycle class go here.
    }

## Reflection on Attribute Metadata

You can perform reflection to find the attribute metadata that is attached to a class. The classes to use for attribute reflection are as follows:

  - [DictClass Class](https://msdn.microsoft.com/en-us/library/gg837663\(v=ax.60\)) – for classes and interfaces.

  - [DictMethod Class](https://msdn.microsoft.com/en-us/library/gg842356\(v=ax.60\)) – for methods on classes, interfaces, or tables.

On the previous reflection classes, the methods for reflecting on attribute metadata are as follows:

  - getAllAttributes method

  - getAttribute method

  - getAttributedClasses method

  - getAttributes method

For more information, see [How to: Use Reflection to Get Attribute Class Metadata](how-to-use-reflection-to-get-attribute-class-metadata.md).

## See also

[Attributes on X++ Types and Methods](attributes-on-x-types-and-methods.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

