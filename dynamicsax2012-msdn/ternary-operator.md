---
title: Ternary Operator (?)
TOCTitle: Ternary Operator (?)
ms:assetid: 05c78c4a-f1c4-46e4-8f49-3a524b013213
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa552755(v=AX.60)
ms:contentKeyID: 35240307
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Ternary Operator (?) 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

In the X++ language of Microsoft Dynamics AX, the ternary operator is a conditional statement that resolves to one of two expressions. This means that a ternary operation statement can be assigned to a variable. In comparison, an if statement provides conditional branching of program flow but cannot be assigned to a variable.

## Syntax

expression1 ? expression2 : expression3

expression1 must be a Boolean expression. If expression1 is true, the whole ternary statement resolves to expression2; otherwise it resolves to expression3.

expression2 and expression3 must be of the same type as each other.

## Example 1

This section describes a code example that returns one of two strings based on a Boolean return value from a method call. The Boolean expression indicates whether the CustTable table has a row with a RecId field value of 1.

result = (custTable::find("1").RecId) ? "found" : "not found";

If this Boolean expression is true (meaning RecId \!= 0), found is assigned to result. Otherwise, the alternative not found is assigned to result.

## Example 2

This section describes a code example that has one ternary statement nested inside another ternary statement.

    print( (custTable.AccountNum > "1000")
                ? ( (custTable.AccountNum < "2000")
                        ? "In interval" : "Above 2000"
                  )
                : "low"
         );

If AccountNum is not greater than 1000, the expression is equal to the third expression and low is printed.

If AccountNum is greater than 1000, the second expression is evaluated, and this also contains a ternary operator. If AccountNum is greater than 1000 and less than 2000, In interval is printed. If AccountNum is greater than 1000 and greater than or equal to 2000, Above 2000 is printed.

## Comparison to the IF Statement

This section describes a comparison of the ternary statement to the if statement.

    a = (b > c) ? b : c;
    
    // The preceding line of code is equivalent to the following if-else code:
    
    if (b > c)
    {
        a = b;
    }
    else
    {
        a = c;
    }

## See also

[if and if ... else Statements](if-and-if-else-statements.md)

[Switch Statements](switch-statements.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

