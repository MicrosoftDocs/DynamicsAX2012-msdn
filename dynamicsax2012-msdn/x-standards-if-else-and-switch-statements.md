---
title: 'X++ Standards: if ... else and switch Statements'
TOCTitle: 'X++ Standards: if ... else and switch Statements'
ms:assetid: 4f0efe0d-8cf6-4181-bc41-3d6fd6e66feb
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa629483(v=AX.60)
ms:contentKeyID: 35243495
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# X++ Standards: if ... else and switch Statements 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

This topic describes X++ code style standards for the if ... else statement and the switch statement.

## if ... else

If you have an if ... else construction, then use positive logic:

**Recommended:**

if (true)

{

    ...

}

else

{

    ...

}

**Avoid:**

if (\!false)

{

    ...

}

else

{

    ...

}

It is acceptable to use negative logic if throwing an error, and in cases where the use of positive logic would make the code difficult to understand.

There should be a space character between the if keyword and the open parenthesis.

## Switch Statements

Always end a case with a break statement (or return/throw). If you intentionally want to make use of the fall-through mechanism supported in X++, replace the missing break statement with a comment line:

    // Fall through

This comment line makes it visually clear to the reader that the fall-through mechanism is utilized.

Use 3 levels of indentation:

switch (Expression)

{

    case Constant:

        Statement;

        break;

    ...

}

Do not put parentheses around cases. ![Warning icon](images/Aa658028.WarningIcon(en-us,AX.60).gif "Warning icon")

## Use a switch Instead of Nested if ... else Statements

Use switch statements instead of nested if ... else statements.

**Recommended:**

switch (myEnum)

{

    case ABC::A:

    ...

        break;

    case ABC::B:

    ...

        break;

    case ABC::C:

    ...

        break;

    default:

    ...

        break;

}

**Avoid:**

if (myEnum == ABC::A)

{

    ...

}

else

{

    if (myEnum == ABC::B)

    {

        ...

    }

    else

    {

        if (myEnum == ABC::C)

        {

            ...

        }

        else

        {

           ...

        }

    }

}

## See also

[if and if ... else Statements](if-and-if-else-statements.md)

[Switch Statements](switch-statements.md)

[Comparison of if and switch Statements](comparison-of-if-and-switch-statements.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

