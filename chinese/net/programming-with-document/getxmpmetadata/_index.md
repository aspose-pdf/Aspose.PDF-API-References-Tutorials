---
title: 获取 XMP 元数据
linktitle: 获取 XMP 元数据
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 的 GetXmpMetadata 功能使用 C# 源代码从 PDF 文档中提取 XMP 元数据。
type: docs
weight: 200
url: /zh/net/programming-with-document/getxmpmetadata/
---

 Aspose.PDF for .NET 是一个流行的 PDF 操作库，它使开发人员能够在其 .NET 应用程序中创建、编辑和转换 PDF 文件。该库提供的功能之一是能够从 PDF 文档中提取 XMP 元数据。本教程将指导您完成使用`GetXmpMetadata`Aspose.PDF for .NET 的功能可以从 PDF 文档中提取 XMP 元数据。

## 第 1 步：为 .NET 安装 Aspose.PDF

要在您的 .NET 应用程序中使用 Aspose.PDF for .NET，您必须首先安装该库。您可以从以下位置下载最新版本的库[Aspose.PDF for .NET 下载页面](https://releases.aspose.com/pdf/net).

下载库后，将 ZIP 文件的内容解压缩到计算机上的文件夹中。然后您需要在您的 .NET 项目中添加对 Aspose.PDF for .NET DLL 的引用。

## 第 2 步：加载 PDF 文档

一旦您安装了 Aspose.PDF for .NET 并在您的 .NET 项目中添加了对 DLL 的引用，您就可以开始使用`GetXmpMetadata`从 PDF 文档中提取 XMP 元数据的功能。

使用此功能的第一步是加载要从中提取 XMP 元数据的 PDF 文档。为此，您可以使用以下代码：

```csharp
// PDF文档的路径
string dataDir = "YOUR DOCUMENT DIRECTORY";

//打开 PDF 文档
Document pdfDocument = new Document(dataDir + "GetXMPMetadata.pdf");
```

在上面的代码中，替换`"YOUR DOCUMENT DIRECTORY"`以及您的 PDF 文档所在目录的路径。此代码会将 PDF 文档加载到`Document`对象，然后您可以使用它来提取 XMP 元数据。

## 第 3 步：提取 XMP 元数据

要从 PDF 文档中提取 XMP 元数据，您可以使用以下代码：

```csharp
Console.WriteLine(pdfDocument.Metadata["xmp:CreateDate"]);
Console.WriteLine(pdfDocument.Metadata["xmp:Nickname"]);
Console.WriteLine(pdfDocument.Metadata["xmp:CustomProperty"]);
```

在上面的代码中，`xmp:CreateDate`, `xmp:Nickname` ， 和`xmp:CustomProperty`是您可以从 PDF 文档中提取的 XMP 元数据属性的示例。您可以将这些属性名称替换为您要提取的任何其他 XMP 元数据属性的名称。

### 使用 Aspose.PDF for .NET 获取 XMP 元数据的示例源代码

这是使用从 PDF 文档中提取 XMP 元数据的完整源代码`GetXmpMetadata`Aspose.PDF for .NET 的特点：

```csharp
// PDF文档的路径
string dataDir = "YOUR DOCUMENT DIRECTORY";

//打开 PDF 文档
Document pdfDocument = new Document(dataDir + "GetXMPMetadata.pdf");

//提取 XMP 元数据
Console.WriteLine(pdfDocument.Metadata["xmp:CreateDate"]);
Console.WriteLine(pdfDocument.Metadata["xmp:Nickname"]);
Console.WriteLine(pdfDocument.Metadata["xmp:CustomProperty"]);
```

在上面的代码中，替换`"YOUR DOCUMENT DIRECTORY"`以及您的 PDF 文档所在目录的路径。此代码将从 PDF 文档中提取 XMP 元数据并将其输出到控制台。