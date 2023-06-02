---
title: PDF 到 EPUB
linktitle: PDF 到 EPUB
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 将 PDF 转换为 EPUB 的分步指南。
type: docs
weight: 120
url: /zh/net/document-conversion/pdf-to-epub/
---

在本教程中，我们将指导您使用 Aspose.PDF for .NET 将 PDF 文件转换为 EPUB 格式。 PDF 格式通常用于显示文档，而 EPUB 格式是专门为电子书设计的。按照以下步骤，您将能够将 PDF 文件转换为 EPUB 格式。

## 先决条件
在开始之前，请确保满足以下先决条件：

- C# 编程语言的基础知识。
- .NET 的 Aspose.PDF 库安装在您的系统上。
- 开发环境，例如 Visual Studio。

## 第 1 步：加载 PDF 文档
在此步骤中，我们将使用 Aspose.PDF for .NET 上传 PDF 文件。请遵循以下代码：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//加载 PDF 文档
Document pdfDocument = new Document(dataDir + "PDFToEPUB.pdf");
```

务必更换`"YOUR DOCUMENTS DIRECTORY"`使用您的 PDF 文件所在的实际目录。

## 第 2 步：实例化 EPUB 保存选项
加载 PDF 文档后，我们将实例化 EPUB 格式的保存选项。使用以下代码：

```csharp
//实例化 EPUB 备份选项
EpubSaveOptions options = new EpubSaveOptions();
```

## 第三步：内容排版规范
现在我们将指定 EPUB 图书内容的布局。使用以下代码：

```csharp
//内容布局规范
options.ContentRecognitionMode = EpubSaveOptions.RecognitionMode.Flow;
```

## 第 4 步：保存 EPUB 文件
一旦我们配置了保存选项，我们现在可以保存生成的 EPUB 文件。这是最后一步：

```csharp
//保存 EPUB 文件
pdfDocument.Save(dataDir + "PDFToEPUB_out.epub", options);
```

代替`"YOUR DOCUMENTS DIRECTORY"`使用要保存输出 EPUB 文件的所需目录。

### 使用 Aspose.Words for .NET 将 PDF 转换为 EPUB 的示例源代码

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//载入PDF文件
Document pdfDocument = new Document(dataDir + "PDFToEPUB.pdf");

//实例化 Epub 保存选项
EpubSaveOptions options = new EpubSaveOptions();

//指定内容的布局
options.ContentRecognitionMode = EpubSaveOptions.RecognitionMode.Flow;

//保存 ePUB 文档
pdfDocument.Save(dataDir + "PDFToEPUB_out.epub", options);
```

## 结论
在本教程中，我们介绍了使用 Aspose.PDF for .NET 将 PDF 文件转换为 EPUB 格式的分步过程。按照上述说明，您可以轻松地将 PDF 文件转换为 EPUB 格式。此功能对于将 PDF 文档转换为可在不同设备上阅读的电子书特别有用。