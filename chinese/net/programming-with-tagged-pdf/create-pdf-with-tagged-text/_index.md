---
title: 使用标记文本创建 PDF
linktitle: 使用标记文本创建 PDF
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 创建带有标记文本的 PDF 的分步指南。
type: docs
weight: 50
url: /zh/net/programming-with-tagged-pdf/create-pdf-with-tagged-text/
---
在本教程中，我们将为您提供有关如何使用 Aspose.PDF for .NET 创建带有标记文本的 PDF 文档的分步指南。 Aspose.PDF 是一个功能强大的库，允许您以编程方式创建、操作和转换 PDF 文档。使用 Aspose.PDF 的标记内容结构功能，您可以将标记文本添加到您的 PDF 文档中。

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

## 第 3 步：创建带有标记文本的 PDF 文档

使用以下代码创建带有标记文本的 PDF 文档：

```csharp
string dataDir = "YOUR_DIRECTORY_OF_DOCUMENTS";
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Tagged PDF document");
taggedContent.SetLanguage("fr-FR");

HeaderElement headerElement = taggedContent.CreateHeaderElement();
headerElement.ActualText = "Header 1";

ParagraphElement paragraphElement1 = taggedContent.CreateParagraphElement();
paragraphElement1.ActualText = "test1";

//在此处添加更多段落

//保存 PDF 文档
document.Save(dataDir + "PDFwithTagText.pdf");
```

此代码创建一个空的 PDF 文档并使用 Aspose.PDF 提供的方法添加标记文本。您可以使用适当的方法添加其他标记的文本元素，例如标题和段落。

### 使用 Aspose.PDF for .NET 创建带有标记文本的 PDF 的示例源代码 
```csharp

//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//创建 PDF 文档
Document document = new Document();
//使用 TaggedPdf 获取内容
ITaggedContent taggedContent = document.TaggedContent;
//为 Documnet 设置标题和语言
taggedContent.SetTitle("Tagged Pdf Document");
taggedContent.SetLanguage("en-US");
//创建文本块级结构元素
HeaderElement headerElement = taggedContent.CreateHeaderElement();
headerElement.ActualText = "Heading 1";
ParagraphElement paragraphElement1 = taggedContent.CreateParagraphElement();
paragraphElement1.ActualText = "test1";
ParagraphElement paragraphElement2 = taggedContent.CreateParagraphElement();
paragraphElement2.ActualText = "test 2";
ParagraphElement paragraphElement3 = taggedContent.CreateParagraphElement();
paragraphElement3.ActualText = "test 3";
ParagraphElement paragraphElement4 = taggedContent.CreateParagraphElement();
paragraphElement4.ActualText = "test 4";
ParagraphElement paragraphElement5 = taggedContent.CreateParagraphElement();
paragraphElement5.ActualText = "test 5";
ParagraphElement paragraphElement6 = taggedContent.CreateParagraphElement();
paragraphElement6.ActualText = "test 6";
ParagraphElement paragraphElement7 = taggedContent.CreateParagraphElement();
paragraphElement7.ActualText = "test 7";
//保存 PDF 文档
document.Save( dataDir + "PDFwithTaggedText.pdf");

```

## 结论

在本教程中，您学习了如何使用 Aspose.PDF for .NET 创建带有标记文本的 PDF 文档。 Aspose.PDF 的标记内容结构功能允许您构建和组织您的文本以获得更好的可访问性和语义。
