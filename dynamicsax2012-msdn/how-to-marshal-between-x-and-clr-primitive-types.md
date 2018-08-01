---
title: 'How to: Marshal Between X++ and CLR Primitive Types'
TOCTitle: 'How to: Marshal Between X++ and CLR Primitive Types'
ms:assetid: 1cc48544-1cbd-42b8-8d18-f786f1f0e0b1
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc584291(v=AX.60)
ms:contentKeyID: 35241463
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Marshal Between X++ and CLR Primitive Types [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

In Microsoft Dynamics AX, the X++ language does implicit conversion or marshaling between several X++ primitive types and their counterpart types managed by the common language runtime (CLR). This means that the X++ assignment operator, the single equal sign (=), can be used between certain pairings of an X++ type with a .NET Framework CLR type.

Implicit marshaling with the X++ assignment operator works in both directions, either from X++ types to CLR types, or from CLR to X++.

## Why Marshaling is Useful

A .NET managed assembly might provide a useful method that returns a System.String object. You can call the method and capture the returned System.String in a variable of that type that you declare in your X++ code.

But if your next step is to pass that string into an X++ method that takes a str, you must first marshal the System.String into a str.

For more information, see [How to: Substitute Primitive Parameter Types Between the CLR and X++](how-to-substitute-primitive-parameter-types-between-the-clr-and-x.md).

## Implicitly Marshaled Conversion Pairs

Each row in the following table lists a pairing of types that are implicitly marshaled by the X++ assignment operator.


> [!NOTE]
> <P>There is no implicit marshaling between the X++ utcdatetime and .NET Framework System.DateTime type. For more information about how to convert between utcdatetime and System.DateTime, see <A href="how-to-convert-between-utcdatetime-and-system-datetime.md">How to: Convert Between utcdatetime and System.DateTime</A>.</P>



<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>X++ type</p></th>
<th><p>CLR type</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>boolean</p></td>
<td><p>System.Boolean</p></td>
</tr>
<tr class="even">
<td><p>date</p></td>
<td><p>System.DateTime</p></td>
</tr>
<tr class="odd">
<td><p>int</p></td>
<td><p>System.Int32</p></td>
</tr>
<tr class="even">
<td><p>int64</p></td>
<td><p>System.Int64</p></td>
</tr>
<tr class="odd">
<td><p>str</p></td>
<td><p>System.String</p></td>
</tr>
<tr class="even">
<td><p>guid</p></td>
<td><p>System.Guid</p></td>
</tr>
<tr class="odd">
<td><p>Real</p></td>
<td><p>System.Single or System.Double</p></td>
</tr>
</tbody>
</table>


## Code Sample for System.Boolean

The following code sample shows the marshaling between the .NET Framework System.Boolean type and its X++ counterpart boolean.
```X++  
    static void JobBooleanMarshal(Args _args) // X++ job.
    {
        System.Boolean netBool; // .NET
        boolean xppBool; // X++
        ;
        // Marshal .NET to X++.
        xppBool = false;
    
        netBool = true;
        xppBool = netBool; // Marshals.
        if (true == xppBool)
        {
            info("A1. Good, .NET was marshaled to X++.");
        }
        else
        {
            info("A2. Bad, .NET was not marshaled to X++.");
        }
        // Marshal X++ to .NET.
        netBool = true;
        
        xppBool = false;
        netBool = xppBool; // Marshals.
        
        xppBool = true;
        xppBool = netBool;
        if (false == xppBool)
        {
            info("B1. Good, X++ was marshaled to .NET.");
        }
        else
        {
            info("B2. Bad, X++ was not marshaled to .NET.");
        }
    }
    /****** Actual infolog output
    Message (01:08:32 pm)
    A1. Good, .NET was marshaled to X++.
    B1. Good, X++ was marshaled to .NET.
    ******/
```
## Code Sample for System.DateTime

The following code sample shows the marshaling between the .NET Framework System.DateTime type and the X++ date type. From System.DateTime, there is no marshaling to the X++ utcdatetime type, and there is no marshaling to the timeOfDay extended data type (which is an int).
```X++  
    static void JobDateTimeMarshal(Args _args)
    {
        System.DateTime netDttm;
        date xppDate;
        str strTemp;
        ;
        // Marshal .NET to X++.
        netDttm = new System.DateTime(1988,7,20 ,13,44,55);
        xppDate = netDttm; // Marshals.
        if (date2str(xppDate,321, 2,2,2,2,4) == "1988.07.20")
        {
            info("A1. Good, .NET was marshaled to X++.");
        }
        else
        {
            info("A2. Bad, .NET was not marshaled to X++.");
        }
        // Marshal X++ to .NET.
        xppDate = 25\11\2002;
        netDttm = xppDate; // Marshals.
        strTemp = netDttm.ToString("s");
        if (strTemp == "2002-11-25T00:00:00")
        {
            info("B1. Good, X++ was marshaled to .NET.");
        }
        else
        {
            info("B2. Bad, X++ was not marshaled to .NET.");
        }
    }
```
## Code Sample for System.Int32

The following code sample shows the marshaling between the .NET Framework System.Int32 type and its X++ counterpart int.
```X++  
    static void JobInt32Marshal(Args _args)
    {
        System.Int32 netInt;
        int xppInt;
        ;
        // Marshal .NET to X++.
        netInt = 33;
        xppInt = netInt; // Marshals.
        if (33 == xppInt)
        {
            info("A1. Good, .NET was marshaled to X++.");
        }
        else
        {
            info("A2. Bad, .NET was not marshaled to X++.");
        }
        // Marshal X++ to .NET.
        netInt = 0;
    
        xppInt = 444;
        netInt = xppInt; // Marshals.
    
        xppInt = 0;
        xppInt = netInt;
        if (444 == xppInt)
        {
            info("B1. Good, X++ was marshaled to .NET.");
        }
        else
        {
            info("B2. Bad, X++ was not marshaled to .NET.");
        }
    }
```
### ![Cc584291.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc584291.collapse_all(en-us,AX.60).gif")X++ int Does Not Marshal to System.Int64

Automatic marshaling works between the X++ int64 type and the .NET Framework type System.Int64, just as marshaling works between the X++ int and the .NET System.Int32.

An X++ int does not marshal to a System.Int64, nor the reverse. A System.Int32 does not marshal to an X++ int64, nor the reverse.

## Code Sample for System.String

The following code sample shows the marshaling between the .NET Framework System.String type and its X++ counterpart str.


> [!WARNING]
> <P>An error occurs if an assignment is made to an X++ str variable from a System.String variable that is currently null.</P>


```X++  
    static void JobStringMarshal(Args _args)
    {
        System.String netString;
        str xppString;
        ;
        // Marshal .NET to X++.
        netString = "cat";
        xppString = netString; // Marshals.
        if ("cat" == xppString)
        {
            info("A1. Good, .NET was marshaled to X++.");
        }
        else
        {
            info("A2. Bad, .NET was not marshaled to X++.");
        }
        // Marshal X++ to .NET.
        netString = "";
    
        xppString = "dog";
        netString = xppString; // Marshals.
    
        xppString = "";
        xppString = netString;
        if ("dog" == xppString)
        {
            info("B1. Good, X++ was marshaled to .NET.");
        }
        else
        {
            info("B2. Bad, X++ was not marshaled to .NET.");
        }
    
    /***** Actual infolog output
    Message (06:27:19 am)
    A1. Good, .NET was marshaled to X++.
    B1. Good, X++ was marshaled to .NET.
    *****/
    }
```
### ![Cc584291.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc584291.collapse_all(en-us,AX.60).gif")X++ Strings Declared with a Maximum Length

As an option in X++, str variables can be declared with a maximum length. The following str declaration sets the maximum length at 8. The assignment would end with the value of myStr being "12345678", with the "9" being truncated:

str 8 myStr = "123456789"; // The 9 is truncated.

The System.String type in .NET Framework does not have a property that corresponds to the maximum length of an X++ str, and string truncation does not occur. This feature difference could lead to different behavior at run time in the following cases:

  - X++ str is marshaled to .NET Framework.

  - X++ is compiled to .NET Framework common intermediate language (CIL), and is run as CIL.

When X++ is run as p-code rather than as CIL, instances of str truncation can be logged by Microsoft Dynamics AX. For more information, see the logstrtrunc parameter in [Client configuration commands](https://msdn.microsoft.com/en-us/library/aa569653\(v=ax.60\)).

## Code Sample for System.Guid

The following code sample shows the marshaling between the .NET Framework System.Guid type and its X++ counterpart guid.
```X++  
    static void JobGuidMarshal(Args _args)
    {
        System.Guid netGuid;
        guid xppGuid;
        str sGuid1
            ,sGuid2;
        ;
        sGuid1 = "10001000-1000-1000-1000-100010001000";
        sGuid2 = "20002000-2000-2000-2000-200020002000";
        // Marshal .NET to X++.
        netGuid = Global::guidFromString(sGuid1);
        xppGuid = netGuid; // Marshals.
        if (xppGuid == Global::guidFromString(sGuid1))
        {
            info("A1. Good, .NET was marshaled to X++.");
        }
        else
        {
            info("A2. Bad, .NET was not marshaled to X++.");
        }
        // Marshal X++ to .NET.
        xppGuid = Global::guidFromString(sGuid2);
        netGuid = xppGuid; // Marshals.
        xppGuid = Global::guidFromString(sGuid1);
        xppGuid = netGuid;
        if (xppGuid == Global::guidFromString(sGuid2))
        {
            info("B1. Good, X++ was marshaled to .NET.");
        }
        else
        {
            info("B2. Bad, X++ was not marshaled to .NET.");
        }
    }
```
## Code Sample for System.Single and System.Double

The following code sample shows the marshaling between the .NET Framework types System.Single and System.Double, and their mutual X++ counterpart real. The sample shows that the X++ real does marshal in both directions, with both .NET Framework types.
```X++  
    static void JobRealMarshal(Args _args)
    {
        str xppStr;
        real xppReal;
        System.Double netDouble;
        System.Single netSingle;
        ;
        xppReal = 1.2305e+6;
    
        netSingle = xppReal;
        xppReal = 0.0;
        xppReal = netSingle;
    
    
        // Works in AX 2009, but not in later versions.
        //netDouble = xppReal;
    
        // Works in AX 2012, but
        // this method does not exist in earlier versions.
        netDouble = Global::real2double(xppReal);
    
    
        xppReal = 0.0;
        xppReal = netDouble;
    
        netSingle = xppReal;
        xppStr = System.Convert::ToString(netSingle);
        info(xppStr);
    }
    /***** Actual infolog output
    Message (01:39:56 pm)
    1230500
    *****/
```
  
The following line of X++ code fails to compile. The reason is that the literal 98.76 is treated as a System.Decimal, which cannot be directly assigned to a System.Double.

  
 System.Double netDouble = 98.76; // This line of X++ code fails to compile.   

## Converting from Int32 to System.Enum

In some cases with X++, an enum element value returned from a .NET Framework method is treated as a System.Int32 value in X++. You can call the System.Enum::ToObject method to convert the Int32 value into an enum element value.

The following X++ code example is artificially forced for simplicity. But it demonstrates how you can convert the Int32 value into an element value. In particular, it demonstrates the calls to the following two methods:

  - System.Object.GetType

  - System.Enum::ToObject

<!-- end list -->
```X++  
    static void GmEnumTest37Job(Args _args) // X++ job, in AOT > Jobs.
    {
        System.AttributeTargets  // Full .NET type name.
             enumAttribTarg1
            ,enumAttribTarg2;
        System.Type netSysType;
        System.Int32 netInt = -125;
        
        enumAttribTarg1 = System.AttributeTargets::Assembly;
        netInt = System.Convert::ToInt32(enumAttribTarg1);
        
        if (enumAttribTarg1 == netInt)
            { info("A_TRUE:    (enumAttribTarg1 == netInt)"); }
        else
            { info("A_FALSE:   (enumAttribTarg1 == netInt)"); }
        
        //  This conversion technique would fail to compile:
        //enumAttribTarg2 = netInt as System.AttributeTargets;
        
        //  This conversion technique succeeds:
        netSysType = enumAttribTarg1.GetType();
        enumAttribTarg2 = System.Enum::ToObject
            (netSysType, netInt);
        
        if (enumAttribTarg1 == enumAttribTarg2)
            { info("B_TRUE:    (enumAttribTarg1 == enumAttribTarg2)"); }
        else
            { info("B_FALSE:   (enumAttribTarg1 == enumAttribTarg2)"); }
    }
    /*****  Pasted from output:
    Message (04:24:27 pm)
    A_FALSE:   (enumAttribTarg1 == netInt)
    B_TRUE:    (enumAttribTarg1 == enumAttribTarg2)
    *****/
```
## Operator Limitations

When you work with .NET primitive types in X++ code, you can use the X++ equal sign (=) assignment operator. However, no other operators can be used with CLR primitives. For instance, you cannot use the comparison operators (such as == or \>). Also, you cannot use bitwise operators (such as & or |).

For more information about X++ operators with .NET primitive types, see [Operators for CLR Primitive Types](operators-for-clr-primitive-types.md).

## See also

[.NET Interop from X++](net-interop-from-x.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

