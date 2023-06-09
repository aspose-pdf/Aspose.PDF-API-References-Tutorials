---
title: PDF转DOC
linktitle: PDF转DOC
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 将 PDF 转换为 DOC 的分步指南。
type: docs
weight: 110
url: /zh/net/document-conversion/pdf-to-doc/
---

在本教程中，我们将指导您使用 Aspose.PDF for .NET 将 PDF 文件转换为 DOC 格式。 PDF 文件通常用于普遍查看和共享文档，而 DOC 格式特定于 Microsoft Word。按照以下步骤，您将能够将 PDF 文件转换为 DOC 格式。

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
Document pdfDocument = new Document(dataDir + "PDFToDOC.pdf");
```

务必更换`"YOUR DOCUMENTS DIRECTORY"`使用您的 PDF 文件所在的实际目录。

## 第 2 步：将 PDF 转换为 DOC 格式
打开PDF文件后，我们就可以进行DOC格式的转换了。使用以下代码：

```csharp
//以 MS 文档格式保存文件
pdfDocument.Save(dataDir + "PDFToDOC_out.doc", SaveFormat.Doc);
```

上面的代码将PDF文件转换为DOC格式并保存为文件名`"PDFToDOC_out.doc"`.

代替`"YOUR DOCUMENTS DIRECTORY"`使用要保存输出 DOC 文件的所需目录。

### 使用 Aspose.PDF for .NET 的 PDF 到 DOC 的示例源代码

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";          

//打开源 PDF 文档
Document pdfDocument = new Document(dataDir + "PDFToDOC.pdf");

//将文件保存为 MS 文档格式
pdfDocument.Save(dataDir + "PDFToDOC_out.doc", SaveFormat.Doc);
```

## 结论
在本教程中，我们介绍了使用 Aspose.PDF for .NET 将 PDF 文件转换为 DOC 格式的分步过程。按照上述说明，您现在应该能够将 PDF 文件转换为 DOC 格式。当您需要在 Microsoft Word 或其他支持 DOC 格式的应用程序中处理 PDF 文件时，此功能非常有用。