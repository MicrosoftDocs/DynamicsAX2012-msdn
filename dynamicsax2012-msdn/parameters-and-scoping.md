---
title: Parameters and Scoping
TOCTitle: Parameters and Scoping
ms:assetid: 34029c0e-82df-4fc4-a305-a5868e532044
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa635663(v=AX.60)
ms:contentKeyID: 35241997
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Parameters and Scoping 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

The scope rules in X++ state that all methods have their own scope. To use data from one scope in a different scope, you have to transfer the data from one scope into the other scope by using parameters.

A method can take one or more parameters. Within the scope of the method, these parameters are treated like local variables and are initialized with the value from the parameter in the method-call. The following table shows an example.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Class declaration</p></th>
<th><p>Method methodQ</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>class Parameter</p></td>
<td><p>void methodQ(int aval, real bval)</p></td>
</tr>
<tr class="even">
<td><p>{</p></td>
<td><p>{</p></td>
</tr>
<tr class="odd">
<td><p>    int a;</p></td>
<td><p>    a = aval;</p></td>
</tr>
<tr class="even">
<td><p>    real b;</p></td>
<td><p>    b = bval;</p></td>
</tr>
<tr class="odd">
<td><p>}</p></td>
<td><p>}</p></td>
</tr>
</tbody>
</table>


Here, a class called Parameter is declared. The class has a method (methodQ), which takes two parameters: an integer and a real. Four variables are visible within the scope of methodQ: aval, bval, a, and b. The a and b variables are in the scope because they are defined in the class declaration for the class.

Assume that ParameterObject is an instance of the Parameter class. If methodQ is invoked on ParameterObject,

ParameterObject.methodQ(1,2.0);

aval is set to the value 1 within the method and the variable bval is set to 2.0 (it is a real) within the method. The two variables a and b in the ParameterObject are set to 1 and 2.0, respectively. You can pass the value of any expression as a parameter.

## Parameters Are Passed by Value

All parameters are passed by value. You cannot change the value of the original variable—you can change only the local variable in the method, which is a copy of the original. The following table shows an example.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Class declaration</p></th>
<th><p>Method methodA</p></th>
<th><p>Method methodB</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>class ByValue</p></td>
<td><p>void methodA(int i)</p></td>
<td><p>void methodB()</p></td>
</tr>
<tr class="even">
<td><p>{</p></td>
<td><p>{</p></td>
<td><p>{</p></td>
</tr>
<tr class="odd">
<td><p>}</p></td>
<td><p>    i = i + 1;</p></td>
<td><p>    int i = 3;</p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p>    print i;</p></td>
<td><p>    print i;</p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p>}</p></td>
<td><p>    this.methodA(i);</p></td>
</tr>
<tr class="even">
<td><p></p></td>
<td><p></p></td>
<td><p>    print i;</p></td>
</tr>
<tr class="odd">
<td><p></p></td>
<td><p></p></td>
<td><p>}</p></td>
</tr>
</tbody>
</table>


Here, a class ByValue is declared with two methods: methodA and methodB.

methodB has a local variable named i, which is used as a parameter to a call methodA.

methodA uses a parameter called i and therefore has a local variable called i. This local variable has the value of the variable i in methodB (because it is used as a parameter in the call).

The result of invoking methodB is that the value of i is printed with its initial value in methodB (3), and then i is passed into methodA as a parameter and printed again with its new value (4). Finally, i is printed again with the value from methodB (3). This illustrates that the two i variables are two different variables.

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

