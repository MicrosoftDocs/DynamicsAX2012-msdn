---
title: 'How to: Modify the Return Value in an Post-Method Event Handler'
TOCTitle: 'How to: Modify the Return Value in an Post-Method Event Handler'
ms:assetid: 0ea8a299-9f87-4330-aeab-87e39610df0f
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg843664(v=AX.60)
ms:contentKeyID: 35240484
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Modify the Return Value in an Post-Method Event Handler 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

You can assign a static method to be an event handler that starts when a specific method on a class ends. This is called an after-method event handler, or a post-method event handler. In the AOT, you assign the event handler as a node under the method node. The **CalledWhen** property on the event handler node must be set to **Post**.

The post-method event handler can modify the return value of the completed method, before the return value is given to the method caller.

For background information about event handler nodes, see [Event Handler Nodes in the AOT](event-handler-nodes-in-the-aot.md).

## The AOT Elements

The following table displays the AOT elements that work together to process the event.




<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>AOT element type</p></th>
<th><p>X++ Code sample</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Plain method: as a member of a class.</p></td>
<td><pre><code>public int numberOfExpectedAttendees
        (int _numOfInvites, int _numOfDeclines)
{
    return _numOfInvites - _numOfDeclines;
}</code></pre></td>
</tr>
<tr class="even">
<td><p>Event handler: starts as a method of a class.</p></td>
<td><pre><code>// CalledWhen = Post.
static public void numberOfExpectedAttendeesEhAfter
        (XppPrePostArgs ppArgs)
{
    int intAttendees;
    //
    intAttendees = any2Int(ppArgs.getReturnvalue());
    info(strFmt(&quot;%1 = intAttendees raw, in event handler.&quot;, intAttendees));
    if (0 &gt; intAttendees)
    {
        intAttendees = 0;
        ppArgs.setReturnValue(intAttendees);
    }
}</code></pre></td>
</tr>
<tr class="odd">
<td><p>Node relationship in the AOT.</p></td>
<td><p>In the following image, notice that the <strong>numberOfExpectedAttendees</strong> method has a child node for the <strong>numberOfExpectedAttendeesEhAfter</strong> event handler. This node is created by dropping a static method</p>
<img src="images/Gg862568.AOTEventHandlerHierarchies(en-us,AX.60).jpg" title="AOT event handler hierarchies" alt="AOT event handler hierarchies" />
<p><strong>AOT nodes for a method and its event handler</strong></p>
<p>By coincidence, the method node for the <strong>numberOfExpectedAttendeesEhAfter</strong> method is also on this same <strong>TestClass</strong> class.</p></td>
</tr>
<tr class="even">
<td><p>Job: to run the simple method.</p></td>
<td><pre><code>static void Job2ReturnTestEhAfter(Args _args)
{
    TestClass testClass9;
    int attendeeCountReturned;
    //
    testClass9 = new TestClass();
    // Run a method that has an event handler that starts after the method finishes.
    attendeeCountReturned = testClass9.numberOfExpectedAttendees(8, 13);
    // The Infolog output displays the effect of the after-method event handler.
    info(strFmt
        (&quot;%1 == the number of expected attendees.&quot;,
        attendeeCountReturned));
}
/*** Output displayed in the Infolog:
0 == the number of expected attendees.
***/</code></pre></td>
</tr>
</tbody>
</table>


## See also

[How to: Modify Parameter Values in a Pre-Method Event Handler](how-to-modify-parameter-values-in-a-pre-method-event-handler.md)

[Walkthrough: Subscribing an Event Handler to a Delegate in the AOT](walkthrough-subscribing-an-event-handler-to-a-delegate-in-the-aot.md)

[Event Handler Nodes in the AOT](event-handler-nodes-in-the-aot.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

