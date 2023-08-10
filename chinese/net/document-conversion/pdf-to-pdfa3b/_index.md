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
- 您的系统上安装了适用于 .NET 的 Aspose.PDF 库。
- 开发环境，例如 Visual Studio。

## 第 1 步：打开源 PDF 文档
在此步骤中，我们将使用 Aspose.PDF for .NET 打开源 PDF 文件。请按照以下代码操作：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//打开源PDF文档
Document pdfDocument = new Document(dataDir + "input.pdf");
```

一定要更换`"YOUR DOCUMENTS DIRECTORY"`与您的 PDF 文件所在的实际目录。

## 第 2 步：转换为 PDF/A-3b
打开PDF文件后，我们可以继续转换为PDF/A-3b格式。使用以下代码：

```csharp
//转换为 PDF/A-3b 格式
pdfDocument.Convert(new MemoryStream(), PdfFormat.PDF_A_3B, ConvertErrorAction.Delete);
```

上面的代码将 PDF 文件转换为 PDF/A-3b 格式并消除任何转换错误。

## 步骤 3：保存生成的 PDF/A-3b 文件
转换完成后，我们需要保存生成的PDF/A-3b文件。这是最后一步：

```csharp
dataDir = dataDir + "PDFToPDFA3b_out.pdf";
//保存输出文档
pdfDocument.Save(dataDir);
```

代替`"YOUR DOCUMENTS DIRECTORY"`以及要保存输出 PDF/A-3b 文件的所需目录。

### 使用 Aspose.PDF for .NET 将 PDF 转换为 PDFA3b 的示例源代码

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//打开文档
Document pdfDocument = new Document(dataDir + "input.pdf");            

pdfDocument.Convert(new MemoryStream(), PdfFormat.PDF_A_3B, ConvertErrorAction.Delete);

dataDir = dataDir + "PDFToPDFA3b_out.pdf";
//保存输出文档
pdfDocument.Save(dataDir);

Console.WriteLine("\nPDF file converted to PDF/A-3B format.\nFile saved at " + dataDir);
```

## 结论
在本教程中，我们介绍了使用 Aspose.PDF for .NET 将 PDF 文件转换为 PDF/A-3b 格式的分步过程。按照上述说明操作，您现在应该能够将 PDF 文件转换为 PDF/A-3b 格式。当您想要将其他文件和数据嵌入到符合 PDF/A-3b 标准的 PDF 文档中时，此功能非常有用。

### 常见问题解答

#### 问：什么是 PDF/A-3b，它与其他 PDF/A 标准有何不同？

答：PDF/A-3b 是一项 ISO 标准，允许将文件和数据嵌入到 PDF 文档中，使其独立并确保长期保存。与其他 PDF/A 标准（例如 PDF/A-1 和 PDF/A-2）不同，PDF/A-3b 允许在 PDF 文档中包含其他文件和数据。此功能使其适合归档和交换复杂的交互式文档。

#### 问：我可以在 PDF/A-3b 文档中包含多个文件和数据吗？

答：是的，PDF/A-3b 的主要优点之一是它能够在 PDF 文档中包含多个文件和数据。您可以嵌入各种类型的文件，例如 XML、电子表格、图像或其他 PDF 文件以及主要 PDF 内容。因此，PDF/A-3b 文档成为包含所有必要元素的独立包。

#### 问：如果 PDF 到 PDF/A-3b 转换过程中出现错误，会发生什么情况？

答：使用 Aspose.PDF for .NET 将 PDF 转换为 PDF/A-3b 格式时，您可以控制错误的处理方式。这`Convert`方法`ConvertErrorAction`参数决定遇到错误时要采取的操作。在提供的代码示例中，`ConvertErrorAction.Delete`使用参数，这意味着转换过程中遇到任何错误都会导致删除有错误的页面。

#### 问：PDF/A-3b 适合长期保存文档吗？

答：是的，PDF/A-3b 是专门为长期保存电子文档而设计的。通过嵌入额外的文件和数据，它可以确保所有必要的组件都包含在 PDF 文档本身中，从而降低随着时间的推移信息丢失或外部依赖性的风险。此功能使其适合以保证长期可访问性和一致性的方式归档文档。