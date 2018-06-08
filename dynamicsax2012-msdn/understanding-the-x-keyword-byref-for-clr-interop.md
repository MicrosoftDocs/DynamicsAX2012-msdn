---
title: Understanding the X++ Keyword byref for CLR Interop
TOCTitle: Understanding the X++ Keyword byref for CLR Interop
ms:assetid: 37731e17-5486-4d1a-8108-f510c6a24e98
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc586700(v=AX.60)
ms:contentKeyID: 35242039
ms.date: 05/18/2015
mtps_version: v=AX.60
dev_langs:
- csharp
---

# Understanding the X++ Keyword byref for CLR Interop 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

You can use the X++ keyword byref to call .NET methods that take parameters by reference.

In all X++ methods, all parameters are passed by value. In .NET, parameters can be passed by value or by reference.

You must understand the parameter passing concepts of by value versus by reference before you can correctly use the byref keyword.

## By Value

When a parameter is passed by value, a copy of the value is given by the caller method to the called method. Assignments made by the called method to its parameter variable are not detectable by the caller.

### ![Cc586700.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc586700.collapse_all(en-us,AX.60).gif")int By Value

When a primitive data type (such as an X++ int) is passed by value, a copy of the value is given to the called method.

The following code example has a section for the caller method and a section for the called method. Both are X++ methods. The called method adds 456 to its parameter variable iTest. The caller method cannot detect that the addition occurred.

#### ![Cc586700.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc586700.collapse_all(en-us,AX.60).gif")Caller Method

    public void CallerMethodByValueInt() // X++
    {
        int iTest = 3;
        ;
        DemoClassXpp::CalledMethodByValueInt(iTest);
        if (iTest == 3)
        {
            info("Good, == 3.")
        }
    }

#### ![Cc586700.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc586700.collapse_all(en-us,AX.60).gif")Called Method

    static public void CalledMethodByValueInt // X++
            (int iTest) // by value
    {
        ;
        iTest = iTest + 456; // Caller can not detect.
    }

### ![Cc586700.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc586700.collapse_all(en-us,AX.60).gif")Object By Value

When an object is passed by value, a copy of the pointer (to the object) is given to the called method. Assignments made to this copy are not detectable by the caller method.

The following code example has a section for the caller method and a section for the called method. Both are X++ methods.

The called method makes an assignment to its meTest1 variable, but the caller cannot detect the assignment. The called method also calls a method on the object pointed to by meTest2, and the caller can detect the resulting change in the state of the object.

#### ![Cc586700.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc586700.collapse_all(en-us,AX.60).gif")Caller Method

    public void CallerMethodByValueObject // X++
    {
        MyEntity meTest1;
        MyEntity meTest2;
        ;
        meTest1 = new MyEntity(1);
        meTest2 = new MyEntity(33);
        DemoClassXpp::CalledMethodByValueObject
                (meTest1, meTest2);
        if (meTest1.GetCounter() == 1)
        {
            info("Good, == 1");
        }
        if (meTest2.GetCounter() == 36)
        {
            info("Good, == 36");
        }
    }

#### ![Cc586700.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc586700.collapse_all(en-us,AX.60).gif")Called Method

    static public void CalledMethodByValueObject // X++
            (
            MyEntity meTest1  // by value
            ,MyEntity meTest2 // by value
            )
    {
        ;
        meTest1 = new MyEntity(555); // Caller can not detect.
        meTest2 .AddToCounter(3); // Caller can detect.
    }

## By Reference

When a parameter is passed by reference, the pointer (that points to the object) is given to the called method. No copy of the pointer is created. Assignments made by the called method to its parameter variable are detectable by the caller method.

The purpose of passing parameters by reference is to overcome the limitation that only one item can be returned from a method. Every parameter passed by reference is basically returned to the caller.

### ![Cc586700.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc586700.collapse_all(en-us,AX.60).gif")int By Reference

When an int is passed by reference to a .NET method, the system converts the int into a new temporary object. Then the pointer to that object is given to the called method. When the called method returns, the temporary object is converted back to an int value. The value is again stored in the frame of the caller on the call stack.


> [!NOTE]
> <P>The operation that creates this kind of temporary object is often termed boxing.</P>



Changes made to the int parameter variable by the called method are detectable by the caller.

The following code example has a section for the X++ caller method and a section for the C\# called method. The called method adds 456 to its parameter variable iTest. The caller method can detect that the addition occurred.

#### ![Cc586700.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc586700.collapse_all(en-us,AX.60).gif")Caller Method

    public void CallerMethodByReferenceInt // X++
    {
        int iTest = 3;
        ;
        TheNamespace.DemoClassNet::CalledMethodByReferenceInt
                (byref iTest);
        if (iTest == 459)
        {
            info("Good, == 459.")
        }
    }

#### ![Cc586700.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc586700.collapse_all(en-us,AX.60).gif")Called Method

``` csharp
static public void CalledMethodByReferenceInt // C#
        (ref int iTest) // by reference
{
    iTest = iTest + 456; // Caller can detect.
}
```

### ![Cc586700.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc586700.collapse_all(en-us,AX.60).gif")Object By Reference

When an object is passed by reference, the pointer to the object is given to the called method. Therefore the caller and the called method both have the same pointer to the same object. No copy of the pointer is created.

Assignments made to the parameter variable in the called method are detectable by the caller.

The following code example has a section for the X++ caller method and a section for the C\# called method.

The called method makes an assignment to its meTest1 variable, and the caller can detect the assignment. The called method also calls a method on the object pointed to by meTest2, and the caller can detect the resulting change in the state of the object.

#### ![Cc586700.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc586700.collapse_all(en-us,AX.60).gif")Caller Method

    public void CallerMethodByReferenceObject // X++
    {
        MyEntity meTest1;
        MyEntity meTest2;
        ;
        meTest1 = new MyEntity(1);
        meTest2 = new MyEntity(33);
        TheNamespace.DemoClassNet::CalledMethodByReferenceObject
                (byref meTest1, byref meTest2);
        if (meTest1.GetCounter() == 555)
        {
            info("Good, == 555");
        }
        if (meTest2.GetCounter() == 36)
        {
            info("Good, == 36");
        }
    }

#### ![Cc586700.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Cc586700.collapse_all(en-us,AX.60).gif")Called Method

``` csharp
static public void CalledMethodByReferenceObject // C#
        (
        out MyEntity meTest1  // by reference
        ,ref MyEntity meTest2 // by reference
        )
{
    meTest1 = new MyEntity(555); // Caller can detect.
    meTest2 .AddToCounter(3); // Caller can detect.
}
```

## See also

[How to: Use the byref Keyword for CLR Interop](how-to-use-the-byref-keyword-for-clr-interop.md)

[.NET Interop from X++](net-interop-from-x.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

