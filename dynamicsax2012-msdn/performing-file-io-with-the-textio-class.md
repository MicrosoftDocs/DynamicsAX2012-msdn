---
title: Performing File IO with the TextIo Class
TOCTitle: Performing File IO with the TextIo Class
ms:assetid: 7a5fe2a8-7f58-4502-adb3-7eac51ab7dd5
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Cc967403(v=AX.60)
ms:contentKeyID: 35246083
ms.date: 05/18/2015
mtps_version: v=AX.60
---

# Performing File IO with the TextIo Class 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

X++ code performs file input and output (IO) by using the TextIo class. TextIo uses Unicode.

## X++ Sample

The following X++ job code sample creates a file and writes to it. Next the code reads from the file, and prints every record to the Infolog.

The use of the FileIOPermission class is also illustrated. FileIoPermission is used to assert that the current method has the authority to call another method that checks for such authority. For more information, see [Code Access Security](code-access-security.md).

    static void Job_File_IO_TextIo_Write_Read(Args _args)
    {
        TextIo txIoRead,
             txIoWrite;
        FileIOPermission fioPermission;
        container containFromRead;
        int xx,
            iConLength;
        str sTempPath,
            sFileName = "Test_File_IO.txt",
            sOneRecord;
        ;
        // Get the temporary path.
        sTempPath = WINAPI::getTempPath();
        info("File is at: " + sTempPath + sFileName);
    
        // Assert permission.
        fioPermission = new FileIOPermission
            (sTempPath + sFileName ,"RW");
        fioPermission.assert();
     
        // If the test file already exists, delete it.
        if (WINAPI::fileExists(sFileName))
        {
            WINAPI::deleteFile(sTempPath + sFileName);
        }
        
        // Open a test file for writing.
        // "W" mode overwrites existing content, or creates the file.
        txIoWrite = new TextIo( sTempPath + sFileName ,"W");
    
        // Write records to the file.
        txIoWrite.write("Hello        World.");
        txIoWrite.write("The sky is blue.");
        txIoWrite.write("");
        txIoWrite.write("// EOFile");
    
        // Close the test file.
        txIoWrite = null;
    
        // Open the same file for reading.
        txIoRead = new TextIo(sTempPath + sFileName ,"R");
        // Read the entire file into a container.
        containFromRead = txIoRead.read();
    
        // Loop through the container of file records.
        while (containFromRead)
        {
            sOneRecord = "";
            iConLength = conLen(containFromRead);
            // Loop through the token in the current record.
            for (xx=1; xx <= iConLength; xx++)
            {
                if (xx > 1) sOneRecord += " ";
                sOneRecord += conPeek(containFromRead ,xx);
            }
            info(sOneRecord);
    
            // Read the next record from the container.
            containFromRead = txIoRead.read();
        }
    
        // Close the test file.
        txIoRead = null;
        // Delete the test file.
        WINAPI::deleteFile(sTempPath + sFileName);
    
        // revertAssert is not really necessary here,
        // because the job (or method) is ending.
        CodeAccessPermission::revertAssert();
    }

## X++ Sample Output

The following is the actual Infolog output.


> [!NOTE]
> <P>Several spaces between Hello and World are condensed to one space in the output. This occurs because the read method uses a string of one or more space characters as a delimiter of tokens, and only the tokens are put into the returned container.</P>



    Message (14:12:47)
    File is at: C:\DOCUME~1\myalias\LOCALS~1\Temp\Test_File_IO.txt
    Hello World.
    The sky is blue.
    
    // EOFile

## See also

[Microsoft Dynamics AX Class Overview](microsoft-dynamics-ax-class-overview.md)

[TextIo Class](https://msdn.microsoft.com/en-us/library/gg957982\(v=ax.60\))

[CommaTextIo Class](https://msdn.microsoft.com/en-us/library/gg821130\(v=ax.60\))

[BinaryIo Class](https://msdn.microsoft.com/en-us/library/gg820682\(v=ax.60\))

[FileIOPermission Class](https://msdn.microsoft.com/en-us/library/gg839563\(v=ax.60\))

[TextBuffer Class](https://msdn.microsoft.com/en-us/library/gg957944\(v=ax.60\))

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

