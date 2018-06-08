---
title: 'X++, C# Comparison: Event'
TOCTitle: 'X++, C# Comparison: Event'
ms:assetid: f871bca1-98e8-48cc-82bc-ba5ff77403b8
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg881685(v=AX.60)
ms:contentKeyID: 35253717
ms.date: 05/18/2015
mtps_version: v=AX.60
dev_langs:
- csharp
---

# X++, C\# Comparison: Event 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

There are some differences in how X++ and C\# implement the event design pattern. For more information, see [Event Terminology and Keywords](event-terminology-and-keywords.md).

## Comparison of Events between X++ and C\#

There are differences in the way delegates are used for events in X++ versus C\#.

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Item</p></th>
<th><p>X++</p></th>
<th><p>C#</p></th>
<th><p>Comment</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>delegate</p></td>
<td><p>In X++, a delegate can be declared only as a member on a class. A delegate cannot be a member on a table.</p>
<p>All delegates are instance members of their class, not static members. No access modifier can be used on a delegate declaration, because all delegates are protected members. Therefore, the event can be raised only by code within the same class where the delegate is a member. However, the one exception to the private nature of a delegate is that code outside their class can operate on the delegates by using the += and -= operators.</p></td>
<td><p>In C#, each delegate is a type, just as every class is a type. A delegate is declared independently of any class.</p>
<p>Without the event keyword, you can have a delegate as a parameter type on a method, just as you can have a class as a parameter type. You can construct an instance of a delegate to pass in for the parameter value.</p></td>
<td><p>In X++, each class is a type, but no delegate is a type. You cannot construct an instance of a delegate. No delegate can be a parameter for a method. But you can create a class that has a delegate member, and you can pass instances of the class as parameter values.</p>
<p>For more information, see <a href="x-keywords.md">X++ Keywords</a>.</p></td>
</tr>
<tr class="even">
<td><p>event</p></td>
<td><p>In X++ code, an event is one of the following:</p>
<ul>
<li><p>An explicit call to a delegate.</p></li>
<li><p>The start or end of a method.</p></li>
</ul>
<p>There is no event keyword in X++.</p>
<p></p></td>
<td><p>In C#, the event keyword is used to declare a delegate type as a member of a class. The effect of the event keyword is to make the delegate protected, yet still accessible for the += and -= operators. You can subscribe event handler methods to an event by using the += operator.</p>
<p>A delegate can be useful without the event keyword, as a technique for passing a function pointer as a parameter into a method.</p></td>
<td><p>The automatic events that occur before the start of a method, and after the end of a method, can be subscribed to only by using the AOT.</p></td>
</tr>
<tr class="odd">
<td><p>+= and -= operators</p></td>
<td><p>In X++, you use the += operator to subscribe methods to a delegate. The -= operator unsubscribes a method from a delegate.</p></td>
<td><p>In C#, you use the += operator to subscribe methods to an event, or to a delegate that is not used with the event keyword.</p></td>
<td><p>The delegate contains a reference to all the objects that have methods subscribed to the delegate. Those objects are not eligible for garbage collection while delegate holds those references.</p></td>
</tr>
<tr class="even">
<td><p>eventHandler</p></td>
<td><p>In X++, the eventHandler keyword is required when you use either the += or -= operator to subscribe or unsubscribe a method from a delegate.</p></td>
<td><p>System.EventHandler is a delegate type in the .NET Framework.</p></td>
<td><p>This term is used differently in X++ than it is in C# or the .NET Framework.</p>
<p>For more information, see <a href="x-keywords.md">X++ Keywords</a>.</p></td>
</tr>
</tbody>
</table>


## X++ and C\# Code Examples

This section contains an X++ code example for the event design pattern. It also contains a C\# code sample for the same design pattern.

### ![Gg881685.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg881685.collapse_all(en-us,AX.60).gif")X++ Example

The important things to notice in the X++ example are the following:

  - The XppClass has a delegate member that is named myDelegate.
    

    > [!NOTE]
    > <P>The AOT contains a node for the delegate. The node is located at <STRONG>AOT</STRONG> &gt; <STRONG>Classes</STRONG> &gt; <STRONG>XppClass</STRONG> &gt; <STRONG>myDelegate</STRONG>. Several event handler nodes can be located under the <STRONG>myDelegate</STRONG> node. Event handlers that are represented by nodes in the AOT cannot be removed by the -= operator during run time.</P>



  - The {} braces at the end of the delegate declaration are required, but they cannot have any code in them.

  - The XppClass has two methods whose parameter signatures are compatible with the delegate. One method is static.

  - The two compatible methods are added to the delegate with the += operator and the eventHandler keyword. These statements do not call the event handler methods, the statements only add the methods to the delegate.

  - The event is raised by one call to the delegate.

  - The parameter value that passed in to the delegate is received by each event handler method.

  - The short X++ job at the top of the example starts the test.

<!-- end list -->

    // X++
    // Simple job to start the delegate event test.
    static void DelegateEventTestJob()
    {
        XppClass::runTheTest("The information from the X++ job.");
    }
    
    
    // The X++ class that contains the delegate and the event handlers.
    class XppClass
    {
        delegate void myDelegate(str _information)
        {
        }
    
        public void myEventSubscriberMethod2(str _information)
        {
            info("X++, hello from instance event handler 2: " + _information);
        }
    
        static public void myEventSubscriberMethod3(str _information)
        {
            info("X++, hello from static event handler 3: " + _information);
        }
    
        static public void runTheTest(str _stringFromJob)
        {
            XppClass myXppClass = new XppClass();
    
            // Subscribe two event handler methods to the delegate.
            myXppClass.myDelegate += eventHandler
                    (myXppClass.myEventSubscriberMethod2);
            myXppClass.myDelegate += eventHandler
                    (XppClass::myEventSubscriberMethod3);
    
            // Raise the event by calling the delegate one time,
            // which calls all the subscribed event handler methods.
            myXppClass.myDelegate(_stringFromJob);
        }
    }

The output from the previous X++ job is as follows:

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>X++, hello from static event handler 3: The information from the X++ job.</p>
<p>X++, hello from instance event handler 2: The information from the X++ job.</p></td>
</tr>
</tbody>
</table>


### ![Gg881685.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg881685.collapse_all(en-us,AX.60).gif")C\# Sample

This section contains a C\# code sample for the event design pattern of the previous X++ sample.

``` csharp
// C#
using System;

// Define the delegate type named MyDelegate.
public delegate void MyDelegate(string _information);

public class CsClass
{
    protected event MyDelegate MyEvent;

    static public void Main()
    {
        CsClass myCsClass = new CsClass();

        // Subscribe two event handler methods to the delegate.
        myCsClass.MyEvent += new MyDelegate
                (myCsClass.MyEventSubscriberMethod2);
        myCsClass.MyEvent += new MyDelegate
                (CsClass.MyEventSubscriberMethod3);

        // Raise the event by calling the event one time, which
        // then calls all the subscribed event handler methods.
        myCsClass.MyEvent("The information from the C# Main.");
    }

    public void MyEventSubscriberMethod2(string _information)
    {
        Console.WriteLine("C#, hello from instance event handler 2: " + _information);
    }

    static public void MyEventSubscriberMethod3(string _information)
    {
        Console.WriteLine("C#, hello from static event handler 3: " + _information);
    }
}
```

The output from the previous C\# sample is as follows:

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>&gt;&gt; CsClass.exe</p>
<p>C#, hello from instance event handler 2: The information from the C# Main.</p>
<p>C#, hello from static event handler 3: The information from the C# Main.</p></td>
</tr>
</tbody>
</table>


## Events and the AOT

Microsoft Dynamics AX has other event systems that apply only to items in the AOT. For more information, see [Event Handler Nodes in the AOT](event-handler-nodes-in-the-aot.md).

## See also

[Event Terminology and Keywords](event-terminology-and-keywords.md)

[X++, C\# Comparisons](x-csharp-comparisons.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

