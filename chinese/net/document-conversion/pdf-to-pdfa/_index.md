---
title: PDF转PDFA
linktitle: PDF转PDFA
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 将 PDF 转换为 PDFA 的分步指南。
type: docs
weight: 140
url: /zh/net/document-conversion/pdf-to-pdfa/
---

在本教程中，我们将引导您完成使用 Aspose.PDF for .NET 将 PDF 文件转换为 PDF/A 格式的过程。 PDF/A 格式是保证电子文档长期保存的 ISO 标准。按照以下步骤，您将能够将 PDF 文件转换为 PDF/A 格式。

## 先决条件
在开始之前，请确保满足以下先决条件：

- C# 编程语言的基础知识。
- .NET 的 Aspose.PDF 库安装在您的系统上。
- 开发环境，例如 Visual Studio。

## 第 1 步：打开源 PDF 文档
在此步骤中，我们将使用 Aspose.PDF for .NET 打开源 PDF 文件。请遵循以下代码：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//打开源 PDF 文档
Document pdfDocument = new Document(dataDir + "PDFToPDFA.pdf");
```

务必更换`"YOUR DOCUMENTS DIRECTORY"`使用您的 PDF 文件所在的实际目录。

## 第 2 步：转换为 PDF/A 格式
打开 PDF 文件后，我们可以继续转换为 PDF/A 格式。使用以下代码：

```csharp
//转换为 PDF/A 兼容文档
//在转换过程中，还会执行验证
pdfDocument.Convert(dataDir + "log.xml", PdfFormat.PDF_A_1B, ConvertErrorAction.Delete);
```

上述代码将 PDF 文件转换为 PDF/A-1b 格式，并在转换过程中执行验证。任何错误都记录在`"log.xml"`文件。

## 第 3 步：保存生成的 PDF/A 文件
转换完成后，我们需要保存生成的PDF/A文件。这是最后一步：

```csharp
dataDir = dataDir + "PDFToPDFA_out.pdf";
//保存输出文件
pdfDocument.Save(dataDir);
```

代替`"YOUR DOCUMENTS DIRECTORY"`使用要保存输出 PDF/A 文件的所需目录。

### 使用 Aspose.Words for .NET 将 PDF 转换为 HTML 的示例源代码

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//打开文档
Document pdfDocument = new Document(dataDir + "PDFToPDFA.pdf");

//转换为 PDF/A 兼容文档
//在转换过程中，还会执行验证
pdfDocument.Convert(dataDir + "log.xml", PdfFormat.PDF_A_1B, ConvertErrorAction.Delete);

dataDir = dataDir + "PDFToPDFA_out.pdf";
//保存输出文档
pdfDocument.Save(dataDir);

Console.WriteLine("\nPDF file converted to PDF/A-1b compliant PDF.\nFile saved at " + dataDir);
```

## 结论
在本教程中，我们介绍了使用 Aspose.PDF for .NET 将 PDF 文件转换为 PDF/A 格式的分步过程。按照上述说明，您现在应该能够将 PDF 文件转换为 PDF/A 格式。当您要确保电子文档的长期合规性时，此功能很有用。