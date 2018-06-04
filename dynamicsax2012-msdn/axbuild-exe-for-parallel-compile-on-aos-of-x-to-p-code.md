---
title: AxBuild.exe for Parallel Compile on AOS of X++ to p-code
TOCTitle: AxBuild.exe for Parallel Compile on AOS of X++ to p-code
ms:assetid: d6da631b-6a9d-42c0-9ffe-26c5bfb488e3
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Dn528954(v=AX.60)
ms:contentKeyID: 59641342
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# AxBuild.exe for Parallel Compile on AOS of X++ to p-code 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2_

AxBuild.exe can accomplish a full compile of all X++ code, into AX p-code, many times faster than the traditional compile that you start from the MorphX client menu. AxBuild.exe is run on the Application Object Server (AOS) tier at a cmd.exe command prompt. This topic explains what AxBuild.exe does and how to use it.

The AxBuild.exe utility program involves compiles to p-code only, and it does not go further by compiling to .NET Framework CIL.

AxBuild.exe became available in cumulative update 7 for Microsoft Dynamics AX 2012 R2.


> [!WARNING]
> <P>You should stop the AOS service before you start AxBuild.exe. Otherwise in certain scenarios, the AxBuild.exe service might provide outdated metadata or outdated p-code to the compile process.</P>



## A.  General Architecture

 

### ![Dn528954.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Dn528954.collapse_all(en-us,AX.60).gif")A.1  Compiling on the Server Tier

AxBuild.exe is installed in the same directory with ax32serv.exe, which is the program name for the AOS. Despite the 32 in its name, ax32serv.exe is a 64 bit program. As a 64 bit program, ax32serv.exe can address much more active memory than the 32 bit client ax32.exe can. The larger amount of active memory might be important for full X++ compiles that involve an extremely large amount of X++ source code.

AxBuild.exe starts several new but temporary instances of the AOS. From the Registry, each temporary AOS uses the same configuration information that is used by a permanent AOS that you identify with the /aos parameter. This is one reason why AxBuild.exe must be run by an account that has no less security authority than the account that runs the permanent AOS has.

![Server config displays the AOS instance number](images/Dn528954.AxBuildExe-AxSrvCfg-Exe-AOS-InstanceNum-param-aos-c36(en-us,AX.60).png "Server config displays the AOS instance number")

**Server configuration displays the AOS instance number for the /aos parameter**

AxBuild.exe coordinates the work of every temporary AOS that it starts. It tells each AOS which pieces of the full X++ compile to accomplish. It gathers the results from each AOS and reports them to the console and a log file.

![X++ on the AOS tier with AxBuild.exe](images/Dn528954.AxBuildExe-Visio-Server-s(en-us,AX.60).png "X++ on the AOS tier with AxBuild.exe")

**Architecture of the X++ compile on the AOS tier**

An earlier compile option involved new but temporary instances of ax32serv.exe to which you could pass a now obsolete parameter. The obsolete parameter is shown in the following command line:  
 ax32serv.exe -startupcmd=CompileAll.

### ![Dn528954.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Dn528954.collapse_all(en-us,AX.60).gif")A.2  Contrast with Compiling on the Client

In the past to accomplish a full X++ compile you had to click a menu in the MorphX client, such as **Build** \> **Compile**. This is a three tier operation which is burdened with transferring data between the client and the AOS. In contrast, the AxBuild.exe approach is only a two tier operation. One reason the AxBuild.exe approach is faster is that it eliminates the data transfers over the network, or over local RPCs, between the AOS and the client.

Compiling on the client does not provide any way to share the workload among several applications. In contrast, AxBuild.exe starts several AOS applications which all run concurrently, which all accomplish parts of the full compile.

As a matter of common practice, the AOS host computer hardware is often more powerful than client computers are. The AOS host typically has more active memory, and has more cores for parallel processing.

![Architecture of X++ compile on the client tier](images/Dn528954.AxBuildExe-Visio-Client-c(en-us,AX.60).png "Architecture of X++ compile on the client tier")

**Architecture of the X++ compile on the client tier**

The MorphX client you can quickly compile an individual X++ method. These partial compilations are extremely efficient for the developer who is adding and fixing a method through cycles of coding then testing. In contrast, AxBuild.exe cannot compile any mere subset of the X++ code on the system.

The MorphX client remains the only option for compiling AX p-code to .NET CIL.

## B.  Performance Gain

In this section we present performance data for AxBuild.exe. Every environment is different, and the performance speeds we see in our tests probably differ from what you see.

In our performance test of AxBuild.exe, we measured a **92%** reduction in the wall clock time that was necessary to complete a full X++ compilation. Stated another way, AxBuild.exe completed the compilation **13 times faster** than the MorphX client did on the same hardware. The software and hardware specifications for our test were as follows:

  - One server computer that had both AX client and AOS installed, and had SQL installed:
    
      - Microsoft Dynamics AX 2012 R2 with cumulative update 7.
    
      - Microsoft SQL Server 2012 SP1 Enterprise (no limit on memory).
    
      - Microsoft Windows Server 2012.

  - The computer hardware had the following specifications:
    
      - 4 processor cores, at 3.7 gigahertz.
    
      - Hyper-threading enabled, which logically doubles the number of cores.
    
      - 32 gigabytes of active memory.
    
      - 6.0 gigabits SATA controller.
    
      - Virtual page caching disabled.

Given the hardware available, AxBuild.exe decided to start **9** temporary AOS workers.

The wall clock time for AxBuild.exe was compared to the time for a legacy client-side full X++ compile. The results were as follows:

  - AxBuild.exe:    10.7 minutes.

  - MorphX client:    146.0 minutes.

  - 146.0  /  10.7  =  13.6

From another measurement we took, a single AOS worker runs 28% faster for not having to transfer information to the MorphX client and back during the full compile.

## C.  How to Run AxBuild.exe

**Preparations**

The following preparations are necessary before you can run AxBuild.exe:

  - You must have completed the installation of cumulative update 7 for Microsoft Dynamics AX 2012 R2. This must include a re-initialization of the model store database that you run manually, by using either axutil.exe schema or the newer PowerShell equivalent. For more information, see [Apply updates to database, AOS, and clients](https://msdn.microsoft.com/en-us/library/hh538446\(v=ax.60\)) or [How to: Create, Drop, or Reinitialize a Model Store](how-to-create-drop-or-reinitialize-a-model-store.md).

  - You must ensure that the account which will run AxBuild.exe has no less authority than has the account that runs the permanent AOS.

  - You must ensure that the option for the [hot-swapping of .NET assemblies](hot-swapping-of-net-assemblies-in-the-aos.md) is turned off in the AOS configuration you choose to use. See the /aos parameter on AxBuild.exe.

  - You must establish and populate the directory that will be referred to by the /altbin parameter.

**Example Command Line**

Here is an example command line for AxBuild.exe that might match the command line you need in your particular environment. The line is artificially wrapped here for better display.

axbuild.exe  xppcompileall  /s=01   
     /altbin="C:\\Program Files (x86)\\Microsoft Dynamics AX\\6.0\\Client\\Bin"

## D.  Outputs from AxBuild.exe

 

### ![Dn528954.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Dn528954.collapse_all(en-us,AX.60).gif")D.1  Outputs to the Console

AxBuild.exe reports its progress to the console through the stdout handle. The stderr handle is not used.

Each AOT element is reported at the moment it is compiled. Some elements can be reported repeatedly at different times before they successfully compile. These repetitions are sometimes necessary because full metadata is not always available to satisfy all dependencies until later phases of the compilation.

### ![Dn528954.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Dn528954.collapse_all(en-us,AX.60).gif")D.2  Output Log Files

AxBuild.exe generates two log files. You can control where the log files are written by using the /log parameter. By default the files are written to the Server\\...\\Log\\ subdirectory under the installation directory of the AOS. Here is a common example of what the specific default path might be:  
   
 C:\\Program Files\\Microsoft Dynamics AX\\60\\Server\\MicrosoftDynamicsAX\\Log\\

The following table describes the two log files.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>File name</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>AxCompileAll.html</p></td>
<td><p>Contains the final list of compile errors in XML format.</p>
<p>You can import the file into the MorphX development environment by following these steps:</p>
<ol>
<li><p>In the AOT, right-click any method node under a class, and click <strong>Compile</strong>.<br />
This displays the <strong>Compiler output</strong> pane.</p></li>
<li><p>Click the <strong>&gt;&gt;</strong> icon on the <strong>Compiler output</strong> pane.<br />
The icon is located near the upper-right on the pane. The icon might be hidden if your pane size is too narrow.</p></li>
<li><p>Click <strong>Import</strong>.<br />
This displays the <strong>Import compile log</strong> dialog.</p></li>
<li><p>Navigate to the Server\...\Log\ directory to find the log file, and then click <strong>Open</strong>.</p></li>
</ol>
<p>After the log file is imported, you can examine and fix each compile error just as if the errors had been logged by the compiler on the client tier.</p></td>
</tr>
<tr class="even">
<td><p>AOTCompile.log</p></td>
<td><p>Contains information that partly duplicates the information that is written to the console.</p></td>
</tr>
</tbody>
</table>


### ![Dn528954.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Dn528954.collapse_all(en-us,AX.60).gif")D.3  Temporary Files

AxBuild.exe writes temporary files to the %TEMP% directory. These files include many details about the process. By default these files are deleted by AxBuild.exe shortly before it ends. However, you can keep the files by using the /nocleanup parameter.

## E.  Parameters for AxBuild.exe

The parameter names are not case-sensitive.

In all cases where the parameter name takes an accompanying value, an = sign is used to join them together, as for example /aos=01.

AxBuild.exe always returns 0.

### ![Dn528954.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Dn528954.collapse_all(en-us,AX.60).gif")E.1  Description of Each Parameter

The following table describes the parameters that you can or must pass into AxBuild.exe.

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Name</p></th>
<th><p>Alias</p></th>
<th><p>Required?</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>xppcompileall</p></td>
<td><p><em>No short alias.</em></p></td>
<td><p>Required.</p></td>
<td><p>Tells the program do a full compile on all X++ code, which creates all new p-code to be stored in the model store database.</p>
<p>This parameter name has no accompanying value, and no leading '/'.</p>
<p>This parameter is a command to tell the program the type of action to perform. So far it is the only command parameter.</p></td>
</tr>
<tr class="even">
<td><p>/altbin</p></td>
<td><p>/a</p></td>
<td><p>Optional.</p></td>
<td><p>Path to the folder on the local AOS host computer that has the DLL files which are installed with an ax32.exe client. AxBuild.exe verifies that ax32.exe is in the directory before it proceeds with the compile action.</p>
<p>A good path to use might be the path that the client install would typically create. You must confirm the exact correct path for your particular environment:<br />
 <br />
 C:\Program Files(x86)\Microsoft Dynamics AX\6.0\Client\Bin\</p>
<p>One way to create and populate such a directory path is to install the client onto the AOS host computer, even though maybe no person would use the client on that host.<br />
Thereafter, any developers who add a third party DLL to their own client directory must ensure that the DLL is manually copied to this corresponding directory on each AOS where this program might be run.</p>
<p>If the ax32.exe client is not installed onto the AOS host computer, this manually created directory must be initially populated manually with all the DLL files from a client installation on another computer.</p>
<p>If you omit this parameter, AxBuild.exe examines the Microsoft Dynamics AX client configuration information in the Windows Registry in an attempt to find the correct path.</p></td>
</tr>
<tr class="odd">
<td><p>/aos</p></td>
<td><p>/s</p></td>
<td><p>Often optional.</p></td>
<td><p>Instance number of an AOS that is installed on the same computer where this program runs.</p>
<p>If you omit this parameter, AxBuild.exe examines the Microsoft Dynamics AX server configuration information in the Windows Registry. If the Registry contains information about exactly one AOS instance, that information is used as the default value for this parameter.</p>
<p>The temporary instances of the AOS all use the same configuration specifications that this AOS instance number uses.</p>
<p>To see a list of all available instance numbers, run the Microsoft Dynamics AX Server Configuration Utility, AxSrvCfg.exe. At the top of its window is a drop-down list that is labeled <strong>Application Object Server Instance</strong>. Perhaps the most commonly used value is 01, as in /aos=01.</p>
<p>The parameters /dbserver and /modelstore are available in case you need to override those parts of the AOS instance configuration information.</p></td>
</tr>
<tr class="even">
<td><p>/compiler</p></td>
<td><p>/c</p></td>
<td><p>Sometimes required.</p>
<p>This /c parameter might be absent from the report that is generated by the /help parameter, but /c is fully supported.</p></td>
<td><p>You need this parameter only when the current directory is not the directory where ax32serv.exe resides. In this case the value of the parameter must be the name ax32serv.exe preceded by its directory path. A realistic example might be the following value:<br />
 <br />
 /compiler=&quot;C:\Program Files\Microsoft Dynamics AX\6.0\Server\bin\ax32serv.exe&quot;</p>
<p>Full compiles that are started by automation might be relatively likely to need this parameter.</p></td>
</tr>
<tr class="odd">
<td><p>/dbserver</p></td>
<td><p>/d</p></td>
<td><p>Optional.</p></td>
<td><p>The name of the Microsoft SQL Server instance that manages the AX model store database.</p>
<p>Typically this parameter is not used. Instead the program is allowed to obtain this information from the configuration it obtains from the AOS instance that is referenced by the /aos parameter.</p></td>
</tr>
<tr class="even">
<td><p>/help</p></td>
<td><p>/h or /?</p></td>
<td><p>Optional.</p></td>
<td><p>Writes brief descriptions about all parameters to the stdout handle of the console.</p>
<p>This parameter name has no accompanying value.</p>
<p>This parameter is implied if no parameters are supplied.</p>
<p>If there are any discrepancies between this topic and the /help output, this topic is correct.</p></td>
</tr>
<tr class="odd">
<td><p>/log</p></td>
<td><p>/l</p></td>
<td><p>Optional.</p></td>
<td><p>Specifies the directory path to which the two log files are written.</p>
<p>The default path is the Server\...\Log\ directory under the installation location of the AOS. More exactly, the default value is stored in the Registry at the following location:<br />
 HKEY_LOCAL_MACHINE\SYSTEM\ControlSet001\services\ <br />
 Dynamics Server\6.0\01\Original (installed configuration) , in logdir.</p>
<p>The /log parameter does not specify the name of a file. It specifies a path.</p>
<p>The /verbose parameter affects how much information is written to this log file.</p></td>
</tr>
<tr class="even">
<td><p>/modelstore</p></td>
<td><p>/m</p></td>
<td><p>Optional.</p></td>
<td><p>Name of the model store database.</p>
<p>Typically this parameter is not used. Instead the program is allowed to use the value it obtains from the configuration as directed by the /aos parameter.</p></td>
</tr>
<tr class="odd">
<td><p>/nocleanup</p></td>
<td><p>/n</p></td>
<td><p>Optional.</p></td>
<td><p>Tells the program to keep the temporary files it writes under the %TEMP% directory.</p>
<p>This parameter name has no accompanying value.</p>
<p>Without this parameter, the default behavior is for the program to delete the temporary files immediately before it ends its run.</p></td>
</tr>
<tr class="even">
<td><p>/verbose</p></td>
<td><p>/v</p></td>
<td><p>Optional.</p></td>
<td><p>Tells the program to write all the tracing and diagnostic information that it has to stdout, and to the AOTComp.log file. Without this parameter, less information is written.</p>
<p>This parameter name has no accompanying value.</p>
<p>Usually the program writes only the subset of information that a person typically might want to watch scroll by on the screen in the cmd.exe window.</p></td>
</tr>
<tr class="odd">
<td><p>/workers</p></td>
<td><p>/w</p></td>
<td><p>Optional.</p></td>
<td><p>Number of parallel or concurrent AOS workers for the compilation and build processes.</p>
<p>The program calculates a sensible integer value based on the number of available processor cores. But you might want to fine tune this value. A rough approximation might be 1.4 workers per core.</p></td>
</tr>
</tbody>
</table>


## F.  Constraints of Compiling on the AOS

### ![Dn528954.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Dn528954.collapse_all(en-us,AX.60).gif")F.1  .NET Objects Cannot be Instantiated

When the X++ compiler starts, it performs special compiles on a few special classes. These classes include Application, Infolog, and ClassFactory. When these special classes are compiled during a compile on the AOS tier, they fail if any custom code has been added to them that makes interop calls to the .NET Framework.

We generally recommend that you not customize the methods in these special classes.

### ![Dn528954.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Dn528954.collapse_all(en-us,AX.60).gif")F.2  Calls to COM Objects Cannot be Chained

In X++ you can sometimes chain together a series of method calls by using the following syntax:  
   
 myThing.method8().method9();   
   
This chaining syntax is valid only if the return type from method8 has a method named method9.

When you compile by using AxBuild.exe, the syntax of method chaining cannot be used with COM objects. The compiler cannot ascertain whether the COM object that is returned by method8 has a method named method9.

The simple solution is to use another common syntax that explicitly gives the compiler the type information it needs to validate the call to method9. The situation is explained in the following table.

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Outcome</p></th>
<th><p>Explanation</p></th>
<th><p>Code example</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Example that <strong>Fails</strong></p></td>
<td><p>This X++ code example syntactically chains the method2 call to the end of the method1 call. The server compiler reports an error for the method2 call.</p>
<p><em>Underlying Details:</em> Often COM objects that are called by X++ code are installed only on the client tier, and are not installed on the server tier. In the preceding code example, the underlying problem is that the server compiler cannot know the return type from method1. Its return type could be another COM object or just an integer. If the return type from method1 were an integer, the chained call to method2 would certainly be invalid. The compiler issues an error because it cannot prove that method1 returns another COM object.</p></td>
<td><pre><code>void methodXpp()
{
    COM comInstanceA = new COM(&quot;MyCOMType_A&quot;);
    comInstanceA.method1().method2();
}</code></pre></td>
</tr>
<tr class="even">
<td><p>Example that <strong>Succeeds</strong></p></td>
<td><p>This X++ code example eliminates the chain, and succeeds.</p>
<p><em>Underlying Details:</em> In the preceding code example, the server compiler is told by an explicit type declaration that variable comInstanceB is a COM object. This gives the compiler justification to insert a call to the dispatch method for method2.</p></td>
<td><pre><code>void methodXpp()
{
    COM comInstanceA = new COM(&quot;MyCOMType_A&quot;);
    COM comInstanceB;
    comInstanceB = comInstanceA.method1();
    comInstanceB.method2();
}</code></pre></td>
</tr>
</tbody>
</table>


## G.  Screenshots during Execution of AxBuild.exe

This section contains screenshots that were taken during a test run of AxBuild.exe. The run was to test for correct functional behavior on a minimal virtual machine that has only one processor. For the test we specified /workers=2 to tell AxBuild.exe to start two temporary AOS workers. Therefore, for this test we expected the compilation to take a long time.

The following screenshot shows the cmd.exe console in which AxBuild.exe was started, including its output which mentions each phase.

![Console for AxBuild.exe](images/Dn528954.AxBuildExe-Run-Exe-Console-ec1(en-us,AX.60).png "Console for AxBuild.exe")

The next screenshot shows the cmd.exe console that was started for a temporary AOS worker.

![Console for a temporary AOS, for AxBuild.exe](images/Dn528954.AxBuildExe-Run-AOSTempWorker-Console-atw2(en-us,AX.60).png "Console for a temporary AOS, for AxBuild.exe")

The next screenshot shows the AxBuild.exe and temporary AOS processes in Task Manager.

![Task Manager displaying two temporary AOS's](images/Dn528954.AxBuildExe-Run-TaskMgr-tm3(en-us,AX.60).png "Task Manager displaying two temporary AOS's")

The next screenshot shows the browser that displays the contents of the AxCompileAll.html log file, which reported two warnings.

![Display of AxCompileAll.html log file](images/Dn528954.AxBuildExe-Log-AxCompileAll-la5(en-us,AX.60).png "Display of AxCompileAll.html log file")

The next screenshot shows a list of the temporary files that AxBuild.exe created in the %TEMP% directory. These \*.tmp files were kept only because the /nocleanup parameter was specified.

![Files in the %TEMP% dir kept by /nocleanup](images/Dn528954.AxBuildExe-Run-TEMP-Dir-td4(en-us,AX.60).png "Files in the %TEMP% dir kept by /nocleanup")

## H.  MorphX Client Menus for Compiling

AxBuild.exe adds one more mechanism that you can use to compile X++ code. In the MorphX client there are several menus that you can use to compile X++. The following table describes these menus.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Menu path</p></th>
<th><p>Description</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Save</strong> button on the X++ code editor</p></td>
<td><p>Incremental compile of the X++ source code that is in the editor pane. The compile is to AX p-code.</p>
<p>However, no compile occurs if the source code has not changed after it was most recently compiled.</p></td>
</tr>
<tr class="even">
<td><p><strong>AOT</strong> &gt; <strong>Classes</strong> &gt; <strong>YourClass</strong> &gt; <strong>YourMethod</strong>. Right-click <strong>YourMethod</strong>, and then click <strong>Compile</strong>.</p></td>
<td><p>Incremental compile of the targeted X++ source code to AX p-code.</p>
<p>The compile does occur even if the code has not changed after it was most recently compiled.</p></td>
</tr>
<tr class="odd">
<td><p>Menu <strong>Build</strong> &gt; <strong>Compile</strong>, or press F7.</p></td>
<td><p>Full compile of X++ to AX p-code.</p>
<p>The full compile occurs regardless of whether the X++ source code has changed after it was most recently compiled.</p>
<p>This is the client option that is most similar to AxBuild.exe.</p></td>
</tr>
<tr class="even">
<td><p>Right-click <strong>AOT</strong>, and then click <strong>Compile</strong>.</p></td>
<td><p>Same as menu <strong>Build</strong> &gt; <strong>Compile</strong>.</p></td>
</tr>
<tr class="odd">
<td><p>Right-click <strong>AOT</strong>, and then click <strong>Add-Ins</strong>, and finally click either of the following:</p>
<ul>
<li><p><strong>Full CIL generation from X++</strong></p></li>
<li><p><strong>Incremental CIL generation from X++</strong></p></li>
</ul></td>
<td><p>The CIL generation takes as input the AX p-code, not any X++ source code.</p>
<p>These CIL generations occur even if the p-code has not changed after the p-code was most recently compiled from X++.</p></td>
</tr>
</tbody>
</table>

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

