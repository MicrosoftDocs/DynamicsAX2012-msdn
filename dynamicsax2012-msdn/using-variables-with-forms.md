---
title: Using Variables with Forms
TOCTitle: Using Variables with Forms
ms:assetid: 3934193a-b694-4cd3-b00f-41c98f5488ab
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa636676(v=AX.60)
ms:contentKeyID: 35242869
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Using Variables with Forms 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Variables usually need to be declared before they can be used. Working with forms, however, some variables are implicitly declared by the system.

## Variables to Reference the Entire Form

The system creates the element variable. It is used to reference the entire form object.

The element variable is typically used in assignments, such as the following.

NotifyDate = element.design().control(control::NotifyDate);

## Variables to Reference the Data Source Table

The system creates a variable. Its name is the same as the table's that is used as a data source. This enables you to do the following:

  - Call a method defined on the table used as a data source for the form. For example:
    
    MyTable .setDefault(ReadWrite::write);

  - Reference the individual fields in the table. For example:
    
    AccountNumber =  MyTable .accountNo;

## Variables to Reference Properties and Methods on the Form Data Source

The system creates a variable. Its name is the same as the table's that is used as a data source, but is postfixed with "ds." This enables you to reference properties and methods on the form data source (as opposed to the table itself), as shown in the following example.

MyTable\_ds .research();

MyTable\_ds .validateWrite();

## See also

[Methods on a Form](methods-on-a-form.md)

[Table Methods](https://msdn.microsoft.com/en-us/library/aa625830\(v=ax.60\))

[Methods on a Form Data Source](methods-on-a-form-data-source.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

