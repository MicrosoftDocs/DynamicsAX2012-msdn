---
title: System Classes Overview
TOCTitle: System Classes Overview
ms:assetid: ab1aeb92-5e49-434c-ac64-25f1fe375daf
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa853470(v=AX.60)
ms:contentKeyID: 35249604
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# System Classes Overview 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

System classes (or kernel classes) are implemented in C++. The source for these classes is not available, but documentation is available for some of the classes in the [Reference](https://msdn.microsoft.com/en-us/library/aa626373\(v=ax.60\)) content.

A system class can have:

  - Static methods (or class methods)

  - Dynamic methods

  - Properties: these are member functions to set properties. For example, LeftMargin.


> [!NOTE]
> <P>You cannot override system class methods.</P>



It is not intended that you design your application objects from scratch by using the system classes. Instead, use them to extend or alter the default functionality in the Application Object Tree (AOT). For example, you could dynamically add extra information to an existing report or change the available options on a form, depending on the user's choice in a previous form.

Some of the categories of system classes are described as follows.

## Collection Classes

The [Collection Classes in Microsoft Dynamics AX](collection-classes-in-microsoft-dynamics-ax.md) enable you to create lists, sets, structs, maps, and arrays.

## Application Objects Classes

These system classes hold functions that are activated whenever you use the AOT to create your application. For example, the system uses the FormDesign class when you define the layout of your form in the Designs node in the Application Object Tree. When you click **New CheckBox** in the AOT, the system activates the controlName method with a CheckBox type control as parameter.

These classes also enable you to create and modify application objects. For example, if you want to change a property on a form string field, see [Forms System classes](form-classes.md) and [Query System Classes](query-object-model.md).

## Integration Classes

The integration to the environment of Microsoft Dynamics AX is typically implemented by classes. Some examples of classes of this category are:

  - COM: call of methods on COM objects

  - DLL: call of Microsoft Windows DLL functions

  - IO: Read and write external files

  - ODBCConnection: an ODBC interface to a foreign database

## Classes Extended by Application Classes

A group of system classes whose names begin with "X" are extended by Application classes. For example, the xInfo System class is extended by the Info Application class. For more information, see [Application substituted kernel classes](substitute-application-classes-for-system-classes.md).

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

