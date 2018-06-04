---
title: Best Practices for Method Modifiers
TOCTitle: Best Practices for Method Modifiers
ms:assetid: 6e1d952c-160c-4787-812e-352fb7472973
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa672948(v=AX.60)
ms:contentKeyID: 35244822
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Best Practices for Method Modifiers 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The best practices for using method modifiers are described in the following sections. For more information, see [Method modifiers](method-modifiers.md).

## Client or Server

These qualifiers are used for Application Object Server (AOS) tuning, where the task is to minimize the traffic between the client and the server. They are relevant only for table methods and static class methods, because other methods (class instance methods) run where their class is instantiated.

  - If a method is running on the server and only makes a single call to the client, it is okay to keep it on the server. If a method makes more than one call, move it to the client and then return it.

  - If a method is running on the client and only makes a single call to the server, it is okay to keep it on the client. If a method makes more than one call, move it to the server and then return it.

  - If you refer to both sides in your method, you must make the decision based on the dynamics of the calls. Maybe you can restructure the method internally or split it up in more than one method.

  - Do not qualify methods as client or server if they do not use anything on that tier.

  - You can use both client and server to change the execution place (to Called from) of a class static method or to document that it is decided that a table method executes best as Called from.

## Public, Protected or Private

You must specify an access level for your method. ![Warning icon](images/Aa658028.WarningIcon(en-us,AX.60).gif "Warning icon")

Only methods that can be used safely by the user of the class or table should be declared public. Even though methods are public by default, it is best to explicitly declare them as public, to show that they are intentionally public.

These access level specifiers affect only the compilation. You can still call a private or protected method at run time by using a noncompile time-checked call technique, so be careful.

## Static

It may be appropriate to make a method static if one of the following apply:

  - It does not use the instance member variables or fields that are defined for the class.

  - It is not going to be overridden.

  - It runs better on a different tier than the object itself.

  - It is related to the class or table, but it does not have its origin in a single object (instance).

One advantage of static methods is that you do not have to spend time creating an object; the method can simply be called.


> [!NOTE]
> <P>Methods that are not static are referred to as "instance methods", "normal methods", "object methods", or simply "methods".</P>



## Final

Unlike other methods, final methods cannot be overwritten.

## Abstract

Use the abstract qualifier when a method has to be implemented in a subclass. Even if it has no effect, it serves as documentation.

Abstract methods can only be declared as empty:

abstract public container pack()

{

}

## See also

[Best Practices for Methods](best-practices-for-methods.md)

[Best Practices for Parameters](best-practices-for-parameters.md)

[Best Practices for Table Methods](best-practices-for-table-methods.md)

[Best Practices for Local Functions](best-practices-for-local-functions.md)

[Naming standards for methods](naming-conventions-methods.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

