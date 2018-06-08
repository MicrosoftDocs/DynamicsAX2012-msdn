---
title: Event Terminology and Keywords
TOCTitle: Event Terminology and Keywords
ms:assetid: b88499d1-40d7-4df7-8b7e-25ac0864879d
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg864037(v=AX.60)
ms:contentKeyID: 35249855
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Event Terminology and Keywords 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

In Microsoft Dynamics AX, you can use the event design pattern to make your X++ code more modular and reusable. The term event is a metaphor that explains how delegates are used.

## The Event Metaphor

When something important occurs during a program run, there might be other modules that need to process the occurrence. These important occurrences are called events. When an event occurs, the program tells its notifier for the event that the notifier must send notifications of the event. A notification must be sent to all the event handlers that are subscribers of the notifier. When the program tells its notifier to send the notifications, we call that raising an event.

### ![Gg864037.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg864037.collapse_all(en-us,AX.60).gif")Terms for Events

The following table displays the terms that are used to describe the event metaphor.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Metaphorical term</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>event</p></td>
<td><p>An important occurrence in a program module where additional modules must process the occurrence.</p></td>
</tr>
<tr class="even">
<td><p>notifier</p></td>
<td><p>The program element that sends information about the event to all the event handlers that are subscribed to the notifier.</p></td>
</tr>
<tr class="odd">
<td><p>subscriber</p></td>
<td><p>The program functions or methods that are subscribed to an event notifier.</p></td>
</tr>
<tr class="even">
<td><p>event handler</p></td>
<td><p>The methods that subscribe to an event notifier. Only the appropriate kind of methods can be event handlers.</p></td>
</tr>
</tbody>
</table>


## X++ Programming with Delegates

The event design pattern starts when you use the **AOT** \> **Classes** \> MyClass \> **New** \> **Delegate** menu to add a delegate to a class.

### ![Gg864037.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg864037.collapse_all(en-us,AX.60).gif")Keywords used for X++ Programming with Delegates

The following table shows the X++ keywords that describe the use of delegates in X++.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>X++ keyword or term</p></th>
<th><p>Code</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>delegate</p></td>
<td><p>delegate myDelegate(str _information) {}</p></td>
<td><p>The code shows how the delegate looks in the method editor in the MorphX client. The return type is always void, so it is not mentioned in the syntax. No code is allowed inside the {} braces.</p></td>
</tr>
<tr class="even">
<td><p>eventHandler</p></td>
<td><p>myClassInstance.myDelegate += eventHandler(otherClass.myInstanceMethod);</p></td>
<td><p>The syntax of the eventHandler keyword might give the impression that eventHandler is an X++ function, but it is not a function. The eventHandler keyword tells the compiler that a method is being subscribed to a delegate.</p></td>
</tr>
<tr class="odd">
<td><p>Subscribe or add a method to a delegate</p></td>
<td><p>myClassInstance.myDelegate += eventHandler(OtherClass::aStaticMethod);</p></td>
<td><p>The static method OtherClass::aStaticMethod becomes subscribed to the delegate.</p></td>
</tr>
<tr class="even">
<td><p>Call a delegate</p></td>
<td><p>myClassInstance.myDelegate(&quot;Hello&quot;);</p></td>
<td><p>This call to the delegate prompts the delegate to call each method that is subscribed to the delegate. The subscribed methods are called in the same sequence in which they were added to the delegate. One subscribed method must complete before the delegate calls the next method.</p></td>
</tr>
</tbody>
</table>


## See also

[X++, C\# Comparison: Event](x-csharp-comparison-event.md)

[X++ Language Programming Guide](x-language-programming-guide.md)

[Event Handler Nodes in the AOT](event-handler-nodes-in-the-aot.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

