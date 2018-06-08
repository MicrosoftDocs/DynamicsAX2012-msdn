---
title: 'How to: Use X++ Syntax for CLR Arrays'
TOCTitle: 'How to: Use X++ Syntax for CLR Arrays'
ms:assetid: 7217670a-2686-455f-a8da-5361ff483507
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc557456(v=AX.60)
ms:contentKeyID: 35245823
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Use X++ Syntax for CLR Arrays 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

X++ has syntax that you can use to directly create and handle .NET Framework arrays. The syntax is an alternative to constructing instances of System.Array directly, and the underlying effect is the same. The syntax is easier to write than the verbose alternative of using a variable declared as .NET Framework type System.Array.

## Code Sample for .NET Framework and Native Arrays in X++

The following X++ code sample creates a .NET Framework array, populates the array, and then prints the contents of the array. For comparisons, it also does the same tasks with a standard X++ array.

    static void JobTestNetArray()
    {
        System.Int32[] iNetNumbers; // .NET Framework array
        int iXppNumbers[2]; // X++ array
        int iXppNum
            ,iXppArrayLength
            ,i;
        ;
        info("Next, .NET Framework array by special X++ syntax.");
        //-------- .NET Framework array by special X++ syntax ------
        iNetNumbers = new System.Int32[2](); // Note the () at end.
        iNetNumbers.SetValue(100, 0); // Resembles iNetNumbers[0]=100.
        iNetNumbers.SetValue(101, 1);
    
        iXppArrayLength = iNetNumbers.get_Length();
        for (i = 0; i < iXppArrayLength; i++)
        {
            iXppNum = iNetNumbers.GetValue(i); // Resembles iNetNumbers[i].
            info(int2str(iXppNum));
        }
    
        info("Next, X++ Native array.");
        //----------- X++ Native array ------
        iXppNumbers[1] = 2201;
        iXppNumbers[2] = 2202;
    
        for (i = 1; i <= dimOf(iXppNumbers); i++)
        {
            info(int2str(iXppNumbers[i]));
        }
    
    /***** Actual infolog output
    Message (07:31:10 am)
    Next, .NET Framework array by special X++ syntax.
    100
    101
    Next, X++ Native array.
    2201
    2202
    *****/
    }

## Syntax Differences Between .NET Framework Arrays vs. Native Arrays in X++

In X++ there are important syntax differences between how you handle .NET Framework arrays versus standard X++ arrays. The differences are as follows:

  - The indexing of .NET Framework arrays is 0 based. The indexing of X++ arrays is 1 based.

  - .NET Framework array variables are declared with the \[\] pair after the type. X++ arrays are declared with the \[\] pair after the variable.

  - .NET Framework arrays are constructed by using the X++ keyword new. The new keyword is not used to create an X++ array.

  - The indexer of a .NET Framework array can be a .NET Framework integer variable, or an X++ integer variable, or a literal integer. The indexer for an X++ array must be an X++ integer variable, or a literal integer, or it can be an expression such as myInt + 3.

  - Even in X++, a .NET Framework array can be multidimensional, as either rectangular or jagged (array of arrays). An X++ array is limited to one dimension.

  - .NET Framework arrays can be of any .NET Framework type. X++ arrays are only for X++ primitive types (such as int or str).

  - .NET Framework arrays can hold .NET Framework types, but not X++ types.

  - The size of an X++ array is determined in the declaration of the array. The size of a .NET Framework array is determined after the declaration.

There are other syntax differences. For instance, you can reinitialize all the elements in an X++ array to a given value by assigning the value to the 0 index of the array. There is nothing comparable to this for .NET Framework arrays. For more information about X++ array syntax, see [Arrays](arrays.md).

## Syntax Differences Between .NET Framework Arrays in C\# vs. X++

The X++ syntax for .NET Framework arrays resembles the syntax for arrays in the .NET Framework language C\#. The differences are as follows:

  - In X++, the code to construct an array needs a () pair after the \[\] pair.

  - .NET Framework array property members, such as Length, cannot be called in X++. Instead, the field or method must be accessed, such as get\_Length.

  - In C\#, .NET Framework array element values can be initialized in the declaration of the array, by using a {} pair after the variable name. This syntax is not supported in X++.

## See also

[.NET Interop from X++](net-interop-from-x.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

