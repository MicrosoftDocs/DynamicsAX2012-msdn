---
title: 'Best Practice Performance Optimizations: General Programming'
TOCTitle: 'Performance Optimizations: General Programming'
ms:assetid: 362aa658-667c-4c05-b85c-f2e61e5c1c03
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa604198(v=AX.60)
ms:contentKeyID: 35242022
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Best Practice Performance Optimizations: General Programming [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

This topic describes programming techniques that can help to improve performance, and how to inform the user if there is a lengthy operation.

## Use Local Caching

You can improve performance by taking a value that is constantly calculated inside a loop out of that loop, and placing it in a variable that is then used inside the loop.

For example, the following method was called from a body line in a report, and used many times when the report was run. The isoCurrencyCode method is called on an Infolog object, which is bound to the client. So when this report is run on the server, there are two client calls per line.

display CurrencyCode currencyCode()

{

    return infolog.isoCurrencyCode()

        ? infolog.isoCurrencyCode()

        : CompanyInfo::find().currencyCode;

}

The previous code was changed so that a currencyCode variable was declared in the class declaration, initialized (once) in the init method, and then used in the currencyCode method.

This is the code used in the init method.

public void init() 

{

    super();

    ...

    currencyCode = infolog.isoCurrencyCode()

        ? infolog.isoCurrencyCode()

        : CompanyInfo::find().currencyCode;  

}

This is the new currencyCode method. There are no longer any calls to the client.

display CurrencyCode currencyCode()

{

    return currencyCode;  

}

## Optimize the Addition of Elements to Containers

Use the += construct to add elements to a container. This construct is optimized by the compiler and results in elements being added much faster than for a container  =  container  +  newValue ; construct. The difference in performance is particularly important for large containers.

The following example shows the two different ways of adding elements to a container.

```X++
    void containerExample
    {
        container c1;
        int a,b;
        ;
        // The non-optimized way to add an element.
        c1 = c1 + a;  
        // The optimized way to add an element.
        c1 += b;
    }
```

## Lengthy Operations

If a user is interacting with the UI and the operation takes longer than one second, use one of these indicators:

  - Use xInfo.startLengthyOperation to set the mouse cursor to idle.

  - Use an hourglass to show that the operation is progressing.

  - Use a progress bar to indicate progress.

## See also

[Best Practices: Performance Optimizations](best-practices-performance-optimizations.md)

[Best Practice Performance Optimizations: AOS Tuning](best-practice-performance-optimizations-aos-tuning.md)

[Best Practice Performance Optimizations: Database Design and Operations](best-practice-performance-optimizations-database-design-and-operations.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

