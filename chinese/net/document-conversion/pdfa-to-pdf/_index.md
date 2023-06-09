---
title: PDFA 到 PDF
linktitle: PDFA 到 PDF
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 将 PDFA 转换为 PDF 的分步指南。
type: docs
weight: 100
url: /zh/net/document-conversion/pdfa-to-pdf/
---

在本教程中，我们将引导您完成使用 Aspose.PDF for .NET 将 PDFA (PDF/A) 文件转换为标准 PDF 格式的过程。 PDFA 格式是 PDF 格式的特定版本，用于保证文档的长期归档。按照以下步骤，您将能够将 PDFA 文件转换为 PDF 格式。

## 先决条件
在开始之前，请确保满足以下先决条件：

- C# 编程语言的基础知识。
- .NET 的 Aspose.PDF 库安装在您的系统上。
- 开发环境，例如 Visual Studio。

## 第 1 步：加载 PDFA 文档
在此步骤中，我们将使用 Aspose.PDF for .NET 加载源 PDFA 文件。请遵循以下代码：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//加载 PDFA 文档
Document doc = new Document(dataDir + "PDFAToPDF.pdf");
```

务必更换`"YOUR DOCUMENTS DIRECTORY"`使用您的 PDFA 文件所在的实际目录。

## 第 2 步：删除 PDF/A 合规信息
现在我们要从文档中删除 PDF/A 合规性信息。使用以下代码：

```csharp
//删除 PDF/A 合规信息
doc.RemovePdfaCompliance();
```

## 第 3 步：保存生成的 PDF 文件
最后，我们将转换后的 PDFA 文件保存为 PDF 格式。使用以下代码：

```csharp
//以 PDF 格式保存更新的文档
doc.Save(dataDir + "PDFAToPDF_out.pdf");
```

上面的代码将转换后的 PDFA 文件保存为 PDF 格式，文件名`"PDFAToPDF_out.pdf"`.

### 使用 Aspose.PDF for .NET 的 PDFA 到 PDF 的示例源代码


```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//打开文档
Document doc = new Document(dataDir + "PDFAToPDF.pdf");

//删除 PDF/A 合规信息
doc.RemovePdfaCompliance();
//保存更新的文档
doc.Save(dataDir + "PDFAToPDF_out.pdf");
```

## 结论
在本教程中，我们介绍了使用 Aspose.PDF for .NET 将 PDFA 文件转换为 PDF 格式的分步过程。按照上述说明，您现在应该能够将 PDFA 文件转换为标准 PDF 格式。当您想要从文档中删除 PDF/A 合规性限制以便更灵活地使用时，此功能很有用。