---
title: PDF 到 XPS
linktitle: PDF 到 XPS
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 将 PDF 转换为 XPS 的分步指南。
type: docs
weight: 220
url: /zh/net/document-conversion/pdf-to-xps/
---

在本教程中，我们将引导您完成使用 Aspose.PDF for .NET 将 PDF 文件转换为 XPS（XML 纸张规范）格式的过程。 XPS 格式是一种基于 XML 的文件格式，用于以电子方式表示文档。按照以下步骤，您将能够将 PDF 文件转换为 XPS 格式。

## 先决条件
在开始之前，请确保满足以下先决条件：

- C# 编程语言的基础知识。
- .NET 的 Aspose.PDF 库安装在您的系统上。
- 开发环境，例如 Visual Studio。

## 第 1 步：加载 PDF 文档
在此步骤中，我们将使用 Aspose.PDF for .NET 加载源 PDF 文件。请遵循以下代码：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//加载 PDF 文档
Document pdfDocument = new Document(dataDir + "input.pdf");
```

务必更换`"YOUR DOCUMENTS DIRECTORY"`使用您的 PDF 文件所在的实际目录。

## 第 2 步：实例化 XPS 保存选项
加载 PDF 文件后，我们将实例化 XPS 保存选项。使用以下代码：

```csharp
//实例化 XPS 保存选项
Aspose.Pdf.XpsSaveOptions saveOptions = new Aspose.Pdf.XpsSaveOptions();
```

## 第 3 步：保存生成的 XPS 文件
现在我们将转换后的 PDF 文件保存为 XPS 格式。使用以下代码：

```csharp
//保存 XPS 文档
pdfDocument.Save("PDFToXPS_out.xps", saveOptions);
```

上面的代码将转换后的 PDF 文件保存为 XPS 格式，文件名`"PDFToXPS_out.xps"`.


### 使用 Aspose.PDF for .NET 将 PDF 转换为 XPS 的示例源代码

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//载入PDF文件
Document pdfDocument = new Document(dataDir + "input.pdf");

//实例化 XPS 保存选项
Aspose.Pdf.XpsSaveOptions saveOptions = new Aspose.Pdf.XpsSaveOptions();

//保存 XPS 文档
pdfDocument.Save("PDFToXPS_out.xps", saveOptions);
```

## 结论
在本教程中，我们介绍了使用 Aspose.PDF for .NET 将 PDF 文件转换为 XPS 格式的分步过程。按照上述说明，您现在应该能够将 PDF 文件转换为 XPS 格式。当您要查看或打印 XPS 格式的 PDF 文档时，此功能很有用。