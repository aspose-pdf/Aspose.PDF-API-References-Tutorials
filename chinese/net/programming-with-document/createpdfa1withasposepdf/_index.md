---
title: 使用 Aspose Pdf 创建 PDF A1
linktitle: 使用 Aspose Pdf 创建 PDF A1
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 创建 PDF A1 文档。带 C# 源代码的分步指南。有效优化 PDF。
type: docs
weight: 90
url: /zh/net/programming-with-document/createpdfa1withasposepdf/
---

在本分步指南中，我们将解释如何使用 Aspose.PDF for .NET 创建 PDF A1 文档。我们将为您提供完成此任务所需的 C# 源代码和说明。

## 第 1 步：定义变量并导入命名空间

一、定义变量`dataDir`表示存储文档的目录。这将用于指定输出文件路径。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

接下来，创建一个新的实例`Document`来自 Aspose.PDF 的类。

```csharp
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
```

## 第 2 步：向 PDF 添加内容

在此步骤中，我们将向 PDF 文档添加一个页面并插入一个包含文本“Hello World!”的文本片段。

```csharp
pdf1.Pages.Add().Paragraphs.Add(new TextFragment("Hello World!"));
```

## 第 3 步：将 PDF 保存到内存流

要将 PDF 转换为 PDF/A1 格式，我们需要将其保存到内存流中。

```csharp
MemoryStream ms = new MemoryStream();
pdf1.Save(ms);
```

## 第 4 步：将 PDF 转换为 PDF/A1 格式

现在，我们将使用以下方法将 PDF 转换为 PDF/A1 格式`Convert`的方法`Document`班级。我们传递一个新的内存流作为输出流并指定`PdfFormat.PDF_A_1A`格式。

```csharp
pdf1.Convert(new MemoryStream(), PdfFormat.PDF_A_1A, ConvertErrorAction.Delete);
```

## 第 5 步：保存转换后的 PDF

最后将转换后的PDF保存到指定目录。

```csharp
pdf1.Save(dataDir + "CreatePdfA1_out.pdf");
```

### 使用 Aspose.PDF for .NET 创建 PDF A1 的示例源代码

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
//在pdf文档中添加一个页面
pdf1.Pages.Add().Paragraphs.Add(new TextFragment("Hello World!"));
MemoryStream ms = new MemoryStream();
//保存文件
pdf1.Save(ms);
pdf1.Convert(new MemoryStream(), PdfFormat.PDF_A_1A, ConvertErrorAction.Delete);
pdf1.Save(dataDir + "CreatePdfA1_out.pdf");
```

按照这些步骤并使用提供的源代码，您可以使用 Aspose.PDF for .NET 创建 PDF A1 文档。

请记住使用要保存输出文件的适当目录路径调整“您的文档目录”。


