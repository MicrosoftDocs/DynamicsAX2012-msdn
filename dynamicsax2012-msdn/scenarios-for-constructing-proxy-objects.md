---
title: Scenarios for Constructing Proxy Objects
TOCTitle: Scenarios for Constructing Proxy Objects
ms:assetid: 50a93340-7705-415b-9c3f-cd1cc7a523a3
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg862008(v=AX.60)
ms:contentKeyID: 35244205
ms.date: 05/18/2015
mtps_version: v=AX.60
dev_langs:
- csharp
---

# Scenarios for Constructing Proxy Objects [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

There are different scenarios for constructing a proxy object from a proxy class that is written in C\# or in another .NET Framework language:

  - Scenario 1: Implicit construction by parameter passing.

  - Scenario 2: Use a proxy object as input to construct a copy in a different namespace.

  - Scenario 3: Construct a Session object in C\#.

## Scenario 1: Implicit Construction by Parameter Passing

This scenario starts when an X++ job passes an X++ DictClass object to a C\# method. The C\# method takes a parameter type of a proxy for the X++ class DictClass. The system performs the marshaling by automatically constructing a proxy object from the DictClass object.

### ![Gg862008.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg862008.collapse_all(en-us,AX.60).gif")1a: The X++ Job

    static void StartInteropFromXppJob2a(Args _args)  // X++
    {
        DictClass dictClass2;
        int classId;
        str className;
    
        classId = classnum(DateTimeUtil);
        dictClass2 = new DictClass(classId);
    
        // Initiate interop from X++.
        className = CSharpDll.CSharpClass::CalledFromXppDc(dictClass2);
    
        info(strFmt("%1 , %2", classId, className));
    }
    /*** Output copied from the Infolog:
    64900 , DateTimeUtil
    ***/

### ![Gg862008.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg862008.collapse_all(en-us,AX.60).gif")1b: The C\# Method

The system automatically constructs a proxy object from the X++ DictClass object, and the C\# method receives the proxy as a parameter.

``` csharp
using System;  // C#
namespace CSharpDll
{
    public class CSharpClass
    {
        static public string CalledFromXppDc
                (MyProxyNamespace.DictClass pxyDictClass)
        {
            return pxyDictClass.name();
        }
    }
}
```

## Scenario 2: Use a Proxy Object as Input to Construct a Copy in a Different Namespace

A C\# application can have two proxy classes to the same X++ class, because the two proxies could have different namespaces. This section describes a scenario where you construct an instance of one proxy from an instance of the other, despite the namespace difference.

In the following example, at run time your C\# code has an instance of the proxy class Finance.TownBank. But your code must pass an Economics.TownBank object to a method. The namespaces do not match.

The solution is to construct an instance of the Economics.TownBank proxy class from the Finance.TownBank object. Your C\# code can use the following proxy constructor for this:

public Bank(Microsoft.Dynamics.AX.ManagedInterop.Object axObject)

After the constructor is called, both proxies reference the same TownBank object in Microsoft Dynamics AX. If one proxy changes the state of the underlying TownBank X++ object, the other proxy sees the changes.

``` csharp
// C# method to create a proxy object from an equivalent proxy object.
using System;
public TestTheProxy3
{
    public CloneAProxy(Finance.TownBank finBank)
    {
        Economics.TownBank ecoBank;
        Economics.AuditManager auditMgr;

        // Constructor call.
        ecoBank = new Economics.TownBank(finBank);

        auditMgr = new Economics.AuditManager();
        // Use the copy of the proxy, ecoBank.
        auditMgr.AuditABank(ecoBank);
    }
}
```

## Scenario 3: Construct a Session object in C\#

A C\# .exe program that is started from the console can construct an instance of the Microsoft.Dynamics.AX.ManagedInterop.Session class. Then the C\# code can call the constructor on a proxy class. For a code example, see [Walkthrough: Adding an X++ Object to a Visual Studio Project](walkthrough-adding-an-x-object-to-a-visual-studio-project.md).

### ![Gg862008.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg862008.collapse_all(en-us,AX.60).gif")Call Dispose on Proxy Objects

After your C\# executable program is finished using an instance of a proxy, we recommend that you call the Dispose method on the instance. A proxy might reference a large amount of unmanaged memory, and calling Dispose prompts the release of the memory. An example follows.

proxyCustTable.Dispose();

Next is another example that relies on the using block construct to call the Dispose method.

using (CustTable proxyCustTable = new CustTable())   
 {   
   // Use proxyCustTable here.   
 }  // Here the system calls the Dispose method on proxyCustTable.

## See also

[Proxy Classes for .NET Interop to X++](proxy-classes-for-net-interop-to-x.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

