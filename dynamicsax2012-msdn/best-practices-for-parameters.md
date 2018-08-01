---
title: Best Practices for Parameters
TOCTitle: Best Practices for Parameters
ms:assetid: 6d8caa01-be6f-4d21-a49b-be6f6d1481f2
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa610793(v=AX.60)
ms:contentKeyID: 35244803
ms.date: 05/18/2015
mtps_version: v=AX.60
dev_langs:
- csharp
---

# Best Practices for Parameters [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Parameters best practices are as follows:

  - Format as camel case. For example, forUpdate and recID.

  - Names begin with an underscore. For example, \_parameterName.

  - Do not use the business area prefix in the name unless it changes the meaning. For example, HcmBenefit \_benefit.

  - If omitting the business area prefix is the name changes the meaning then do provide the business area. For example, CustTable \_custTable.

  - Put each parameter/argument on a separate line. For an example of an X++ layout with more than one parameter, see [X++ Layout](x-layout.md)

  - Align the types and the parameter names horizontally. For example:

DialogField addField(

    int         \_type,

    FieldLabel  \_label = '',

    FieldHelp   \_help = '')

Example 2:

``` csharp
Class MyClass()
{ 
    MyType myVar;
    public MyType parmMyVar(MyType value = myVar)
    {
        myVar = value;
        return myVar;
    }
}
```

 Do not have unused parameters, unless you are overriding a method or implementing an interface. You will get a best practices warning ![Warning icon](images/Aa658028.WarningIcon(en-us,AX.60).gif "Warning icon") for unused parameters in private methods, and a best practices info ![Information icon](images/Aa658028.InfoIcon(en-us,AX.60).gif "Information icon") for unused parameters in public and protected methods. This is because the parameters might be used elsewhere in the class hierarchy.

## See also

[X++ Layout](x-layout.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

