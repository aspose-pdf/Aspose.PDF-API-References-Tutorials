---
title: PDF 后记
linktitle: PDF 后记
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 将 PostScript 转换为 PDF 的分步指南。
type: docs
weight: 230
url: /zh/net/document-conversion/postscript-to-pdf/
---

在本教程中，我们将引导您完成使用 Aspose.PDF for .NET 将 PostScript (PS) 文件转换为 PDF 格式的过程。 PostScript 格式是一种页面描述语言，用于描述文档的图形外观。按照以下步骤，您将能够将 PostScript 文件转换为 PDF 格式。

## 先决条件
在开始之前，请确保满足以下先决条件：

- C# 编程语言的基础知识。
- .NET 的 Aspose.PDF 库安装在您的系统上。
- 开发环境，例如 Visual Studio。

## 第 1 步：加载 PostScript 文档
在此步骤中，我们将使用 Aspose.PDF for .NET 加载源 PostScript 文件。请遵循以下代码：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//创建 PsLoadOptions 的新实例
LoadOptions options = new PsLoadOptions();

//使用创建的加载选项打开 .ps 文件
Document pdfDocument = new Document(dataDir + "input.ps", options);
```

务必更换`"YOUR DOCUMENTS DIRECTORY"`使用 PostScript 文件所在的实际目录。

## 第 2 步：保存生成的 PDF 文件
最后，我们将转换后的 PostScript 文件保存为 PDF。使用以下代码：

```csharp
//保存文件
pdfDocument.Save(dataDir + "PSToPDF.pdf");
```

上面的代码将转换后的 PostScript 文件保存为 PDF 格式，文件名`"PSToPDF.pdf"`.

### 使用 Aspose.PDF for .NET 的 Postscript to PDF 示例源代码

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//创建 PsLoadOptions 的新实例
LoadOptions options = new PsLoadOptions();
//使用创建的加载选项打开 .ps 文档
Document pdfDocument = new Document(dataDir + "input.ps", options);
//保存文档
pdfDocument.Save(dataDir + "PSToPDF.pdf");
```

## 结论
在本教程中，我们介绍了使用 Aspose.PDF for .NET 将 PostScript 文件转换为 PDF 格式的分步过程。按照上述说明，您现在应该能够将 PostScript 文件转换为 PDF 格式。当您想要将 PostScript 文件转换为 PDF 格式以便更常用和更好的兼容性时，此功能很有用。