---
title: Static Methods
TOCTitle: Static Methods
ms:assetid: 0ddcfbe9-8ea2-4948-95cb-3cb517972157
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa584754(v=AX.60)
ms:contentKeyID: 35240456
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Static Methods 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

In X++ you can decorate a method with the static keyword. This keyword instructs the system to create only one instance of the method regardless of how many instances of its class you create. This single instance is used throughout your Microsoft Dynamics AX session.

Static methods are generally intended for cases where the following criteria are met:

  - The method has no reason to access the member variables that are declared in the **classDeclaration** block of the class.

  - The method has no reason to call any instance (non-static) methods of the class.

## Syntax

### ![Aa584754.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa584754.collapse_all(en-us,AX.60).gif")Declaring a Static Method

Consider the example of a software key type that is used for piracy prevention. Each instance of a software key can have its own unique value. But all software keys must conform to the rules of software key design. Therefore the logic to test for software key conformance is the same for all software keys. The method that contains the conformance validation logic should be static. Here is an example of a method that is declared with the static keyword:

static public boolean validateSoftwareKey(str \_softwareKeyString)   
 {   
     // X++ code here.   
 }

### ![Aa584754.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa584754.collapse_all(en-us,AX.60).gif")Calling a Static Method

In the following example, there is no need to first construct an instance of the SoftwareKey class before you call a static method on the class. To call the static method validateSoftwareKey, the syntax starts with the name of the class that contains the method. A pair of colon (::) characters is used to connect the class name to the static method name.

boolean yourBool = SoftwareKey::validateSoftwareKey(yourSoftwareKeyString);

## See also

[Declaration of Methods](declaration-of-methods.md)

[Method Modifiers](method-modifiers.md)

[Best Practices for Method Modifiers](best-practices-for-method-modifiers.md)

[Methods in X++](methods-in-x.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

