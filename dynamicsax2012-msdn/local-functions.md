---
title: Local Functions
TOCTitle: Local Functions
ms:assetid: 432d3e13-7a16-4315-b23f-406e53b3d23d
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa637343(v=AX.60)
ms:contentKeyID: 35242953
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Local Functions 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

You can declare local functions inside a method or a job in X++. A local function can contain code that would otherwise have to be duplicated in two or more places within your method.


> [!TIP]
> <P>The best practice is to add private methods to the class rather than to add local functions inside the method.</P>



## Code Example of a Local Function

The following X++ job code example shows valid declarations of two local functions named localFunc55b and localFunc66c. Calls to the local functions occur after the function declarations in the code example, as is required.
```X++  
    static void G_LocalFuncJob2(Args _args) // X++ job.
    {
        int nn = 654;
    
        void localFunc55b(int _iNum)  // The local function.
        {
            str sInnerString;
            sInnerString = "String_in_localFunc55b";
            info(strFmt("localFunc55b: %1 , %2 , %3", 
                _iNum, sInnerString, nn));
        }
    
        void localFunc66c()
        {
            info("Printing from inside localFunc66c.");
        }
        ; // This semicolon marks the end of local function declarations.
    
        localFunc55b(55);
        localFunc66c();
    
        // Next print statement would fail to compile,
        // because sInnerString is restricted to the
        // scope of the local function in which it is declared.
        //print sInnerString; pause;
    }
    /***  Infolog window display:
    Message (07:38:54 pm)
    localFunc55b: 55 , String_in_localFunc55b , 654
    Printing from inside localFunc66c.
    ***/
```
## Declaration of Local Functions

  - The local functions must be declared physically above any non-declaration statements that exist in the method or job.

  - You can declare more than one local function in your method. But all local functions must be declared in an uninterrupted series, with the set terminated by one semicolon.

## Scoping of Variables

  - Code that is inside the local function can access variables that are declared in the method or job that contains the local function.

  - Code that is outside the local function cannot access variables that are declared in the local function.

## Calls to Local Functions

  - A local function can be called only by code in the same method or job where the local function is declared.

  - An X++ local function should never call itself. Such recursion can prevent the successful compile of X++ to .NET Framework CIL.
    

    > [!NOTE]
    > <P>X++ local functions are transformed into inline code when the X++ method is compiled into CIL.</P>



## See also

[Methods in X++](methods-in-x.md)

[Best Practices for Local Functions](best-practices-for-local-functions.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

