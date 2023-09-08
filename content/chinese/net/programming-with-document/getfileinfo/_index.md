---
title: 获取 PDF 文件中的文件信息
linktitle: 获取 PDF 文件中的文件信息
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 的 PDF 文件中的 GetFileInfo 功能来检索有关 PDF 文档的元数据信息。
type: docs
weight: 180
url: /zh/net/programming-with-document/getfileinfo/
---
 Aspose.PDF for .NET 是一个流行的 PDF 操作库，使开发人员能够在其 .NET 应用程序中创建、编辑和转换 PDF 文件。该库提供的功能之一是能够检索有关 PDF 文档元数据的信息。本教程将指导您完成使用`GetFileInfo`Aspose.PDF for .NET 的功能可检索有关 PDF 文档元数据的信息。

## 第 1 步：安装 Aspose.PDF for .NET

要在 .NET 应用程序中使用 Aspose.PDF for .NET，您必须首先安装该库。您可以从以下位置下载该库的最新版本[Aspose.PDF for .NET 下载页面](https://releases.aspose.com/pdf/net).

下载该库后，将 ZIP 文件的内容解压到计算机上的文件夹中。然后，您需要在 .NET 项目中添加对 Aspose.PDF for .NET DLL 的引用。

## 第 2 步：加载 PDF 文档

安装 Aspose.PDF for .NET 并在 .NET 项目中添加对 DLL 的引用后，您就可以开始使用`GetFileInfo`检索有关 PDF 文档元数据的信息的功能。

使用此功能的第一步是加载您想要检索其信息的 PDF 文档。为此，您可以使用以下代码：

```csharp
// PDF文档的路径
string dataDir = "YOUR DOCUMENT DIRECTORY";

//打开 PDF 文档
Document pdfDocument = new Document(dataDir + "GetFileInfo.pdf");
```

在上面的代码中，替换`"YOUR DOCUMENT DIRECTORY"`以及 PDF 文档所在目录的路径。此代码会将 PDF 文档加载到`Document`对象，然后您可以使用该对象检索有关文档元数据的信息。

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

### 使用 Aspose.PDF for .NET 获取 PDF 文件信息的示例源代码

以下是使用以下命令检索 PDF 文档元数据的完整源代码`GetFileInfo` Aspose.PDF for .NET 的功能：

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

## 结论

在本教程中，我们讨论了如何使用 Aspose.PDF for .NET 检索有关 PDF 文档元数据的信息。通过加载 PDF 文档并访问其元数据属性，您可以收集有关文档特征和属性的信息。 Aspose.PDF for .NET 提供了一个简单易用的 API 来处理 PDF 文档，包括检索元数据信息，使其成为 .NET 应用程序中 PDF 操作的宝贵工具。

### 常见问题解答

#### 问：PDF 文档中的元数据是什么？

答：PDF文档中的元数据是指描述文档属性和特征的信息。此信息通常包括文档的标题、作者、主题、关键字、创建日期、修改日期等。

#### 问：如何在我的 .NET 项目中安装 Aspose.PDF for .NET？

答：要安装 Aspose.PDF for .NET，您需要从以下位置下载该库：[Aspose.PDF for .NET 下载页面](https://releases.aspose.com/pdf/net)。下载后，解压 ZIP 文件的内容并在 .NET 项目中添加对 Aspose.PDF for .NET DLL 的引用。

#### 问：我可以自定义代码以仅检索特定元数据属性吗？

答：是的，您可以通过注释掉不需要的行来自定义代码以检索特定的元数据属性。代码中的每一行都对应一个特定的元数据属性，因此您可以根据需要包含或排除属性。

#### 问：我可以使用 Aspose.PDF for .NET 检索哪些类型的元数据属性？

答：使用Aspose.PDF for .NET，您可以检索PDF文档的各种元数据属性，包括作者、标题、主题、关键字、创建日期和修改日期。