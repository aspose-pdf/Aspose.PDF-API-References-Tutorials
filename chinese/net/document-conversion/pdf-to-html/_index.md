---
title: PDF 到 HTML
linktitle: PDF 到 HTML
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 将 PDF 转换为 HTML 的分步指南。
type: docs
weight: 130
url: /zh/net/document-conversion/pdf-to-html/
---

在本教程中，我们将引导您完成使用 Aspose.PDF for .NET 将 PDF 文件转换为 HTML 格式的过程。 PDF 格式通常用于查看和共享文档，而 HTML 格式用于创建网页。按照以下步骤，您将能够将 PDF 文件转换为 HTML 格式。

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
Document pdfDocument = new Document(dataDir + "PDFToHTML.pdf");
```

务必更换`"YOUR DOCUMENTS DIRECTORY"`使用您的 PDF 文件所在的实际目录。

## 第 2 步：PDF 到 HTML 转换
打开 PDF 文件后，我们可以继续转换为 HTML 格式。使用以下代码：

```csharp
//以 HTML 格式保存文件
pdfDocument.Save(dataDir + "output_out.html", SaveFormat.Html);
```

上面的代码将PDF文件转换为HTML格式并保存为`"output_out.html"`文件。

代替`"YOUR DOCUMENTS DIRECTORY"`使用要保存输出 HTML 文件的所需目录。

### 使用 Aspose.PDF for .NET 将 PDF 转换为 HTML 的示例源代码

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//打开源 PDF 文档
Document pdfDocument = new Document(dataDir + "PDFToHTML.pdf");

//将文件保存为 MS 文档格式
pdfDocument.Save(dataDir + "output_out.html", SaveFormat.Html);
```

## 结论
在本教程中，我们介绍了使用 Aspose.PDF for .NET 将 PDF 文件转换为 HTML 格式的分步过程。按照上述说明，您现在应该能够将 PDF 文件转换为 HTML 格式。当您想将 PDF 内容嵌入网页或其他支持 HTML 格式的应用程序时，此功能很有用。

