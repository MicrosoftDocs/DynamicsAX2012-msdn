---
title: Destructors
TOCTitle: Destructors
ms:assetid: f127fed6-d63a-419f-aed4-6bb8c0a6b281
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa886274(v=AX.60)
ms:contentKeyID: 35253335
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Destructors [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

A destructor is used to explicitly destroy a class object.

X++ objects are destructed automatically when there are no more references to them. You can destruct them explicitly in the following ways:

  - Use the finalize method.

  - Set the object handle to null.

## finalize

Use the finalize method to explicitly destruct an object. There are no implicit calls to the finalize method. You must call it to execute the statements in it.

// From any method in a class.

{

...

if(Condition)

// Removes object from memory.

this.finalize();

...

}

The finalize method is also where to put any other clean-up code. For example, if your class uses a DLL module, you can use the finalize method to release the DLL when you no longer need it.


> [!WARNING]
> <P>Use finalize carefully. It will destruct an object even if there are references to it.</P>



## Set an Object Handle to null

Set the object handle to null to terminate an object. This only destroys the object if there are no other object handles pointing to it. Check that other programmers haven't already used the object handle.

For example:

// Create an object handle of the type MyObject.

MyObject mo;

;

// Create an object of MyObject type and

// link it to the object handle.

mo = new myObject();

// Terminate the object.

mo = null;

## See also

[Constructors](constructors.md)

[Declaration of Classes](declaration-of-classes.md)

[Declaration of Methods](declaration-of-methods.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

