---
title: X++ Compiled to .NET CIL
TOCTitle: X++ Compiled to .NET CIL
ms:assetid: 02098aad-2028-4f59-b53f-6b0bd002b25a
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg839855(v=AX.60)
ms:contentKeyID: 35240123
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# X++ Compiled to .NET CIL [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

In Microsoft Dynamics AX, scheduled batch jobs written in X++ must first be compiled into the common intermediate language (CIL) of the .NET Framework. Therefore, X++ batches can sometimes complete much faster than if they were run as interpreted p-code.


> [!NOTE]
> <P>An older name for CIL was Microsoft intermediate language (MSIL).</P>



## Overview of the CIL Processes

The basic steps for running X++ source code as CIL are described in the following table.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Step</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Write, save, and compile your X++ class.</p></td>
<td><p>The X++ source code for your class is automatically compiled into p-code when you save the source in the AOT.</p></td>
</tr>
<tr class="even">
<td><p>Compile the p-code into CIL.</p></td>
<td><p>X++ is compiled into p-code. The p-code can be compiled into CIL by the following menu:</p>
<p><strong>AOT</strong> &gt; <strong>Add-ins</strong> &gt; <strong>Incremental CIL generation from X++</strong></p>
<p>Also, the toolbar on the development workspace has buttons for generating CIL.</p>

> [!note]  
> <P>If errors occur during the generation of CIL, consider temporarily suspending the antivirus software that is running on your AOS computer. The CIL generation process writes files to an AOS installation subdirectory. The directory path could resemble the following: C:\Program Files\Microsoft Dynamics AX\60\Server\MicrosoftDynamicsAX\bin\XppIL\</P>

</td>
</tr>
<tr class="odd">
<td><p>Recycle your multiple AOS services.</p></td>
<td><p>If your installation has more than one AOS, you must recycle every AOS service after the CIL build finishes.</p>
<p>The recycle causes each AOS to load the assembly that contains the updated CIL.</p></td>
</tr>
<tr class="even">
<td><p>Global ::runClassMethodIL</p></td>
<td><p>You can run your X++ code as CIL by using the method <a href="https://msdn.microsoft.com/en-us/library/gg802844(v=ax.60)">::runClassMethodIL</a>. See the code sample later in this topic.</p></td>
</tr>
<tr class="odd">
<td><p>Run the X++ method with a batch job.</p></td>
<td><p>Batch jobs run only on the AOS, not on the AX32.exe client. X++ classes that run on the AOS are run as CIL, not as p-code.</p>
<p>In the AOT, create a simple job that calls your method. Schedule the batch job. For more information, see <a href="walkthrough-extending-runbasebatch-class-to-create-and-run-a-batch.md">Walkthrough: Extending RunBaseBatch Class to Create and Run a Batch</a>.</p></td>
</tr>
</tbody>
</table>


## Code Sample Using runClassMethodIL

This section provides the X++ code for all the methods in a class that is named DemoClassCIL. You can create this class in the AOT.

The countNestedLoops method can be run by the X++ interpreter, or it can be run as CIL. The technique is to call the Global::runClassMethodIL method. This involves writing additional methods that wrap the countNestedLoops method. The method modifiers server static are necessary for this scenario.

The following countNestedLoops method is simple.
```X++  
    // Called by:  main, countNestedLoopsContainer.
    public server static str countNestedLoops(int _numOfLoops)
    {
        int runningSum = 0, ii, kk;
        
        for (ii = 0; ii < _numOfLoops; ii++)
        {
            for (kk = 0; kk < _numOfLoops; kk++)
            {
                runningSum++;
            }
        }
        return "Final sum is: " + int2str(runningSum);
    }
```
Next, the countNestedLoopsWrapper method takes in a container as its parameter, and returns another container. This is the signature that is required by the Global::runClassMethodIL method. Notice this method is intended to be private, not public.
```X++  
    // Called by:  countNestedLoopsWrapper.
    private server static container countNestedLoopsContainer(container _cNumOfLoops)
    {
        int runningSum = 0, ii, kk;
        int numOfLoops;
        str sSumInString;
        container cReturn;
    
        numOfLoops = conPeek(_cNumOfLoops, 1);
    
        sSumInString = DemoClassCIL::countNestedLoops(numOfLoops);
    
        return conPoke(cReturn, 1, sSumInString);
    }
```
Next, the countNestedLoopsWrapper method makes the call to the Global::runClassMethodIL method.
```X++  
    // Called by:  main.
    public server static str countNestedLoopsWrapper(int _numOfLoops)
    {
        container cFromCIL;
        
        new XppILExecutePermission().assert();
        
        cFromCIL = Global::runClassMethodIL
            ("DemoClassCIL",             // Or use classStr function.
            "countNestedLoopsContainer", // Or use staticMethodStr function.
            [_numOfLoops]
            );
        
        return conPeek(cFromCIL,1);
    }
```
Finally we have the main method which initiates the run of the scenario. The main method calls the countNestedLoops and countNestedLoopsWrapper methods. The durations of each method are compared.

To run this method, open its source code in the MorphX client code editor, and then press F5 or click the green arrow icon.
```X++  
    // Run this method, from the MorphX code editor,
    // or from a job under AOT > Jobs.
    public server static void main(Args _args)
    {
        int startTicksInterp, endTicksInterp;
        int startTicksCIL, endTicksCIL;
        str resultStrInterpreted, resultStrCIL;
        int numLoopsWanted = 987;
        
        // These first two calls ensure DLL files are loaded,
        // before we can do a fair comparison.    
        DemoClassCIL::countNestedLoops(numLoopsWanted);
        DemoClassCIL::countNestedLoopsWrapper(numLoopsWanted);
    
        startTicksInterp = WinAPIServer::getTickCount();
        resultStrInterpreted = DemoClassCIL::countNestedLoops(numLoopsWanted);
        endTicksInterp = WinAPIServer::getTickCount();
    
        startTicksCIL = WinAPIServer::getTickCount();
        resultStrCIL = DemoClassCIL::countNestedLoopsWrapper(numLoopsWanted);
        endTicksCIL = WinAPIServer::getTickCount();
        
        Global::info(strFmt
            ("%1 (Interpreted: %2), (CIL: %3).",
            resultStrCIL,
            endTicksInterp - startTicksInterp,
            endTicksCIL - startTicksCIL
            ));
    
    /*** Infolog output:
    Message_@SYS14327 (07:50:01 pm)
    Final sum is: 974169 (Interpreted: 406), (CIL: 0).
    ***/
    }
```
The **Infolog** message that is commented at the bottom of the main method shows that the CIL run completed much faster than the interpreted run.

## Methods on Queries and Forms Cannot Compile to CIL

Classes, tables, and enums are types in the X++ language. X++ types can be compiled to CIL. The queries and forms in the AOT are not X++ types, and they cannot be compiled to CIL. This means there are a few minor cases where calls from CIL to X++ p-code can cause an exception.

Suppose a method that is running as CIL calls a method on a query. The query method calls the ClassFactory system class of Microsoft Dynamics AX. This case causes an exception to be thrown. The problem is that the CIL session does not have access to all the system classes, yet the query method makes a call to a system class.

Your CIL code often cannot call query methods that call system classes. However, in Microsoft Dynamics AX some system classes have been re-implemented in CIL. These re-implementations enable some of the cases to succeed.

## See also

[X++ Scenarios that are Not Supported in CIL](x-scenarios-that-are-not-supported-in-cil.md)

[X++ Language Programming Guide](x-language-programming-guide.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

