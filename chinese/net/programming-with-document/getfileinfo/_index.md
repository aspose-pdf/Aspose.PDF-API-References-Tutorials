---
title: 获取文件信息
linktitle: 获取文件信息
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 的 GetFileInfo 功能来检索有关 PDF 文档的元数据信息。
type: docs
weight: 180
url: /zh/net/programming-with-document/getfileinfo/
---

 Aspose.PDF for .NET 是一个流行的 PDF 操作库，它使开发人员能够在其 .NET 应用程序中创建、编辑和转换 PDF 文件。该库提供的功能之一是能够检索有关 PDF 文档元数据的信息。本教程将指导您完成使用`GetFileInfo`Aspose.PDF for .NET 的功能，用于检索有关 PDF 文档元数据的信息。

## 第 1 步：为 .NET 安装 Aspose.PDF

要在您的 .NET 应用程序中使用 Aspose.PDF for .NET，您必须首先安装该库。您可以从以下位置下载最新版本的库[Aspose.PDF for .NET 下载页面](https://releases.aspose.com/pdf/net).

下载库后，将 ZIP 文件的内容解压缩到计算机上的文件夹中。然后您需要在您的 .NET 项目中添加对 Aspose.PDF for .NET DLL 的引用。

## 第 2 步：加载 PDF 文档

一旦您安装了 Aspose.PDF for .NET 并在您的 .NET 项目中添加了对 DLL 的引用，您就可以开始使用`GetFileInfo`检索有关 PDF 文档元数据的信息的功能。

使用此功能的第一步是加载要检索其信息的 PDF 文档。为此，您可以使用以下代码：

```csharp
// PDF文档的路径
string dataDir = "YOUR DOCUMENT DIRECTORY";

//打开 PDF 文档
Document pdfDocument = new Document(dataDir + "GetFileInfo.pdf");
```

在上面的代码中，替换`"YOUR DOCUMENT DIRECTORY"`以及您的 PDF 文档所在目录的路径。此代码会将 PDF 文档加载到`Document`对象，然后您可以使用它来检索有关文档元数据的信息。

## 第 3 步：检索文档的元数据

要检索有关 PDF 文档元数据的信息，您可以使用以下代码：

```csharp
//获取文档信息
DocumentInfo docInfo = pdfDocument.Info;

//显示文档信息
Console.WriteLine("Author: {0}", docInfo.Author);
Console.WriteLine("Creation Date: {0}", docInfo.CreationDate);
Console.WriteLine("Keywords: {0}", docInfo.Keywords);
Console.WriteLine("Modify Date: {0}", docInfo.ModDate);
Console.WriteLine("Subject: {0}", docInfo.Subject);
Console.WriteLine("Title: {0}", docInfo.Title);
```

在上面的代码中，每一行检索 PDF 文档的不同元数据属性并将其输出到控制台。您可以自定义此代码以仅检索您感兴趣的属性。

### 示例源代码使用 Aspose.PDF for .NET 获取 PDF 文件信息

这是使用检索 PDF 文档的元数据的完整源代码`GetFileInfo`Aspose.PDF for .NET 的特点：

```csharp
// PDF文档的路径
string dataDir = "YOUR DOCUMENT DIRECTORY";

//打开 PDF 文档
Document pdfDocument = new Document(dataDir + "GetFileInfo.pdf");

//获取文档信息
DocumentInfo docInfo = pdfDocument.Info;

//显示文档信息
Console.WriteLine("Author: {0}", docInfo.Author);
Console.WriteLine("Creation Date: {0}", docInfo.CreationDate);
Console.WriteLine("Keywords: {0}", docInfo.Keywords);
Console.WriteLine("Modify Date: {0}", docInfo.ModDate);
Console.WriteLine("Subject: {0}", docInfo.Subject);
Console.WriteLine("Title: {0}", docInfo.Title);
```