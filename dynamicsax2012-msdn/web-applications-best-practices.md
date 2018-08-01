---
title: Web Applications Best Practices
TOCTitle: Web
ms:assetid: 80367d2c-d218-4e51-a290-8f5d1bf93f1a
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa657049(v=AX.60)
ms:contentKeyID: 35246136
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Web Applications Best Practices [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

When you create HTML documents or contents from X++ code, use the following standards.

## Formatting Strings with Web Tags

The Web class has a set of functions to format and output strings with Web tags. Use these, if possible.

To build strings:

1.  Construct the user interface string by using the strFmt system function.

2.  Insert HTML tags.
    
    For example:
    
    strFmt('\<h2\>%1\</h2\>',strFmt("@SYS4711",accountNum))

## Where to Place the Code

Put logic in classes (and tables), so it can be reused in a new context, like a Web page.

## Transactions

Keep locks on shared records to an absolute minimum. Use as few locks as possible, and for as short time as possible.

Transactions should be started only after the user has pressed a button, and they be completed before the control is returned to the user (the user may navigate to another Web page, and forget about the transaction on the current page).

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

