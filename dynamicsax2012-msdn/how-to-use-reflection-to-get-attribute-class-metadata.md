---
title: 'How to: Use Reflection to Get Attribute Class Metadata'
TOCTitle: 'How to: Use Reflection to Get Attribute Class Metadata'
ms:assetid: 7b0c7602-aded-4840-9a2e-0372bdc33b27
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg862476(v=AX.60)
ms:contentKeyID: 35246089
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Use Reflection to Get Attribute Class Metadata [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

You can use the DictMethod class in X++ reflection code to discover the metadata value of an attribute that is decoration on an X++ method.

This topic gives a code sample that you can copy, compile, and run. The sample is dedicated to the SysEntryPointAttribute class as the attribute. The code sample accepts your parameter values for the method name, and for the name of the class that contains the method.

## X++ Code Sample

This code sample is a static method. In a comment block at the bottom is code for a small AOT job that runs the method. The sample assumes the method is a member of a class named AttributeReflection, but you can change that name.

The parmChecked method is particular to the SysEntryPointAttribute class, and it is not inherited from its base class SysAttribute. Each attribute class can have its own method name for its metadata.

```X++
    static public int MetadataOfSysEntryPointAttributeOnMethod
                (
                str _sNameOfClass,
                str _sNameOfMethod
                )
    {
        // Return Values:
        // 0 == Has the attribute, its metadata value is false;
        // 1 == Has the attribute, its metadata value is true;
        // 2 == The method lacks the SysEntryPointAttribute.
    
        int nReturnValue = -1,
            nClassId;
        boolean boolParmChecked;
        
        DictMethod dm;
        Object attributeAsObject;
        SysEntryPointAttribute sepAttribute;
        
        Global::info("Starting AttributeReflection" 
            + " ::MetadataOfSysEntryPointAttributeOnMethod ....");
        Global::info(strFmt
            ("Parameters are: _sNameOfClass = %1 ,  _sNameOfMethod = %2 .", 
            _sNameOfClass, _sNameOfMethod)
            );
        
        nClassId = Global::className2Id(_sNameOfClass);
        
        dm = new DictMethod
            (UtilElementType::ClassInstanceMethod,
            nClassId,
            _sNameOfMethod
            );
        
        attributeAsObject = dm.getAttribute("SysEntryPointAttribute");
        
        if (attributeAsObject is SysEntryPointAttribute)
        {
            sepAttribute = attributeAsObject as SysEntryPointAttribute;
        
            boolParmChecked = sepAttribute.parmChecked();
            
            if (boolParmChecked)
                nReturnValue = 1;
            else
                nReturnValue = 0;
            
            Global::info(
                strFmt("Return value is %1.",
                    nReturnValue)
                );
        }
        else
        {
            nReturnValue = 2;
            Global::error("Object is not a SysEntryPointAttribute??");
        }
    
        return nReturnValue;
    }
    /*** Output displayed in the Infolog.
    Message (05:03:22 pm)
    Starting AttributeReflection ::MetadataOfSysEntryPointAttributeOnMethod ....
    Parameters are: _sNameOfClass = CustCustomerService ,  _sNameOfMethod = create .
    Return value is 1.
    ***/
    
    
    /**************
    
    // Simple AOT > Jobs job to run the method.
    
    static void AttributeReflection33Job(Args _args)
    {
        AttributeReflection::MetadataOfSysEntryPointAttributeOnMethod
            ("CustCustomerService", "create");
    }
    
    **************/
```

## See also

[Attributes on X++ Types and Methods](attributes-on-x-types-and-methods.md)

[DictMethod Class](https://msdn.microsoft.com/en-us/library/gg842356\(v=ax.60\))

[SysEntryPointAttribute Class](https://msdn.microsoft.com/en-us/library/gg958657\(v=ax.60\))

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

