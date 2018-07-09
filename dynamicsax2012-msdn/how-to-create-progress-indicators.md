---
title: 'How to: Create Progress Indicators'
TOCTitle: 'How to: Create Progress Indicators'
ms:assetid: 9264cd96-4ceb-42bc-adef-0d8ac9c24d9b
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa841990(v=AX.60)
ms:contentKeyID: 35247470
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# How to: Create Progress Indicators 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Use a progress indicator during operations that take more than 2 seconds.

  - Use an hourglass mouse pointer if the process takes 2-7 seconds.

  - Use a progress bar if the process takes 8 seconds or more.

## Display an Hourglass Pointer

1.  Call the startLengthyOperation method when the operation starts.

2.  Call the endLengthyOperation method when the operation ends.

Both of these methods are on the Global application class.

The hourglass pointer is displayed until you call the endLengthyOperation method.


> [!NOTE]
> <P>You do not have to declare a variable when you use the Global class.</P>



### ![Aa841990.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa841990.collapse_all(en-us,AX.60).gif")Example: Display an Hourglass Pointer

The following example overrides the clicked method on a form control to refresh the database log.
```X++  
    void clicked()
    {
        super();
        startLengthyOperation();
        sysDatabaseLog_ds.research();
        endLengthyOperation();
    }
```
## Display a Progress Bar

1.  Initialize a SysOperationProgress variable.

2.  Set a caption for the form by using the SysOperationProgress.setCaption method.

3.  Set an animation to run while the operation is in progress by using the SysOperationProgress.setAnimation method.
    
    A number of animations are provided with Microsoft Dynamics AX. To view them, run the Tutorial\_ShowAVIFiles class. If you use one of these animation files, you need to declare the AviFiles macro at the top of your code.

4.  Specify the total number of operation steps.
    
    This is needed for the time-remaining calculation. If you do not set the total number of operation steps, the progress indicator is not shown. The total is often a count of the number of records, and may be time-consuming to calculate. Don't specify the total if the time is taken to calculate the records is comparable to the total time taken for the operation.

5.  Perform the operation. For each step, specify a description and a step number. For example:
    ```X++  
        for (i = 1; i <= 100; i++)
        {
            progress.setText(strfmt("Step %1", i));
            progress.incCount();
        }
    ```
    The description must be short and informative because it might change quickly during the execution.
    
    As an alternative to incCount() you can use setCount(int i).

During the execution, the progress indicator is updated accordingly. The estimated time remaining is calculated and displayed.

The default update interval is 3 seconds. If the task of updating the display takes more than 10% of the update interval due to latency on the network connection, the update interval is increased by 1 second.


> [!TIP]
> <P>Separate an operation into as many steps as possible. This gives the user the best information and the best remaining-time estimate. The time spent informing the user has no impact because the form is updated only once a second—even less frequently on low bandwidth connections.</P>



### ![Aa841990.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa841990.collapse_all(en-us,AX.60).gif")Example: Use a Single Progress Indicator

The following example creates a simple progress indicator.
```X++  
    static void operationProgress(Args _args)
    {
        #AviFiles
        SysOperationProgress progress = new SysOperationProgress();
        int i;
    
        ;
    
        progress.setCaption("My Task");
        progress.setAnimation(#AviUpdate);
        progress.setTotal(30000);
        for (i = 1; i <= 30000; i++)
        {
            progress.setText(strfmt("Step %1", i));
            progress.setCount(i, 1);
        }
    }
```
## Use More Than One Progress Indicator

If you have a more complex operation, you can have more than one progress indicator. All of the previously described methods have a default parameter that indicates which progress indicator (or bar) is being referred to.


> [!NOTE]
> <P>The time-remaining calculation is done solely on the first bar. The first bar must always show the overall progress.</P>



### ![Aa841990.collapse\_all(en-us,AX.60).gif](images/Gg863931.collapse_all(en-us,AX.60).gif "Aa841990.collapse_all(en-us,AX.60).gif")Example: Use Three Progress Indicators
```X++  
    static void SysOperationProgress(Args _args)
    {
        #define.count1(10)
        #define.count2(5)
        #define.count3(200)
        #AviFiles
        
        // 3 bars.
        SysOperationProgress progress = new SysOperationProgress(3);
        int i, j, k;
        ;
     
        progress.setCaption("My Task");
        progress.setAnimation(#AviUpdate);
     
        // Bar 1.
        progress.setTotal(#count1, 1);
        // Bar 2.
        progress.setTotal(#count2, 2);
        // Bar 3.
        progress.setTotal(#count3, 3);
     
        for (i=0; i<#count1; i++)
        {
            // Bar 1.
            progress.setText(strfmt("Bar 1 - Step %1 of %2", i, #count1), 1);
            progress.setCount(i, 1);
            for (j=0; j<#count2; j++)
            {
                // Bar 2.
                progress.setText(strfmt("Bar 2 - Step %1 of %2", j, #count2), 2);
                progress.setCount(j, 2);
                for (k=0; k<#count3; k++)
                {
                    // Bar 3.
                    progress.setText(
                        strfmt("Bar 3 - Step %1 of %2", k, #count3), 3);
                    progress.setCount(k, 3);
                    sleep(20);      // Time-consuming task.
                }
            }
        }
    }
```
## User Input During an Operation

Following are progress indicator options for user input during an operation:

  - SysOperationProgress.hide – hides the progress form and pauses the time-remaining calculation. The progress indicator reappears when setCount, incCount, or setText is subsequently called.

  - SysOperationProgress.kill – terminates the progress form and starts the progress again. You don't have to reset the caption, animation, and total.

## Using Progress Indicators with the Runbase Framework

Runbase is the standard framework for job execution, and must have a progress indicator. In the standard application, most progress indicators are used from the RunBase framework.

Use the RunBase.progressInit method to initialize the progress indicator:
```X++  
    public void progressInit(
        str       caption,
        int       total,
        Filename  animation,
        int       updateInterval = 1,
        int       numOfBars      = 1)
```
Indicating progress during the actual operation is similar to the standard Operation Progress framework. Use the member variable progress:

progress.incCount();

If you have more than one progress bar, use the progress variable defined in RunBase. It points to the Progress class initialized in the progressInit method. For example:
```X++  
    {
        this.progressInit("Caption",10,#AviFileCopy,1,2);
        progress.setCount(bar1count);
        progress.setTotal(maxBar2Count,bar2count);
        ...
        ...
        progress.setCount(bar2count,2);
    }
```
## See also

[RunBase Framework](runbase-framework.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

