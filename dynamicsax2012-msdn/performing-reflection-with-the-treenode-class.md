---
title: Performing Reflection with the TreeNode Class
TOCTitle: Performing Reflection with the TreeNode Class
ms:assetid: 5362868d-41fa-441d-9b02-0e8861f42370
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc967395(v=AX.60)
ms:contentKeyID: 35244326
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Performing Reflection with the TreeNode Class 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

This topic gives information about performing reflection on Application Object Tree (AOT) items such as tables and classes. In your X++ code in Microsoft Dynamics AX, you can use the TreeNode class to perform reflection. The TreeNode class can also add nodes to the AOT, such as adding an element to an enumeration.

## X++ Example

### ![Cc967395.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc967395.collapse_all(en-us,AX.60).gif")Description

The following code example locates the AOT node for a specific base enumeration. All child nodes are checked to determine the next available integer value for an EnumValue. Then another child node is added under the enumeration. Finally, the code pauses so that you can inspect the AOT for the new node. When you see the new node, you can click **Yes** on a dialog box. This resumes the job code, and the job deletes the new node before it is completed.

The example relies on the following items which are installed with the system.

  - The \#AOT macro. The macro is located in the AOT under the **Macros** node.

  - The base enumeration BankAccountType that is in the AOT under \\Data  Dictionary\\Base Enums\\.

The example uses the following methods on the TreeNode class:

  - AOTadd

  - AOTcompile

  - AOTdelete

  - AOTfindChild

  - AOTfirstChild

  - AOTgetProperties

  - AOTgetProperty

  - AOTnextSibling

  - AOTsave

  - AOTsetProperty

  - AOTToString

  - findNode

### ![Cc967395.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc967395.collapse_all(en-us,AX.60).gif")Code

    static void Job_TreeNode_AOTsave_Reflection(Args _args)
    {
        // #AOT is defined in the AOT under Macros.
        #AOT
        TreeNode tnode2Enum,
            tnode3Element
            ;
        int iMaxEnumValue = -1;
        str sEnumName = "BankAccountType",
            sEnumElementNameNew = "PiggyBankAccount",
            sTemp;
        ;
        // Uses the full path to obtain the node for the new enum element
        // that this job creates near its completion.
        tnode2Enum = TreeNode::findNode(
            #BaseEnumsPath
            + "\\" + sEnumName
            + "\\" + sEnumElementNameNew
            + "\\" );
        // Deletes the enum element node if it pre-exists.
        if (tnode2Enum)
        {
            info("Deleting the enum element: ["
                + sEnumElementNameNew
                + "], because it pre-exists.");
            tnode2Enum.AOTdelete();
        }
        else
        {
            info("Not deleting the enum element: ["
               + sEnumElementNameNew
               + "], because it does not pre-exist.");
        }
    
        // Finds the node for the target enum, by searching for the name.
        tnode2Enum = TreeNode::findNode(#BaseEnumsPath);
        tnode2Enum = tnode2Enum.AOTfindChild(sEnumName);
    
        if (tnode2Enum == null)
        {
            Error("Cannot find treeNode: " + sEnumName);
            return;
        }
        info( "AOToString:  " + tnode2Enum.AOTToString() );
    
        // Gets the first child node of the enum.
        tnode3Element = tnode2Enum.AOTfirstChild();
        info("");
        info("Properties of the first child element:");
        info(tnode3Element.AOTgetProperties());
        info("");
    
        // Inside the while loop the AOTnextSibling method is called.
        // This enables the loop to process each child node of the enum.
        // An alternative is to use a TreeNodeIterator that is obtained
        // from the AOTiterator method.
        while (tnode3Element)
        {
            if ( iMaxEnumValue < any2int(
                    tnode3Element.AOTgetProperty("EnumValue"))
                )
            {
                iMaxEnumValue = tnode3Element.AOTgetProperty("EnumValue");
            }
            info( "iMaxEnumValue == " + int2str(iMaxEnumValue) );
    
            tnode3Element = tnode3Element.AOTnextSibling();
        }
        ++iMaxEnumValue;
    
        // The call to AOTadd on the parent returns a new child node of the enum.
        
        tnode3Element = tnode2Enum.AOTadd("PiggyBankAccount");
        // Sets the numeric property on the new child.
        tnode3Element.AOTsetProperty("EnumValue", iMaxEnumValue);
    
        // Saves the new child into the system by saving the parent enum.
        // Then the new child node appears in the AOT.
        tnode2Enum.AOTcompile();
        tnode2Enum.AOTsave();
    
        // Asks the user to verify that the AOT displays the new node.
        sTemp = "Is the new element displayed in the AOT?";
        warning(sTemp);
        print(sTemp);
        print("Then click 'Yes' to resume and finish the job,"
           + " to delete the new element.");
        print("Or, click 'No' to end the job,"
           + " to leave the new node in the AOT.");
        pause;
    
        // Cleans up by deleting the newly added element.
        tnode2Enum = TreeNode::findNode(
            #BaseEnumsPath
            + "\\" + sEnumName
            + "\\" + sEnumElementNameNew
            + "\\" );
        if (tnode2Enum)
        {
            info("Deleting the enum element: ["
                + sEnumElementNameNew
                + "], because the add did work.");
            tnode2Enum.AOTdelete();
        }
        else
        {
            error("Not deleting the enum element: ["
                + sEnumElementNameNew
                + "], because the add did not work.");
        }
    }

#### ![Cc967395.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc967395.collapse_all(en-us,AX.60).gif")Output

The output to the Infolog is as follows:

<pre IsFakePre="true" xmlns="http://www.w3.org/1999/xhtml">Message (11:16:07 am)
Deleting the enum element: [PiggyBankAccount], because it pre-exists.
AOToString:  Path: \Data Dictionary\Base Enums\BankAccountType Layer: usr

Properties of the first child element:
PROPERTIES
  Name                #CheckingAccount
  Label               #@SYS95020
  ConfigurationKey    #
  EnumValue           #0
ENDPROPERTIES

iMaxEnumValue == 0
iMaxEnumValue == 1
Is the new element displayed in the AOT?
Deleting the enum element: [PiggyBankAccount], because the add did work.</pre>


## See also

[Microsoft Dynamics AX Class Overview](microsoft-dynamics-ax-class-overview.md)

[TreeNode Class](https://msdn.microsoft.com/en-us/library/gg958198\(v=ax.60\))

[MemberFunction Class](https://msdn.microsoft.com/en-us/library/gg941602\(v=ax.60\))

[MethodInfo Class](https://msdn.microsoft.com/en-us/library/gg942043\(v=ax.60\))

[ClassBuild Class](https://msdn.microsoft.com/en-us/library/gg754182\(v=ax.60\))

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

