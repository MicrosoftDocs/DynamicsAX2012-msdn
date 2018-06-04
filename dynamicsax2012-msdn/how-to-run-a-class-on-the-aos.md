---
title: 'How to: Run a Class on the AOS'
TOCTitle: 'How to: Run a Class on the AOS'
ms:assetid: cce3c605-d3ec-4292-9cf7-c364987c430c
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc620031(v=AX.60)
ms:contentKeyID: 35251653
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Run a Class on the AOS 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

In Microsoft Dynamics AX, you can specify whether a class, class instance, or class method will execute on the Application Object Server (AOS) or the client. This topic describes where classes and class static methods are run and how to change the location of where a class runs.

Classes have a property called RunOn with the following values:

  - Client

  - Called from (default setting)

  - Server

Objects created from the class exist at the location specified. For example, if the RunOn property for a class is set to Called from, the object will run where the code instantiating the object is running.

Classes that extend or inherit from another class also inherit the RunOn property. If the inherited RunOn property value is set to Client or Server, it cannot be modified. If the inherited RunOn property is set to Called from, it can be modified in the property settings for the class.

By default, class and table static methods run in the same location as the class object. To modify the default setting, you can add client or server, or both, to the class static method declaration. When the class object is set to client or server, you can add both client and server to the method declaration to set the RunOn property of a static method to Called from.

For more information, see [Application Object RunOn Property Overview](application-object-runon-property-overview.md).

### To run a class on the AOS

1.  In the Application Object Tree (AOT), expand the **Classes** node.

2.  In the **Classes** node, right-click the class template that you want to run on the AOS, and then click **Properties**.

3.  In the **Properties** sheet, set the RunOn property to Server.

4.  In the AOT, right-click the modified class, and then click **Save**.

### To modify the RunOn property of a class static method

1.  In the AOT, expand the **Classes** node, and then expand the class that contains the static method that you want to modify.

2.  Right-click the static method that you want to modify, and then click **Edit**. The **Class Editor** window opens.

3.  In the **Class Editor**, enter one of the following static method declaration modifiers.
    
        // Sets the RunOn property to Called from.
        client server static boolean myMethod()
        {
            // ToDo Insert code here.
        }
    
    \- or -
    
        // Sets the RunOn property to Client.
        client static boolean myMethod()
        {
            // ToDo Insert code here.
        }
    
    \- or -
    
        // Sets the RunOn property to Server.
        server static boolean myMethod()
        {
            // ToDo Insert code here.
        }

4.  In the AOT, right-click the modified class, and then click **Save**.

## See also

[AOS Overview](aos-overview.md)

[Developing Applications Using the AOS](developing-applications-using-the-aos.md)

[Best Practices: Application Object Server (AOS)](best-practices-application-object-server-aos.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

