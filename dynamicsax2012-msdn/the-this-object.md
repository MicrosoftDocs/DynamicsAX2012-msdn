---
title: The this Object
TOCTitle: The this Object
ms:assetid: 621a4977-7604-44c3-b57c-3a15d0aadd89
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa633089(v=AX.60)
ms:contentKeyID: 35244551
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# The this Object 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

In an X++ method, the keyword this is a reference to the instance of the class or table in which the this keyword is used. The this reference is never required, but it can clarify your code, and it enhances the behavior of IntelliSense in the code editor.

The this reference can be used in the following ways:

  - Can be used to qualify the names of other instance (non-static) methods in the same class where the this reference is used. For example:  
     boolColorChanged = this.colorItOrange();
    

    > [!NOTE]
    > <P>In X++ all calls to instance methods must be qualified, either with the this reference or with a variable.<BR>In contrast, C# does not always require such qualification.</P>



  - Can be used to quality the names of methods that are inherited by the this object.

  - Can be used to qualify the names of fields on the table that contains the method that the this keyword is used in.

The this reference cannot be used in the following ways:

  - Cannot be used to qualify the names of member variables that are declared in the classDeclaration code.  
    C\# allows such qualification.

  - Cannot be used in a static method.

  - Cannot be used to qualify the names of static methods of the class or table.

## See also

[Methods in X++](methods-in-x.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

