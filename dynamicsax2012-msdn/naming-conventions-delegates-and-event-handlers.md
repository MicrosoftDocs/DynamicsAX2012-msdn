---
title: 'Naming Conventions: Delegates and Event Handlers'
TOCTitle: Delegates and Event Handlers
ms:assetid: bfcf5320-9051-4fc1-b271-1269f7d92a4a
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg879953(v=AX.60)
ms:contentKeyID: 35250075
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Naming Conventions: Delegates and Event Handlers [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

This topic provides the naming convention for delegates and event handlers when using X++. For information on how these concepts support the event scenario in Microsoft Dynamics AX, see [Event Handler Nodes in the AOT](event-handler-nodes-in-the-aot.md).

## Delegate Naming Conventions

When you name a delegate, follow the general [Naming Conventions](naming-conventions.md) for X++ and the [Naming Conventions for Methods](naming-conventions-methods.md). The following list describes additional naming guidelines for delegates.

  - Use Pascal case, for example invoiceCreated, invoiceCreating, and mapRendered.

  - The two components of the name should be a noun (for example invoice) and a verb (for example opening or opened). An example is invoiceOpened. When the class name is a noun, the noun can be omitted from the delegate name. For example, Invoice.opened.
    
    Use present tense for logic that runs before an event occurs (end with ing)
    
    Use past tense for logic that runs after an event occurs (end with ed)

  - The following example illustrates definitions of two delegates creating and created in the Invoice class that is a noun.
    
    ```X++
    class Invoice
    {
        …
        delegate void creating(object sender, InvoiceEventArgs args) {}
        delegate void created(object sender, InvoiceEventArgs args) {} 
    }
       
    ```

## Event Handler Naming Conventions

Event handlers must have a name with the suffix EventHandler. The following example illustrates names that consist of the delegate name and the EventHandler suffix.

```X++
    void createdEventHandler(object sender, InvoiceEventArgs args)
    void invoiceCreatedEventHandler(object sender, InvoiceEventArgs args)
```

> [!NOTE]
> <P>Event handler naming conventions apply to pre and post event handlers.</P>



## See also

[Event Handler Nodes in the AOT](event-handler-nodes-in-the-aot.md)

[Naming Conventions](naming-conventions.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

