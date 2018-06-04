---
title: Calling Static X++ Methods
TOCTitle: Calling Static X++ Methods
ms:assetid: f4cd0eb1-2cbb-4554-b61d-85cbf7e7eff6
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Hh812513(v=AX.60)
ms:contentKeyID: 44090299
ms.date: 11/07/2012
mtps_version: v=AX.60
dev_langs:
- csharp
---

# Calling Static X++ Methods 


_**Applies To:** Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

From within code for a User Control, you can call static X++ methods for classes and tables. The Session object provides access to the AxaptaAdapter object. The AxaptaAdapter object has methods that you can use to call static X++ methods. See [Session Object](session-object.md) for detailed information about how to retrieve the Session object.

## Calling Static X++ Methods for Classes

To call a static method for a class, use CallStaticClassMethod() from the AxaptaAdapter object. For example, the following code defines the static method named triple for the Example class. This simple method triples the value that is passed to it.

    public static int triple(int _value)
    {
        return 3 * _value;
    }

The following code for a button in a User Control takes the text from the IntValue text box. It converts it to an integer, and then uses CallStaticClassMethod() to call the triple static method that is defined for the Example class. The result is displayed in the text box.

``` csharp
protected void TripleButton_Click(object sender, EventArgs e)
{
    int i;

    i = (int)AxSession.AxaptaAdapter.CallStaticClassMethod("Example", "triple", Convert.ToInt16(IntValue.Text));

    IntValue.Text = Convert.ToString(i);
}
```

## Calling Static X++ Methods for Tables

To call a static method for a table, use CallStaticRecordMethod() from the AxaptaAdapter object. For example, the following code for a button in a User Control takes the text from the CustAccount text box. It uses CallStaticRecordMethod() to call the exist static method that is defined for the CustTable table. If the customer account exists, true is returned. Otherwise, false is returned. The result is used to set the value of a check box.

``` csharp
protected void CustomerExists_Click(object sender, EventArgs e)
{
    Boolean exists;

    exists = (bool)AxSession.AxaptaAdapter.CallStaticRecordMethod("CustTable", "exist", CustAccount.Text);

    if (exists)
        cbExists.Checked = true;
    else
        cbExists.Checked = false;
}
```

