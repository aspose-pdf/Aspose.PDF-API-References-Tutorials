---
title: PDF 转 PDFA3b
linktitle: PDF 转 PDFA3b
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 将 PDF 转换为 PDF/A-3b 的分步指南。
type: docs
weight: 150
url: /zh/net/document-conversion/pdf-to-pdfa3b/
---

在本教程中，我们将引导您完成使用 Aspose.PDF for .NET 将 PDF 文件转换为 PDF/A-3b 格式的过程。 PDF/A-3b 是用于在 PDF 文档中嵌入文件和数据的 ISO 标准。按照以下步骤，您将能够将 PDF 文件转换为 PDF/A-3b 格式。

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
Document pdfDocument = new Document(dataDir + "input.pdf");
```

务必更换`"YOUR DOCUMENTS DIRECTORY"`使用您的 PDF 文件所在的实际目录。

## 第 2 步：转换为 PDF/A-3b
打开 PDF 文件后，我们可以继续转换为 PDF/A-3b 格式。使用以下代码：

```csharp
//转换为 PDF/A-3b 格式
pdfDocument.Convert(new MemoryStream(), PdfFormat.PDF_A_3B, ConvertErrorAction.Delete);
```

上面的代码将 PDF 文件转换为 PDF/A-3b 格式并消除了任何转换错误。

## 第 3 步：保存生成的 PDF/A-3b 文件
转换完成后，我们需要保存生成的PDF/A-3b文件。这是最后一步：

```csharp
dataDir = dataDir + "PDFToPDFA3b_out.pdf";
//保存输出文件
pdfDocument.Save(dataDir);
```

代替`"YOUR DOCUMENTS DIRECTORY"`使用要保存输出 PDF/A-3b 文件的所需目录。

### 使用 Aspose.PDF for .NET 将 PDF 转换为 PDFA3b 的示例源代码

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//打开文档
Document pdfDocument = new Document(dataDir + "input.pdf");            

pdfDocument.Convert(new MemoryStream(), PdfFormat.PDF_A_3B, ConvertErrorAction.Delete);

dataDir = dataDir + "PDFToPDFA3b_out.pdf";
//保存输出文件
pdfDocument.Save(dataDir);

Console.WriteLine("\nPDF file converted to PDF/A-3B format.\nFile saved at " + dataDir);
```

## 结论
在本教程中，我们介绍了使用 Aspose.PDF for .NET 将 PDF 文件转换为 PDF/A-3b 格式的分步过程。按照上述说明，您现在应该能够将 PDF 文件转换为 PDF/A-3b 格式。当您想要将附加文件和数据嵌入到符合 PDF/A-3b 标准的 PDF 文档时，此功能很有用。