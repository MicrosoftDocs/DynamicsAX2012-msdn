---
title: Secured APIs
TOCTitle: Secured APIs
ms:assetid: a81bca0f-4035-4902-a793-eeb1fd91b8c9
ms:mtpsurl: https://msdn.microsoft.com/en-us/library/Aa852189(v=AX.60)
ms:contentKeyID: 35248500
ms.date: 05/18/2015
mtps_version: v=AX.60
dev_langs:
- powershell
---

# Secured APIs 


_**Applies To:** Microsoft Dynamics AX 2012 R3, Microsoft Dynamics AX 2012 R2, Microsoft Dynamics AX 2012 Feature Pack, Microsoft Dynamics AX 2012_

Certain APIs that ship with Microsoft Dynamics AX use [Code Access Security](code-access-security.md). When these APIs are run on the server, a class derived from CodeAccessPermission must be used. This helps make the APIs more secure. When you upgrade from a previous version of Microsoft Dynamics AX, you must modify calls to these APIs to ensure that the code executes correctly.


> [!NOTE]
> <P>The security feature is enabled by default. You can disable the feature or simulate the feature when you're testing code by using the following command at the command-line window.</P>



``` powershell
ax32serv.exe -console 01 -caslevel=[enable/disable/trace]
```

When you use the **trace** switch to simulate the feature, Infolog reports any APIs that are called incorrectly.

When you run ax32serv.exe from the command line, you are running an instance of Application Object Server (AOS) as a non-service.

APIs that use Code Access Security are shown in the following list. For more information about calling these APIs, see [How to: Secure an API on the AOS](how-to-secure-an-api-on-the-aos.md).

[AOSLoadGen.new](https://msdn.microsoft.com/en-us/library/gg802526\(v=ax.60\)) method

[AsciiIo.new](https://msdn.microsoft.com/en-us/library/gg802696\(v=ax.60\)) method

[BinaryIo.new](https://msdn.microsoft.com/en-us/library/gg820685\(v=ax.60\)) method

[BinData.loadFile](https://msdn.microsoft.com/en-us/library/gg820723\(v=ax.60\)) method

[BinData.saveFile](https://msdn.microsoft.com/en-us/library/gg820731\(v=ax.60\)) method

[CLRInterop.new](https://msdn.microsoft.com/en-us/library/gg803396\(v=ax.60\)) method

[CLRInterop::getAnyTypeForObject](https://msdn.microsoft.com/en-us/library/gg803036\(v=ax.60\)) method

[CLRInterop::getLastException](https://msdn.microsoft.com/en-us/library/gg803038\(v=ax.60\)) method

[CLRInterop::getObjectForAnyType](https://msdn.microsoft.com/en-us/library/gg803039\(v=ax.60\)) method

[CLRInterop::staticInvoke](https://msdn.microsoft.com/en-us/library/gg803400\(v=ax.60\)) method

[CLRObject.dispatch](https://msdn.microsoft.com/en-us/library/gg803402\(v=ax.60\)) method

[CLRObject.new](https://msdn.microsoft.com/en-us/library/gg803405\(v=ax.60\)) method

[COM.new](https://msdn.microsoft.com/en-us/library/gg803460\(v=ax.60\)) method

[COMDispFunction.call](https://msdn.microsoft.com/en-us/library/gg803465\(v=ax.60\)) method

[Comma7Io.new](https://msdn.microsoft.com/en-us/library/gg821072\(v=ax.60\)) method

[CommaIo.new](https://msdn.microsoft.com/en-us/library/gg821100\(v=ax.60\)) method

[CommaTextIo.new](https://msdn.microsoft.com/en-us/library/gg821138\(v=ax.60\)) method

[DictClass.callObject](https://msdn.microsoft.com/en-us/library/gg837546\(v=ax.60\)) method

[DictClass.callStatic](https://msdn.microsoft.com/en-us/library/gg837548\(v=ax.60\)) method

[DictTable.callObject](https://msdn.microsoft.com/en-us/library/gg842542\(v=ax.60\)) method

[DictTable.callStatic](https://msdn.microsoft.com/en-us/library/gg842543\(v=ax.60\)) method

[DLL.new](https://msdn.microsoft.com/en-us/library/gg804384\(v=ax.60\)) method

[DLLFunction.call](https://msdn.microsoft.com/en-us/library/gg804386\(v=ax.60\)) method

[evalBuf](https://msdn.microsoft.com/en-us/library/aa858407\(v=ax.60\)) function

[Io.new](https://msdn.microsoft.com/en-us/library/gg921460\(v=ax.60\)) method

[runAs](https://msdn.microsoft.com/en-us/library/aa893873\(v=ax.60\)) function

[runBuf](https://msdn.microsoft.com/en-us/library/aa656300\(v=ax.60\)) function

[Statement.executeQuery](https://msdn.microsoft.com/en-us/library/gg926451\(v=ax.60\)) method

[Statement.executeUpdate](https://msdn.microsoft.com/en-us/library/gg926452\(v=ax.60\)) method

[TextBuffer.fromFile](https://msdn.microsoft.com/en-us/library/gg957938\(v=ax.60\)) method

[TextBuffer.toFile](https://msdn.microsoft.com/en-us/library/gg957970\(v=ax.60\)) method

[TextIo.new](https://msdn.microsoft.com/en-us/library/gg957992\(v=ax.60\)) method

[Thread.new](https://msdn.microsoft.com/en-us/library/gg926882\(v=ax.60\)) method

[Thread::executeInUIThread](https://msdn.microsoft.com/en-us/library/gg926872\(v=ax.60\)) method

[Thread::getThisThread](https://msdn.microsoft.com/en-us/library/gg926878\(v=ax.60\)) method

[TreeNode.treeNodeExport](https://msdn.microsoft.com/en-us/library/gg958206\(v=ax.60\)) method

[WinAPIServer::copyFile](https://msdn.microsoft.com/en-us/library/gg764668\(v=ax.60\)) method

[WinAPIServer::createFile](https://msdn.microsoft.com/en-us/library/gg784970\(v=ax.60\)) method

[WinAPIServer::deleteFile](https://msdn.microsoft.com/en-us/library/gg784981\(v=ax.60\)) method

[WinAPIServer::fileExists](https://msdn.microsoft.com/en-us/library/gg784982\(v=ax.60\)) method

[WinAPIServer::fileSize](https://msdn.microsoft.com/en-us/library/gg784985\(v=ax.60\)) method

[WinAPIServer::getFileModifiedDate](https://msdn.microsoft.com/en-us/library/gg784993\(v=ax.60\)) method

[WinAPIServer::getTempPath](https://msdn.microsoft.com/en-us/library/gg785007\(v=ax.60\)) method

[WinAPIServer::pathExists](https://msdn.microsoft.com/en-us/library/gg785013\(v=ax.60\)) method

[XmlDocument.load](https://msdn.microsoft.com/en-us/library/gg949342\(v=ax.60\)) method

[XmlDocument.save](https://msdn.microsoft.com/en-us/library/gg949363\(v=ax.60\)) method

[XmlDocument::newFile](https://msdn.microsoft.com/en-us/library/gg949352\(v=ax.60\)) method

[XmlNode.transformNode](https://msdn.microsoft.com/en-us/library/gg949525\(v=ax.60\)) method

[XmlReader::newFile](https://msdn.microsoft.com/en-us/library/gg928495\(v=ax.60\)) method

[XmlReaderSettings.prohibitDtd](https://msdn.microsoft.com/en-us/library/gg928535\(v=ax.60\)) method

[XmlResolver.allowFileAccess](https://msdn.microsoft.com/en-us/library/gg928537\(v=ax.60\)) method

[XmlResolver.allowWebAccess](https://msdn.microsoft.com/en-us/library/gg928538\(v=ax.60\)) method

[XmlResolver.baseUrlOverride](https://msdn.microsoft.com/en-us/library/gg928539\(v=ax.60\)) method

[XmlResolver.useCredentials](https://msdn.microsoft.com/en-us/library/gg928542\(v=ax.60\)) method

[XmlSchema.writeToFile](https://msdn.microsoft.com/en-us/library/gg949662\(v=ax.60\)) method

[XmlSchema::newFile](https://msdn.microsoft.com/en-us/library/gg949655\(v=ax.60\)) method

[XmlTextReader::newFile](https://msdn.microsoft.com/en-us/library/gg959610\(v=ax.60\)) method

[XmlTextReader.prohibitDtd](https://msdn.microsoft.com/en-us/library/gg959613\(v=ax.60\)) method

[XmlTextWriter::newFile](https://msdn.microsoft.com/en-us/library/gg959623\(v=ax.60\)) method

[XmlTransform::execute](https://msdn.microsoft.com/en-us/library/gg959626\(v=ax.60\)) method

[XmlWriter::newFile](https://msdn.microsoft.com/en-us/library/gg959635\(v=ax.60\)) method

[XppCompiler.new](https://msdn.microsoft.com/en-us/library/gg929107\(v=ax.60\)) method

[XppCompiler.execute](https://msdn.microsoft.com/en-us/library/gg929104\(v=ax.60\)) method

[XppCompiler.executeEx](https://msdn.microsoft.com/en-us/library/gg929105\(v=ax.60\)) method

[xRecord.skipAosValidation](https://msdn.microsoft.com/en-us/library/gg950408\(v=ax.60\)) method

## See also

[How to: Secure an API on the AOS](how-to-secure-an-api-on-the-aos.md)

  
**Announcements:** New book: "Inside Microsoft Dynamics AX 2012 R3" now available. Get your copy at the [MS Press Store](https://www.microsoftpressstore.com/store/inside-microsoft-dynamics-ax-2012-r3-9780735685109).

