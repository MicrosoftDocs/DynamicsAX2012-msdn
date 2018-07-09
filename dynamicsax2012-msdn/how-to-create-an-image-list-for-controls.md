---
title: 'How to: Create an Image List for Controls'
TOCTitle: 'How to: Create an Image List for Controls'
ms:assetid: fce02eca-795a-4609-888f-69474431800a
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa892733(v=AX.60)
ms:contentKeyID: 35254202
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Create an Image List for Controls 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

If you use a Tree or a ListView control in a form, you must generate an image list that is loaded when the form is opened and released when the form is closed.

You can also use an image list in a Window control if the control is bound to an integer database field. The control uses the value of the field as an index to the image to be used.

Images in the list must be registered in the resAppl macro (in the **Macros** node in the Application Object Tree (AOT)).


> [!TIP]
> <P>Open the tutorial_Resources form to view the images already registered in the resAppl macro.</P>



## Create an Image List

1.  Create a class that extends the ImageListAppl class.

2.  Name the class ImageListAppl \_XXX.
    
    For example, ImageListAppl\_Aot, ImageListAppl\_Prod.

3.  Override the build method to add the images to the list. You must call super() before adding your own code. For example:
    
       ```X++
       void build()
        {
            super(); 
            this.Add(#ImageProduction);
            this.Add(#ImageItem);
            this.Add(#ImageBOM);
            this.Add(#ImageService);
            this.Add(#ImageSetUp);
            this.Add(#ImageProcess);
            this.Add(#ImageQty);
        }
       ```


> [!TIP]
> <P>To ascertain how image lists are used in the application, open the tutorial<EM>_</EM>formListControl and tutorial_formTreeControl forms, and then check the ImageListAppl_* application classes.</P>



## Example: Use an Image List in a Form

Wherever you use a Tree control or a ListView control in a form, make modifications that correspond to those in the following example. It uses the ImageListAppl\_Prod image list.

```X++
    void classDeclaration()
    {
        #resAppl
        ImageListAppl_Prod   imageListAppl_Prod;
        FormTreeControl      tree;
        FormListControl      list;
    }
    void init()
    {
        tree = element.control(control::myTree);
        list = element.control(control::myList);
        imageListAppl_Prod = new ImageListAppl_Prod();
        tree.SetImageList(imageListAppl_Prod.ImageList());
        list.SetImageList(imageListAppl_Prod.ImageList());
    }
    void insertTreeItem(int parent, str name)
    {
        FormTreeItem   item = new FormTreeItem(
            name,
            imageListAppl_Prod.Image(#ImageProduction)   , 1);
        ;
        tree.AddItem(parent,   FormTreeAdd::Last, item)
    }
    void insertListItem(int parent, str name)
    {
        FormListItem item = new FormListItem(
            name, 
            imageListAppl_Prod.Image(#ImageProduction));
        ;
        list.AddItem(item);
    }
```

## See also

[Image Manipulation Classes](image-manipulation-classes.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

