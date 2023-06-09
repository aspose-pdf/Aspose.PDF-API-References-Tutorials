---
title: 使用标记图像创建 PDF
linktitle: 使用标记图像创建 PDF
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 创建带有标记图像的 PDF 的分步指南。
type: docs
weight: 40
url: /zh/net/programming-with-tagged-pdf/create-pdf-with-tagged-image/
---
在本教程中，我们将为您提供有关如何使用 Aspose.PDF for .NET 创建带有标记图像的 PDF 文档的分步指南。 Aspose.PDF 是一个功能强大的库，允许您以编程方式创建、操作和转换 PDF 文档。使用 Aspose.PDF 的标记内容结构功能，您可以将标记图像添加到您的 PDF 文档中。

## 先决条件

在开始之前，请确保您具备以下先决条件：

1. Visual Studio 安装了 .NET 框架。
2. .NET 的 Aspose.PDF 库。

## 第 1 步：项目设置

首先，在 Visual Studio 中创建一个新项目并添加对 Aspose.PDF for .NET 库的引用。您可以从 Aspose 官方网站下载该库并将其安装在您的机器上。

## 第 2 步：导入必要的命名空间

在您的 C# 代码文件中，导入访问 Aspose.PDF 提供的类和方法所需的命名空间：

```csharp
using System;
using Aspose.Pdf;
using Aspose.Pdf.Tagged;
```

## 第 3 步：创建带有标记图像的 PDF 文档

使用以下代码创建带有标记图像的 PDF 文档：

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Creating a PDF with a tagged image");
taggedContent.SetLanguage("fr-FR");

IllustrationElement figure1 = taggedContent.CreateFigureElement();
taggedContent.RootElement.AppendChild(figure1);
figure1.AlternativeText = "Aspose Logo";
figure1.Title = "Picture 1";
figure1.SetTag("Fig");
figure1.SetImage(dataDir + @"aspose-logo.jpg");
```

此代码创建一个空的 PDF 文档并使用 Aspose.PDF 提供的方法添加标记图像。图像用替代文本、标题和标签指定。

## 第 4 步：保存 PDF 文档

使用以下代码保存 PDF 文档：

```csharp
document.Save(dataDir + "PDFwithTaggedImage.pdf");
```

此代码将带有标记图像的 PDF 文档保存到指定文件。

### 使用 Aspose.PDF for .NET 创建带有标记图像的 PDF 的示例源代码 
```csharp

//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("CreatePDFwithTaggedImage");
taggedContent.SetLanguage("en-US");
IllustrationElement figure1 = taggedContent.CreateFigureElement();
taggedContent.RootElement.AppendChild(figure1);
figure1.AlternativeText = "Aspose Logo";
figure1.Title = "Image 1";
figure1.SetTag("Fig");
//添加分辨率为 300 DPI 的图像（默认情况下）
figure1.SetImage(dataDir + @"aspose-logo.jpg");
//保存 PDF 文档
document.Save(dataDir + "PDFwithTaggedImage.pdf");

```

## 结论

在本教程中，您学习了如何使用 Aspose.PDF for .NET 创建带有标记图像的 PDF 文档。标记图像向您的 PDF 文档添加额外的结构化信息。
