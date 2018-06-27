---
title: 'X++, C# Comparison: Array Syntax'
TOCTitle: 'X++, C# Comparison: Array Syntax'
ms:assetid: c2ad940a-34ae-4ac5-9358-e0b1b749ac56
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc967423(v=AX.60)
ms:contentKeyID: 35250113
ms.date: 05/18/2015
mtps_version: v=AX.60
dev_langs:
- csharp
---

# X++, C\# Comparison: Array Syntax 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

This topic compares array syntax between X++ and C\#.

## X++ to C\# Comparisons

There are similarities and differences in the features and syntax for arrays in X++ versus C\#.

### ![Cc967423.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc967423.collapse_all(en-us,AX.60).gif")Similarities

Overall there is much similarity in the syntax and treatment of arrays in X++ and C\#. However there are many differences.

### ![Cc967423.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc967423.collapse_all(en-us,AX.60).gif")Differences

The following table lists areas in the \[\] syntax for arrays that are different for X++ and C\#.

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Category</p></th>
<th><p>X++</p></th>
<th><p>C#</p></th>
<th><p>Comments</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Declaration</p></td>
<td><p>An array is declared with square brackets appended to the variable name.</p></td>
<td><p>An array is declared with square brackets appended to the data type.</p></td>
<td><p>int myInts[]; // X++</p>

> [!note]  
> <P>An X++ array cannot be a parameter in a method.</P>

</td>
</tr>
<tr class="even">
<td><p>Declaration</p></td>
<td><p>The array syntax supports only primitive data types, such as int and str. The syntax does not support classes or tables.</p></td>
<td><p>The array syntax supports primitive data types and classes.</p></td>
<td><p>In X++ you can use the Array <a href="https://msdn.microsoft.com/en-us/library/gg802677(v=ax.60)">Array</a> for an array of objects.</p></td>
</tr>
<tr class="odd">
<td><p>Declaration</p></td>
<td><p>X++ is limited to single dimension arrays (myStrings[8]).</p></td>
<td><p>C# adds support for multi-dimensional arrays (myStrings[8,3]) and for jagged arrays (myStrings[8][3]).</p></td>
<td><p>In X++ you cannot have an array of arrays. However, there is advanced syntax for limiting the amount of active memory that a large array can consume, which looks like the multi-dimensional syntax in C#: int intArray[1024,16];. For more information, see <a href="best-practice-performance-optimizations-swapping-arrays-to-disk.md">Best Practice Performance Optimizations: Swapping Arrays to Disk</a>.</p></td>
</tr>
<tr class="even">
<td><p>Declaration</p></td>
<td><p>In X++ an array is a special construct but it is not an object.</p></td>
<td><p>In C# all arrays are objects regardless of syntax variations.</p></td>
<td><p>X++ does have an Array class, but its underlying mechanism differs from arrays created by using the [] syntax.</p>
<p>In C# all arrays use the same underlying mechanism, regardless of whether [] syntax of the System.Array class is used in your code.</p></td>
</tr>
<tr class="odd">
<td><p>Length</p></td>
<td><p>In X++ the length of a static sized array is determined in the declaration syntax.</p></td>
<td><p>In C# the size of an array is determined when the array object is constructed.</p></td>
<td><p>When you use the [] declaration syntax in X++, no more preparation is needed before you assign values to the array.</p>
<p>In C# you must declare and then construct the array before assigning to it.</p></td>
</tr>
<tr class="even">
<td><p>Length</p></td>
<td><p>An X++ array can have a dynamic length that can be increased even after population has begun. This applies only when the array is declared without a number inside the []. Performance might be slowed if the length of the dynamic array is increased many times.</p></td>
<td><p>In C# the length of an array cannot be changed after the length is set.</p></td>
<td><p>In the following fragment of X++ code, only the myInts array is dynamic and can increase in size.</p>
<p>int myInts[];</p>
<p>int myBools[5];</p>
<p>;</p>
<p>myInts[2] = 12;</p>
<p>myInts[3] = 13;</p>
<p>myBools[6] = 26; //Error</p></td>
</tr>
<tr class="odd">
<td><p>Length</p></td>
<td><p>You can get the length of some arrays by using the dimOf <a href="https://msdn.microsoft.com/en-us/library/aa597117(v=ax.60)">function</a>.</p></td>
<td><p>C# arrays are objects that have a Length property.</p></td>
<td><p>No comments.</p></td>
</tr>
<tr class="even">
<td><p>Indexing</p></td>
<td><p>Array indexing is 1 based.</p></td>
<td><p>Array indexing is 0 based.</p></td>
<td><p>mtIntArray[0] would cause an error in X++.</p></td>
</tr>
<tr class="odd">
<td><p>Constant</p></td>
<td><p>In X++ a constant value is best achieved by using the #define precompiler directive.</p></td>
<td><p>In C# you can decorate your variable declaration with the keyword const, to achieve a constant value.</p></td>
<td><p>X++ has no const keyword. C# cannot assign values to variables that are created by its #define precompiler directive.</p></td>
</tr>
</tbody>
</table>


## X++ and C\# Samples

The following code samples show how arrays of primitive data types are handled. The first sample is in X++, and the second sample is in C\#. Both samples achieve the same results.

### ![Cc967423.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc967423.collapse_all(en-us,AX.60).gif")X++ Sample

    static void JobRs005a_ArraySimple(Args _args)
    {
        #define.macroArrayLength(3)
    
        // Static length.
        str sSports[#macroArrayLength];
    
        // Dynamic length, changeable during run time.
        int years[];
        int xx;
        Global::warning("-------- SPORTS --------");
        sSports[#macroArrayLength] = "Baseball";
    
        for (xx=1; xx <= #macroArrayLength; xx++)
        {
            info(int2str(xx) + " , [" + sSports[xx] + "]");
        }
        warning("-------- YEARS --------");
        years[ 4] = 2008;
        years[10] = 1930;
    
        for (xx=1; xx <= 10; xx++)
        {
            info(int2str(xx) + " , " + int2str(years[xx]));
        }
    }

#### ![Cc967423.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc967423.collapse_all(en-us,AX.60).gif")Output

The output to the Infolog is as follows:

<pre IsFakePre="true" xmlns="http://www.w3.org/1999/xhtml">Message (14:16:08)
-------- SPORTS --------
1 , []
2 , []
3 , [Baseball]
-------- YEARS --------
1 , 0
2 , 0
3 , 0
4 , 2008
5 , 0
6 , 0
7 , 0
8 , 0
9 , 0
10 , 1930</pre>


### ![Cc967423.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc967423.collapse_all(en-us,AX.60).gif")C\# Sample

``` csharp
using System;
public class Pgm_CSharp
{
    static public void Main( string[] args )
    {
        new Pgm_CSharp().Rs005a_CSharp_ArraySimple();
    }
    private void Rs005a_CSharp_ArraySimple()
    {
        const int const_iMacroArrayLength = 3;

        // In C# the length is set at construction during run.
        string[] sSports;
        int[] years;

        int xx;
        Console.WriteLine("-------- SPORTS --------");
        sSports = new string[const_iMacroArrayLength];
        sSports[const_iMacroArrayLength - 1] = "Baseball";

        for (xx=0; xx < const_iMacroArrayLength; xx++)
        {
            Console.WriteLine( xx.ToString()
                + " , [" + sSports[xx] + "]" );
        }
        Console.WriteLine("-------- YEARS --------");
        // In C# you must construct the array before assigning to it.
        years = new int[10];
        years[ 4] = 2008;
        years[10 - 1] = 1930;

        for (xx=0; xx < 10; xx++)
        {
            Console.WriteLine( xx.ToString()
                + " , [" + years[xx].ToString() + "]" );
        }
    }
} // EOClass
```

#### ![Cc967423.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc967423.collapse_all(en-us,AX.60).gif")Output

The output from the C\# program to the command line console is as follows:

<pre IsFakePre="true" xmlns="http://www.w3.org/1999/xhtml">-------- SPORTS --------
0 , []
1 , []
2 , [Baseball]
-------- YEARS --------
0 , [0]
1 , [0]
2 , [0]
3 , [0]
4 , [2008]
5 , [0]
6 , [0]
7 , [0]
8 , [0]
9 , [1930]</pre>


## Additional X++ Features

The container is a special data type that is available in X++. It can be considered as similar to an array, or similar to a List collection. For more information, see [Containers](containers.md).

## See also

[X++, C\# Comparisons](x-csharp-comparisons.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

