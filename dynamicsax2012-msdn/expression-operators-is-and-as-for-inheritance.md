---
title: 'Expression Operators: Is and As for Inheritance'
TOCTitle: 'Expression Operators: Is and As for Inheritance'
ms:assetid: 03dd2742-ae64-49bc-918b-8683c6f3f5af
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Gg843452(v=AX.60)
ms:contentKeyID: 35240246
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Expression Operators: Is and As for Inheritance 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

In Microsoft Dynamics AX, the X++ language provides the as and is expression operators to control downcast assignments. Downcast assignments involve class or table inheritance.


> [!NOTE]
> <P>For information about the terminology of inheritance, see <A href="inheritance-terminology.md">Inheritance Terminology</A>.</P>



Assignment statements that implicitly downcast can cause errors that are hard for the programmer to predict or diagnose. You can use the as keyword to make your downcasts explicit. You can use the is keyword to test whether a downcast is valid at run time.

## As Keyword

You can use the as keyword for assignments that downcast from a base class variable to a derived class variable. The as keyword tells other programmers and the compiler that you believe the downcast will be valid during run time.

### ![Gg843452.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg843452.collapse_all(en-us,AX.60).gif")As Keyword at Compile Time

Starting in Microsoft Dynamics AX 2012 or in a release to follow, the X++ compiler reports an error for downcast assignment statements that lack the as keyword.

### ![Gg843452.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg843452.collapse_all(en-us,AX.60).gif")As Keyword at Run Time

At run time, the as keyword causes the downcast assignment statement to assign null if the downcast is invalid.

### ![Gg843452.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg843452.collapse_all(en-us,AX.60).gif")Code Example for the As Keyword

In the following code example, the DerivedClass class extends the BaseClass class. The code example contains two valid assignments between its basec and derivedc variables. The upcast assignment to basec does not need the as keyword, but the downcast assignment to derivedc does need the as keyword. The following code would compile and run without errors.

    static void AsTestJob33(Args _args)
    {
        // DerivedClass extends BaseClass.
        BaseClass basec; 
        DerivedClass derivedc;
    
        // BottomClass extends DerivedClass.
        BottomClass bottomc;
    
        derivedc = new DerivedClass();
    
        // AS is not needed for an upcast assignment like this.
        basec = derivedc;
    
        // AS is needed for a downcast assignment like this.
        derivedc = basec as DerivedClass;
    
        bottomc = new BottomClass();
        // AS causes this invalid downcast to assign null.
        bottomc = basec as DerivedClass;
    }

## Is Keyword

The is keyword ascertains whether an object is a subtype of a specified class. The is expression returns true if the object is a subtype of the class, or if the object is the same type as the class.

### ![Gg843452.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg843452.collapse_all(en-us,AX.60).gif")Is Keyword at Compile Time

The X++ compiler reports an error if an is keyword expression compares two types where neither is a subtype of the other, and they are not of the same type. The compiler reports a similar error for any plain assignment statement between two types where neither is a subtype of the other, and they are not of the same type.

### ![Gg843452.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg843452.collapse_all(en-us,AX.60).gif")Is Keyword at Run Time

At run time the type of variable that references the underlying object is irrelevant to the is keyword. The is keyword causes the system to check the object that the variable references, not the declared type of the variable that references the object.

### ![Gg843452.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg843452.collapse_all(en-us,AX.60).gif")Code Examples for the Is Keyword

The following code examples illustrate the conditions that control whether an is expression returns true or false. The code examples rely on the fact that the Form class and the Query class both extend the TreeNode class.

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Code example</p></th>
<th><p>Explanation</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><pre><code>Form myForm = new Form();
info(strFmt(&quot;%1&quot;, (myForm is Query)));</code></pre></td>
<td><p>The X++ compiler issues an error.</p>
<p>The compiler ascertains that the Form class and the Query class are not part of the same inheritance hierarchy. Both the Form class and the Query extends the TreeNode class, but neither Form nor Query is a subtype of the other.</p></td>
</tr>
<tr class="even">
<td><pre><code>TreeNode myTreeNode = new TreeNode();
info(strFmt(&quot;%1&quot;, (myTreeNode is Form)));</code></pre></td>
<td><p>The Infolog displays <strong>0</strong> during run time, where <strong>0</strong> means false.</p>
<p>No supertype object can be considered to also be of its subtype class.</p></td>
</tr>
<tr class="odd">
<td><pre><code>Form myForm;
info(strFmt(&quot;%1&quot;, (myForm is Form)));</code></pre></td>
<td><p>The Infolog displays <strong>0</strong> during run time, where <strong>0</strong> means false.</p>
<p>A null reference causes the is expression to return false.</p></td>
</tr>
<tr class="even">
<td><pre><code>Form myForm = new Form();
info(strFmt(&quot;%1&quot;, (myForm is Form)));</code></pre></td>
<td><p>The Infolog displays <strong>1</strong> during run time, where <strong>1</strong> means true.</p>
<p>An object is an instance of its own class type.</p></td>
</tr>
<tr class="odd">
<td><pre><code>Form myForm = new Form();
info(strFmt(&quot;%1&quot;, (myForm is TreeNode)));</code></pre></td>
<td><p>The Infolog displays <strong>1</strong> during run time, where <strong>1</strong> means true.</p>
<p>Every subtype is also of its supertype.</p></td>
</tr>
<tr class="even">
<td><pre><code>Form myForm = new Form();
TreeNode myTreeNode;
myTreeNode = myForm; // Upcast.
info(strFmt(&quot;%1&quot;, (myTreeNode is Form)));</code></pre></td>
<td><p>The Infolog displays <strong>1</strong> during run time, where <strong>1</strong> means true.</p>
<p>The type of the underlying object is what matters in the is expression, not the type of the variable that references the object.</p></td>
</tr>
</tbody>
</table>


## Using Is and As Keywords Together

This is keyword is often used to safely test whether the as keyword will work.

### ![Gg843452.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg843452.collapse_all(en-us,AX.60).gif")Code Example

The following code example contains a common use of the is keyword. The as keyword is used after the is keyword verifies that the as keyword will the object. The is and as keywords are uppercase to make them more visible in this example.

    static void IsKeywordJob46(Args _args) // X++
    {
        DerivedClass derivedc;
        BaseClass basec;
    
        basec = new DerivedClass();  // An upcast.
        if (basec IS DerivedClass)
        {
            info("Test 1: (basec IS DerivedClass) is true. Good.");
            derivedc = basec AS DerivedClass;
        }
    
        basec = new BaseClass();
        if (!(basec IS DerivedClass))
        {
            info("Test 2: (!(basec IS DerivedClass) is true. Good."));
        }
    }

<table>
<colgroup>
<col style="width: 100%" />
</colgroup>
<thead>
<tr class="header">
<th><p>Output to the Infolog</p></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Test 1: (basec IS DerivedClass) is true. Good.</p>
<p>Test 2: (!(basec IS DerivedClass)) is true. Good.</p></td>
</tr>
</tbody>
</table>


## Object Class is a Special Case

The Object class can appear as a special case in inheritance functionality. The X++ compiler has special logic to bypass type checking for assignments to and from variables that are declared of type Object.


> [!NOTE]
> <P>You could misinterpret some X++ statements if you are unaware of this special case.</P>



Some classes inherit from the Object class, some inherit from another class, and some do not inherit from any class. The Dialog class does not inherit from any class, yet the assignment and call statements in the following code example all work.

    static void ObjectIsAsJob4(Args _args)
    {
        Bank bank4;
        Object obj2;
        Dialog dlog3 = new Dialog("Test 4.");
    
        obj2 = dlog3;  // The assignment does work.
        obj2.run(false);  // The call causes the dialog to display.
        info("Test 4a is finished.");
        ...
    }

The assignment would fail at compile time if it had been bank4 = dlog3;, because the Bank and Dialog classes have no inheritance relationship to each other.

The X++ compiler performs only one small check on assignments to a variable that is declared of the Object class. The compiler checks to make sure that the item being assigned to the Object variable is an instance of a class.

The compiler does not allow an instance of a table buffer to be assigned to the Object variable. Also, the compiler does not allow primitive data types, such as int or str, to be assigned to the Object variable.

### ![Gg843452.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Gg843452.collapse_all(en-us,AX.60).gif")Root Items in Table Inheritance

All tables inherit directly from the Common system table, unless they explicitly inherit from a different table. The Common table cannot be instantiated. The Common table does not exist in the underlying physical database. The Common table inherits from the xRecord class, but only in a special way that is not appropriate for the is keyword or the as keyword.

## As Keyword and Tables

When the as keyword is used to perform an invalid downcast among tables, the target variable references an unusable non-null entity. Any attempt to dereference the target variable will cause an error that stops the X++ program.

## Is and As Keywords and Extended Data Types

Each extended data type has an **Extends** property. The style of inheritance that is controlled by this property differs from the style of inheritance that the is and as keywords are designed for.

## More Information about Inheritance

For information about the extends keyword for inheritance between classes, see [X++ Keywords](x-keywords.md) and [X++, C\# Comparison: Object Oriented Programming](x-csharp-comparison-object-oriented-programming.md).

For information about inheritance between tables, see [Table Inheritance Overview](table-inheritance-overview.md).

## See also

[Operators](operators.md)

[Inheritance Terminology](inheritance-terminology.md)

[SysDictClass::is Method](https://msdn.microsoft.com/en-us/library/gg926608\(v=ax.60\))

[SysDictClass::as Method](https://msdn.microsoft.com/en-us/library/gg926599\(v=ax.60\))

[SysDictClass::isEqualOrSuperclass Method](https://msdn.microsoft.com/en-us/library/gg926609\(v=ax.60\))

[SysDictClass::isSuperclass Method](https://msdn.microsoft.com/en-us/library/gg958109\(v=ax.60\))

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

