---
title: No Code in Forms
TOCTitle: No Code in Forms
ms:assetid: e26feeb8-042a-4564-a31c-4880a67624f7
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa879485(v=AX.60)
ms:contentKeyID: 35253109
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# No Code in Forms [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Do not place code in a form unless you cannot place it in a class or in a table method. Code written on forms cannot be reused and is difficult to customize.

A class that processes all the logic in a form should have the same name as the form with "Form" as the suffix. If you have a complex form, create a class for server-related tasks. This class should have the same name as the form, but with "Server" as the suffix.

If you have code in the form, the code should be for making only simple changes to the appearance of the form or to the form’s query. Try to place the code on the form or on the data source. Place code directly on controls only when you are absolutely certain that there is no other solution, and then use the AutoDeclaration property on these controls.

## Reasons for Removing Code from Forms

  - Forms are entirely client-based. There should be no code in them that manipulates the database (business logic). The code should be removed from the form and placed on the server.

  - Putting the business logic in methods on classes and tables makes it possible to customize, method by method. As a result, only the customized methods are overlayered. Methods on classes and tables are stored individually in the Application Object Tree (AOT), and thus can be individually overlayered. Because a form is a single layered application object, changes to the business logic in a form overlay the complete form—not just any customized method. This results in unwanted, redundant application object content in the upper layer.

  - Code placed in classes and tables can be reused in other application objects. Code inside a form is not practical to use—it is difficult to access, and there is no compile-time control.

  - The physical implementation of Web forms is very different from ordinary forms. If your business logic is not dependent on the look and implementation of a form, it is much easier to duplicate the form as a Web form.

  - When you want to enable your business logic for COM, it is essential that the business logic is not constructed in a form-dependent way.

## See also

[Forms Best Practices](forms-best-practices.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

