---
title: Dead Code Examples
TOCTitle: Dead Code Examples
ms:assetid: ed302786-1e48-409f-ab09-32d21ecac58b
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa884501(v=AX.60)
ms:contentKeyID: 35253239
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Dead Code Examples [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Avoid writing redundant code.

## Example 1

In the following example, b++ is never reached:

a++;

return a;

b++;

return b;

## Example 2

In the following example, the break statement is never reached:

switch (type)

{

    case UtilElementType::Job:

         return false;

         break;

    ...    

## Example 3

In the following example, return a is never reached:

if (\!a)

{

    throw error("@SYS21628");

    return a;

}

b++;

return b;

## Example 4

In the following example, the else statement is never used, because execution has already ended at the return statement:

if (a)

{

    return a;

}

else

{

    b++;

    return b;

}

Use this format instead:

if (a)

{

    return a;

}

b++;

return b;

## See also

[Clear Code Examples](clear-code-examples.md)

[X++ Coding Standards](x-coding-standards.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

