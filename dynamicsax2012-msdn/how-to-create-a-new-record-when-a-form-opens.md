---
title: 'How to: Create a New Record When a Form Opens'
TOCTitle: 'How to: Create a New Record When a Form Opens'
ms:assetid: 7ec6785f-71f3-4724-8b90-bc77d7814beb
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa642442(v=AX.60)
ms:contentKeyID: 35246125
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Create a New Record When a Form Opens 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

To create a new record every time that the user opens a form:

  - Call the create method on the form data source.

  - Set the InsertAtEnd property on the form data source to No.

  - Set the StartPosition property on the form data source (to First or Last).

## Example

The following example is from the run method in the PurchCreateOrder form. purchTable\_ds is the variable for the PurchTable data source on the form.

    void run()
    {
        purchTable_ds.create();
        element.modifyForm();
     
        super();
    
         purchTable_ds.lookUpOrderAccount();
     
        if (!purchTableType)
        {
            element.close();
            throw Exception::Error;
        }
    } 

## See also

[Methods on a Form Data Source](methods-on-a-form-data-source.md)

[Form Data Source Properties](form-data-source-properties.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

