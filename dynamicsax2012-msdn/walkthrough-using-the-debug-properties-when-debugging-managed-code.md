---
title: 'Walkthrough: Using the Debug Properties When Debugging Managed Code'
TOCTitle: 'Walkthrough: Using the Debug Properties When Debugging Managed Code'
ms:assetid: 27503d6d-593a-48dc-98aa-90c567efa269
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh129886(v=AX.60)
ms:contentKeyID: 35590997
ms.date: 11/21/2012
mtps_version: v=AX.60
---

# Walkthrough: Using the Debug Properties When Debugging Managed Code 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

After you add a project to the Microsoft Dynamics AX model store, you can then call code in that project from X++. When you call managed code from X++, you can use the project-level debugging properties to debug the code from Microsoft Visual Studio.

In this walkthrough, you will do the following:

  - Create a managed code class that adds two numbers and returns the result.

  - Create an X++ class that calls the managed code class.

  - Set the debug properties and step through debugging the two classes.

## Prerequisites

To complete this walkthrough you need:

  - Microsoft Dynamics AX with Visual Studio Tools installed

  - Visual Studio 2010

### Creating the Class Library in Visual Studio

1.  Open Visual Studio and create a new C\# class library by selecting **File** \> **New** \> **Project**. In the **Installed Templates** tree, navigate to **Visual C\#** \> **Windows** and then select **Class Library**.

2.  In the **Name** field, type **TestCalculator** and then click **OK**.

3.  In **Solution Explorer**, click **Class1**. In the **Properties Pane**, change the **Name** property to ManagedCalc.cs. When prompted to rename all references to the code element Class1, click **Yes**.

4.  Add the following code to the ManagedCalc class:
    
        public decimal addNumbers(decimal x, decimal y)
            {
                return x + y;
            }
    
    The ManagedCalc.cs file should resemble the following:
    
        namespace TestCalculator
        {
            public class ManagedCalc
            {
                public decimal addNumbers(decimal x, decimal y)
                {
                    return x + y;
                }
            }
        }

5.  Set a breakpoint on the following line of code in the addNumbers method: return x + y;.

6.  Click **Build** \> **Build Solution**.

7.  In **Solution Explorer**, right-click the **TestCalculator** project and then click **Add TestCalculator to AOT**. This adds the project to the Microsoft Dynamics AX model store.

8.  In **Solution Explorer**, click the **TestCalculator** project. Set the **Deploy to Client** property to **Yes**.

9.  Right-click the **TestCalculator** project and then click **Deploy**. This deploys the class assembly to the client. The next time the client connects to the server and accesses the assembly, it will load the assembly in memory.

### Creating an X++ Class that Calls the Managed Class

1.  Open Microsoft Dynamics AX and navigate to the **Developer Workspace**. In the Application Object Tree (AOT), right-click the **Classes** node and then click **New Class**.

2.  In the **Properties** tab, set the **Name** property to xppCalc.

3.  Right-click the xppCalc class, point to **New**, and then click **Method**. Replace the code in the method with the following:
    
        public System.Decimal addNumbers(System.Decimal x, System.Decimal y)
        {
            System.Decimal result;
            // Create a variable from the managed code type
            TestCalculator.ManagedCalc mc = new TestCalculator.ManagedCalc();
        
            // Call the managed code method and return the result.
            result = mc.addNumbers(x,y);
            return result;
        }

4.  Right-click the xppCalc class, point to **New**, and then click **Method**. Replace the code in the method with the following:
    
        public static void main(Args _args)
        {
            xppCalc calc = new xppCalc();
        
            // Initialize the variables to add.
            System.Decimal x = 284858.33;
            System.Decimal y = 749274.23;
        
            // Call the X++ method to add the numbers.
            info(System.Convert::ToString(calc.addNumbers(x,y)));
        }
    
    You must have a main method defined on your class if the class will be used as a debug target from Visual Studio. This is the method that is called when you debug after the Visual Studio process attaches to the client process (Ax32.exe).

5.  In the code editor, set a breakpoint on the last line of the xppCalc.main method that displays the calculator result.

6.  Right-click the xppCalc class and then click **Compile**. Close the Microsoft Dynamics AX client.

### Debugging the Code

1.  In Visual Studio, in **Solution Explorer**, click the **TestCalculator** project.

2.  In the **Properties** pane, set the **Debug Target** property to **Client**.

3.  Set the **Startup Element** property to **\\Classes\\xppCalc**. This instructs the debugger to run the main method of the xppCalc class. Alternatively, you can right-click the xppCalc class in Application Explorer and then click **Set as startup element**.

4.  Press F5 or click **Debug** \> **Start Debugging** to begin debugging. The Microsoft Dynamics AX Debugger opens and stops at the breakpoint you set in the xppCalc.main method. Before this occurs, the Visual Studio Debugger attaches to the Microsoft Dynamics AX client process, opens the client, and calls the xppCalc.main method.
    

    > [!TIP]
    > <P>If you receive an error that the startup element is invalid, you may want to refresh the Classes node in Application Explorer. To do this, right-click the <STRONG>Classes</STRONG> node and then click <STRONG>Refresh</STRONG>.</P>



5.  Press F11 to step through the code in the Microsoft Dynamics AX Debugger. When the X++ method xppCalc.addNumbers calls the managed code method ManagedCalc.addNumbers, execution stops at the breakpoint you set in Visual Studio. Then context switches to Visual Studio and you can continue to step through the code. When the call returns to the X++ method, context switches back to the Microsoft Dynamics AX Debugger.

## See also

[Debugging Managed Code in Microsoft Dynamics AX](debugging-managed-code-in-microsoft-dynamics-ax.md)

[Debugging in Microsoft Dynamics AX 2012](debugging-in-microsoft-dynamics-ax-2012.md)

