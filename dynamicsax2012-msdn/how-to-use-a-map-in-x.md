---
title: 'How to: Use a Map in X++'
TOCTitle: 'How to: Use a Map in X++'
ms:assetid: 81f0217c-a24f-4da7-8390-0405549d11d9
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Ee330226(v=AX.60)
ms:contentKeyID: 35246148
ms.date: 05/18/2015
mtps_version: v=AX.60
description: Master the use of AOT map objects in X++ with Microsoft Dynamics AX. Learn syntax, examples, and error detection for efficient runtime.
---

# How to: Use a Map in X++ 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

You need unusual X++ syntax to use an AOT map object in Microsoft Dynamics AX. Some of the X++ statements are late-bound, and errors in them cannot be detected until run time.

## Example of Using a Map in X++

The following sections describe the AOT objects for an example of using a map in X++. The objects would be found in the following AOT locations:

  - **AOT** \> **Data Dictionary** \> **Tables**

  - **AOT** \> **Data Dictionary** \> **Maps**

  - **AOT** \> **Jobs**

### ![Ee330226.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Ee330226.collapse_all(en-us,AX.60).gif")The Tables

The following table presentation describes the two tables that are used in the example.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Table name</p></th>
<th><p>Fields</p></th>
<th><p>Methods</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>TabPhone</p></td>
<td><p>brandName</p>
<p>batteryVoltage1</p></td>
<td><p>public void doubleTheVoltage()</p></td>
</tr>
<tr class="even">
<td><p>TabClock</p></td>
<td><p>brandName</p>
<p>batteryVoltage2</p></td>
<td><p>public void doubleTheVoltage(str _comment)</p></td>
</tr>
</tbody>
</table>


### ![Ee330226.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Ee330226.collapse_all(en-us,AX.60).gif")The Map

The following table presentation is designed to mimic the node hierarchy of the AOT for a map. The **MapDevice** node would be located under **AOT** \> **Data Dictionary** \> **Maps**.

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p><strong>MapDevice</strong></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p><strong>Fields</strong></p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p></p></td>
<td><p><strong>brandName</strong></p>
<p><strong>batteryVoltage3</strong></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p><strong>Mappings</strong></p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p></p></td>
<td><p><strong>TabClock</strong></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p><strong>MapDevice.brandName == TabClock.brandName</strong></p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p><strong>MapDevice.batteryVoltage3 == TabClock.batteryVoltage2</strong></p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p></p></td>
<td><p><strong>TabPhone</strong></p></td>
<td><p></p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p><strong>MapDevice.brandName == TabPhone.brandName</strong></p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p></p></td>
<td><p></p></td>
<td><p><strong>MapDevice.batteryVoltage3 == TabPhone.batteryVoltage1</strong></p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p><strong>Methods</strong></p></td>
<td><p></p></td>
<td><p></p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p></p></td>
<td><p><strong>public void doubleTheVoltage(str _comment)</strong></p>
<p><strong>public int getTheVoltage()</strong></p></td>
<td><p></p></td>
</tr>
</tbody>
</table>


### ![Ee330226.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Ee330226.collapse_all(en-us,AX.60).gif")The X++ Job Code

The following X++ job code shows the important lines of code for using a map in X++ code. The comments are discussed in more detail in a section that follows the code.
```X++  
    // X++ job.
    static void MapJob()
    {
        MapDevice mDevice;
        TabClock tClock;
        TabPhone tPhone;
        ;
        // 1: Call the method as it is implemented on the map.
        mDevice.doubleTheVoltage("Testing");
    
        // 2: Twice, call a method that is defined in the AOT under MapDevice > Methods.
        mDevice.getTheVoltage();
        mDevice.MapDevice::getTheVoltage();
    
        // 3: Activate the TabClock mapping on the map.
        mDevice = tClock;
    
        // 4: Set fields that are defined in the AOT under MapDevice > Fields.
        mDevice.brandName = "Contoso";
        mDevice.batteryVoltage3 = 9;
    
        // 5: Call an inherited method. The toString method returns "Class xRecord".
        print mDevice.toString();
    
        // 6: Call a method that is defined in the AOT only under MapDevice > Methods.
        mDevice.MapDevice::getTheVoltage();
    
        // 7: Call the method as it is implemented on the table.
        mDevice.doubleTheVoltage("Testing");
    }
```
#### ![Ee330226.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Ee330226.collapse_all(en-us,AX.60).gif")Elaboration of the X++ Job Comments

The following table presentation discusses the // comments from the previous X++ job code example.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Comment in X++ job</p></th>
<th><p>Discussion</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>// 1: Call the method as it is implemented on the map.</p></td>
<td><p>The method name doubleTheVoltage is used in both tables and in the map. No table buffer has yet been assigned to the map. Therefore, this call to mDevice.doubleTheVoltage(&quot;Testing&quot;) is understood by the X++ runtime engine to refer to the method defined on the map itself.</p>
<p>The compiler cannot know whether the call will be valid during run time. The compiler does not know whether a buffer for the TabPhone table will first be assigned to the map variable, which would make the call invalid. Therefore, this is a late-bound call, and final validation of this call occurs at run time.</p></td>
</tr>
<tr class="even">
<td><p>// 2: Twice, call a method that is defined in the AOT under MapDevice &gt; Methods.</p></td>
<td><p>The second of these two calls has the extra segment MapDevice:: in its syntax. Because no table buffer has yet been assigned to the map, this extra segment is optional at this point in the code.</p></td>
</tr>
<tr class="odd">
<td><p>// 3: Activate the TabClock mapping on the map.</p></td>
<td><p>The assignment mDevice = tClock succeeds because the map has a mapping for the TabClock table. The fields of the map now reference the values of their corresponding fields in the tClock table buffer.</p></td>
</tr>
<tr class="even">
<td><p>// 4: Set fields that are defined in the AOT under MapDevice &gt; Fields.</p></td>
<td><p>In these assignment statements, the only field names that the map variable can reference are those that appear in the AOT under <strong>Maps</strong> &gt; <strong>MapDevice</strong> &gt; <strong>Fields</strong>. Field names from the table buffer cannot be used.</p></td>
</tr>
<tr class="odd">
<td><p>// 5: Call an inherited method. The toString method returns &quot;Class xRecord&quot;.</p></td>
<td><p>The toString method is the implementation from the xRecord class.</p></td>
</tr>
<tr class="even">
<td><p>// 6: Call a method that is defined in the AOT only under MapDevice &gt; Methods.</p></td>
<td><p>The method name getTheVoltage occurs only on the map, not on either table in this example. Despite the uniqueness of the method name, the call mDevice.MapDevice::getTheVoltage() to this method must include the segment MapDevice::. This segment would be optional if no table buffer had been assigned to the map.</p></td>
</tr>
<tr class="odd">
<td><p>// 7: Call the method as it is implemented on the table.</p></td>
<td><p>The method name doubleTheVoltage occurs on both tables and on the map. From the three available implementations of the method, the implementation that is invoked by mDevice.doubleTheVoltage(&quot;Testing&quot;) depends on whether a table buffer has been assigned to the map variable. At this point in the code, a table has been assigned to the map. Therefore, the call must contain no additional qualifiers.</p>
<p>This called method is implemented on the TabClock table. However, it is not valid to explicitly qualify with the table or mapping name, as in mDevice.TabClock::doubleTheVoltage(“Testing”).</p></td>
</tr>
</tbody>
</table>


## See also

[Tables, Views, and Maps](tables-views-and-maps.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

