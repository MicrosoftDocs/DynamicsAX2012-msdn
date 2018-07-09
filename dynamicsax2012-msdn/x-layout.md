---
title: X++ Layout
TOCTitle: X++ Layout
ms:assetid: 1fe3e89e-e639-4eb8-9f6d-21af2894c2ab
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa619943(v=AX.60)
ms:contentKeyID: 35241533
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# X++ Layout 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

## General Guidelines

  - Only one statement per line.

  - Break up complex expressions that are more than one line - make it visually clear.

  - Use a single blank line to separate entities.

  - Do not use parentheses around the case constants. ![Warning icon](images/Aa658028.WarningIcon(en-us,AX.60).gif "Warning icon")

  - Do not use parentheses around where expressions.

  - Add one space between if, switch, for, while and the expressions starting parentheses. For example:
    
    if (creditNote)

  - Use braces around all code blocks, except for around case clauses in a switch statement. Use braces even if there is only one statement in the block.

## Indentation

An indentation is equivalent to four (4) characters, which corresponds to one tab in the X++ editor. You must not start a new line in columns 2, 3 or 4. ![Error icon](images/Aa872655.ErrorIcon(AX.60).gif "Error icon")

  - Put opening and closing braces, { and }, on the same level, on separate lines, and aligned with the command creating the block. They must be at the start of a line, and in a tab column position (1, 5, 9 etc.). ![Error icon](images/Aa872655.ErrorIcon(AX.60).gif "Error icon") Braces must be on a dedicated line ![Error icon](images/Aa872655.ErrorIcon(AX.60).gif "Error icon") unless a opening brace is followed by a semicolon ( {; ) or a closing brace is followed by a while ( }while ).

  - The following reserved words should be placed at the beginning of a line: case, catch, changeCompany, continue, default, else, for, if, retry, return, switch, try, ttsAbort, ttsBegin, ttsCommit, while. ![Warning icon](images/Aa658028.WarningIcon(en-us,AX.60).gif "Warning icon")
    
    The exceptions to this rule are:
    
    case: … (reserved words in a case statement)
    
    default: … (reserved words in a default statement)
    
    else if
    
    }while

  - If a line of code starts with any other reserved word, or with an alphabetical character, the line should start in a tab column position (1, 5, 9 etc). ![Warning icon](images/Aa658028.WarningIcon(en-us,AX.60).gif "Warning icon") The following reserved words must be placed in a tab column position: case, catch, changeCompany, continue, default, else, for, if, retry, return, switch, try, ttsAbort, ttsBegin, ttsCommit, while. ![Error icon](images/Aa872655.ErrorIcon(AX.60).gif "Error icon")
    
    The exceptions to these rules are:
    
    case: … (reserved words in a case statement)
    
    default: … (reserved words in a default statement)
    
    else if
    
    }while

  - The reserved word else must have a dedicated line unless you write else if ![Error icon](images/Aa872655.ErrorIcon(AX.60).gif "Error icon").

  - switch-case statements: indent case and default statements by 1 level (with any code within these indented a further level) and indent break statements by two levels.

  - Indent where and other qualifiers to the select statement by one level.

  - If Booleans are used in a long expression, put them at the start of an indented new line.

### ![Aa619943.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa619943.collapse_all(en-us,AX.60).gif")Example switch-case Statement
```X++
    switch (myEnum)
    {
        case ABC::A:
            ...
            break;
        case ABC::B
            ...
            break;
        default:
            ...
            break;
    }
```
### ![Aa619943.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa619943.collapse_all(en-us,AX.60).gif")Example select Statement
```X++
    select myTable
        index hint myIndex
        where myTable.field1 == 1
            && myTable.field2 == 2;
```
### ![Aa619943.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa619943.collapse_all(en-us,AX.60).gif")Example Layout of Booleans in a Long Expression
```X++
    select firstOnly utilElements
        where utilElements.recordType == recordType
            && utilElements.parentId == parentID
            && utilElements.name == elementName;
```
## Column Layout

Column layout should be used where more than one line has the same structure; for example, in declarations or assignments.

Do not use column layout when there is only one row, or if consecutive rows do not have the same structure.

Column format is defined using extra blanks.

### ![Aa619943.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa619943.collapse_all(en-us,AX.60).gif")Example Column Layout
```X++
    tmpABC.refRecId     = inventTable.recId;
    tmpABC.itemGroupId  = inventTable.itemGroupId;
    tmpABC.itemId       = inventTable.itemId;
    tmpABC.amount       = amount;
    tmpABC.oldValue     = this.getCategory(inventTable);
    tmpABC write();
```
## Layout for Methods

The starting parenthesis on method declarations and calls should be the character just after the method name (no space).

If there are one or two parameters, the parameters can be listed on the same line. If there are more than two parameters, move each parameter onto a new line, and indent by 4 spaces.

### ![Aa619943.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa619943.collapse_all(en-us,AX.60).gif")Example Layout for Method with One or Two Parameters
```X++
    myMethod(parameter1, parameter2);
```
### ![Aa619943.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa619943.collapse_all(en-us,AX.60).gif")Example Layout for Method with Many Parameters
```X++
    myMethod(
        parameter1,
        parameter2,
        parameter3);
```
## See also

[X++ Coding Standards](x-coding-standards.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

