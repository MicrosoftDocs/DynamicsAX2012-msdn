---
title: Best Practices for Accessor Methods
TOCTitle: Accessor Methods
ms:assetid: 45370ba7-3b81-459c-bb94-2f870acff719
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa627844(v=AX.60)
ms:contentKeyID: 35242970
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Best Practices for Accessor Methods 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

In Microsoft Dynamics AX classes, member variables are always protected; that is, they cannot be accessed directly from outside the class. They can only be accessed from within the objects of the class itself or its subclasses. To access the variables from outside, you have to write accessor methods.

Accessor methods can set, get, or get and set the value of a variable.

Accessor methods can be public or protected, and should have the same name as the member variable they access, prefixed with "parm." For example, the following accessor method gets and sets the MyVar variable.

```X++
public MyType parmMyVar(MyType _myVar = MyVar)
{
    ;

    MyVar = _myVar;
    return MyVar;
}
```

If the method needed only to get the value of the variable, it would be as follows.

```X++
public MyType parmMyVar()
{
    ;

    return MyVar;
}
```

When variables contain huge amounts of data (for example, large containers or memo fields), it is recommended that you use the technique in the following example. The disadvantage of using it in all cases is the overhead of an additional method call.

```X++
container parmCode(container _code = conNull())
{
    if (!prmIsDefault(_code))
    {
        code = _code;
    }

    return code;
}
```

> [!NOTE]
> <P>You can use a code editor script to automatically create the accessor method. In the code editor, press ALT+M to open the editor scripts menu, and then select <STRONG>Template</STRONG> &gt; <STRONG>Method</STRONG> &gt; <STRONG>parm</STRONG>. Enter the data type, and then the name of the variable.</P>



## See also

[Best Practices for Constructors](best-practices-for-constructors.md)

[Best Practices for init Methods](best-practices-for-init-methods.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

