---
title: Searching for Multiple Occurrences Design Pattern
TOCTitle: Searching for Multiple Occurrences
ms:assetid: c9bdeff9-acfe-4981-900f-e496db87a8f4
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa867933(v=AX.60)
ms:contentKeyID: 35251258
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Searching for Multiple Occurrences Design Pattern 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Use the following pattern when you search through a text for multiple (all the) occurrences of a search expression.

    int         startPos;
    TextBuffer textBuffer = new TextBuffer();
    ;
    textBuffer.setText(/*Your text goes here*/);
    startPos = 0;
    while (textBuffer.find(/*Your search expression goes here*/,startPos))
    {
         /* Do whatever is needed with the text found.
             The text is found in the buffer contents 
             from textBuffer.matchPos() and textBuffer.matchLen() ahead */
        ...
        startPos = textBuffer.matchPos() + textBuffer.matchLen();
    } 


> [!TIP]
> <P>By default, the search expression is a regular expression.</P>



## Example

The following illustrates an example of the multiple occurrences design pattern.

    static void textBufferFind(Args _args)
    {
        int startPos;
        TextBuffer textBuffer = new TextBuffer();
        ;
        textBuffer.setText("Hello World");
        startPos = 0;
        while (textBuffer.find('o',startPos))
        {
            print textBuffer.matchPos(),' ',textBuffer.matchLen();
            startPos = textBuffer.matchPos() + textBuffer.matchLen();
        }
        pause;
    }

## See also

[Microsoft Dynamics AX Design Patterns](microsoft-dynamics-ax-design-patterns.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

