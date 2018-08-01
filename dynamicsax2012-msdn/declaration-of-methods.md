---
title: Declaration of Methods
TOCTitle: Declaration of Methods
ms:assetid: 0db59beb-35ca-4b7a-b41e-18d4a96dfedf
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa584699(v=AX.60)
ms:contentKeyID: 35240446
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Declaration of Methods [AX 2012]


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Methods are created using the Application Object Tree (AOT). When methods are created, MorphX creates a default declaration that must be altered.

Method declarations consist of a header and a body. The method header declares the name and return type (possibly void) of the method, the method modifiers, and parameters. The method body consists of variable declarations, method declarations, and statements.

## Return Type

If a method does not return anything, you must specify this with the void keyword.

void methodName()

{

    ...

}

If a method returns something, you must specify the return type and include a return statement.

int methodName()

{

    return myInt;

}

## Syntax

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<tbody>
<tr class="odd">
<td><p>Method declaration</p></td>
<td><p>=</p></td>
<td><p>Heading  Body</p></td>
</tr>
<tr class="even">
<td><p>Heading</p></td>
<td><p>=</p></td>
<td><p>[ Modifiers ]  ReturnType  MethodName  (  ParameterList  )</p></td>
</tr>
<tr class="odd">
<td><p><a href="method-modifiers.md">Modifiers</a></p></td>
<td><p>=</p></td>
<td><p>[client] [server] [edit | display | public | protected | private] [static | abstract | final ]</p></td>
</tr>
<tr class="even">
<td><p>ReturnType</p></td>
<td><p>=</p></td>
<td><p>Datatype  | void | anytype</p></td>
</tr>
<tr class="odd">
<td><p>MethodName</p></td>
<td><p>=</p></td>
<td><p>Identifier</p></td>
</tr>
<tr class="even">
<td><p>ParameterList</p></td>
<td><p>=</p></td>
<td><p>[ Parameter  { ,  Parameter  }]</p></td>
</tr>
<tr class="odd">
<td><p>Parameter</p></td>
<td><p>=</p></td>
<td><p>Datatype  Variableidentifier  [ =  Expression  ]</p></td>
</tr>
<tr class="even">
<td><p>Body</p></td>
<td><p>=</p></td>
<td><p>{ [  VariableDeclarations  ] [  EmbeddedFunctionDeclarations  ] [  Statements  ] }</p></td>
</tr>
<tr class="odd">
<td><p>EmbeddedFunctionDeclaration</p></td>
<td><p>=</p></td>
<td><p>Heading  {[  VariableDeclarations  ] [  Statements  ]}</p></td>
</tr>
</tbody>
</table>



> [!NOTE]
> <P>If you use the anytype return type, the method can return any data type.</P>



## Examples

### ![Aa584699.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa584699.collapse_all(en-us,AX.60).gif")Method Without a Return Type
```X++  
    void update ()
    {   
        // Variable declared and initialized
        CustTable this_Orig = this.orig();
     
        // First statement in body (begin transaction)
        ttsBegin;
        this.setNameAlias();
        // Calls super's implementation of update
        super();
        this.setAccountOnVend(this_Orig);
        if (this_Orig.custGroup != this.custGroup)
            ForecastSales::setCustGroupId(
                this.accountNum,
                this_Orig.custGroup,
                this.custGroup);
     
        // Commits transaction
        ttsCommit;
    }
```
### ![Aa584699.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa584699.collapse_all(en-us,AX.60).gif")Method with Parameters
```X++  
    boolean checkAccountBlocked(AmountCur amountCur)
    {
        if (this.blocked == CustVendorBlocked::All 
            ||(this.blocked == CustVendorBlocked::Invoice 
            && amountCur > 0 ))
        return checkFailed(strFmt("@SYS7987",this.accountNum));
     
        return true;
    }
```
checkAccountBlocked returns a Boolean value and acts on the parameter amountCur.

### ![Aa584699.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa584699.collapse_all(en-us,AX.60).gif")Methods with Modifiers

Only the method headers are shown in the following examples.
```X++  
    // A method that cannot be overridden
    final int dontAlterMe() 
    
    // A static method 
    static void noChange()
    
    // A display method that returns an integer
    display int value() 
```
## See also

[Method Modifiers](method-modifiers.md)

[Using Optional Parameters](using-optional-parameters.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

