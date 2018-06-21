---
title: Reflect on .NET Elements of X++ Methods
TOCTitle: Reflect on .NET Elements of X++ Methods
ms:assetid: 2f616dec-a261-4d89-860e-fede18c37154
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh272119(v=AX.60)
ms:contentKeyID: 36536729
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Reflect on .NET Elements of X++ Methods [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

In Microsoft Dynamics AX, the DictMethod system class has reflection methods that can report on the .NET Framework types that an X++ method uses. The .NET Framework types can be used for parameters, local variables, the return type, and more.

## Code Example with the DictMethod System Class

The following code example shows how you can use the DictMethod system class to reflect on the .NET Framework elements of an X++ method. The specific types that reflection finds are determined by the DictMethod methods that are called. In the code example the following methods are among those that are called, and their method names explain the types that are targeted for reflection:

  - clrParameterType

  - clrReturnType

  - clrVarType

The most important part of the code example is the letsReflectNow method. It constructs a DictMethod object by passing in the name of the X++ method to reflect on. It also passes in the name of the X++ class that the X++ method belongs to.

    public class ReflectDemoClass3  // X++ class.
    {
        /// <summary>
        /// This static Main method is run from developer environment,
        /// by double-clicking its node in the AOT.
        /// This method runs the rest of the demonstration.
        /// </summary>
        static public void Main(Args _args)
        {
            ReflectDemoClass3 rdemo3;
            gm3 = new ReflectDemoClass3();
            gm3.letsReflectNow();
        }
    
        /// <summary>
        /// Calls reflection methods on the DictMethod system class.
        /// </summary>
        public void letsReflectNow()
        {
            str computedType;
            DictMethod dm;
    
            dm = new DictMethod
                (UtilElementType::ClassInstanceMethod,
                classnum(ReflectDemoClass3),
                'methodNetParamReturn1'
                );
            computedType = dm.clrParameterType(1); // 1 means the first parameter.
            info(strFmt("Param_1: computedType == %1",computedType));
    
            computedType = dm.clrReturnType();
            info(strFmt("Return type: computedType == %1",computedType));
    
            computedType = dm.clrVarType(2);
            info(strFmt("Local_var_2: computedType == %1",computedType));
    
    
            computedType = this.methodNetParamReturn1(42);
            info(strFmt("Returned_string: computedType == %1",computedType));
    
    /*****  Infolog output:
    Message_@SYS14327 (03:49:08 pm)
    Param_1: computedType == System.Int32
    Return type: computedType == System.String
    Local_var_2: computedType == System.DateTime
    Returned_string: computedType == Input param was 42, at 5/16/2011 3:49:07 PM
    *****/
        }
    
        /// <summary>
        /// This method is the target of reflection by method letsReflectNow.
        /// </summary>
        public System.String methodNetParamReturn1  // Reflect me.
                (System.Int32 _netInt32)
        {
            System.String netString;
            System.DateTime netDtTm;
            str strTemp9, strTemp8, strTemp7;
      
            netDtTm = System.DateTime::get_Now();
    
            strTemp8 = _netInt32.ToString();
            strTemp9 = netDtTm.ToString();
    
            strTemp7 = strFmt("Input param was %1, at %2",
                strTemp8, strTemp9);
            netString = strTemp7;
    
            return netString;
        }
    }

### ![Hh272119.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Hh272119.collapse_all(en-us,AX.60).gif")How to Run the X++ Code Example

You can run the X++ example by following these steps:

1.  Create the ReflectDemoClass33 under **AOT** \> **Classes**.

2.  Add the three methods, Main and letsReflectNow and methodNetParamReturn1, to the ReflectDemoClass33 class.

3.  Paste the X++ code from the example into those new methods by using the code editor.

4.  Double-click the Main method in the AOT. The **Infolog** window appears with the output.

## See also

[.NET Interop from X++](net-interop-from-x.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

