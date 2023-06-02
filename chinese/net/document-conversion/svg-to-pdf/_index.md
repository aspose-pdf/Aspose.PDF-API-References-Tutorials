---
title: SVG 转 PDF
linktitle: SVG 转 PDF
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 轻松快速地将 SVG 转换为 PDF。
type: docs
weight: 280
url: /zh/net/document-conversion/svg-to-pdf/
---

本教程将引导您完成使用 Aspose.PDF for .NET 将 SVG 文件转换为 PDF 文件的步骤。 Aspose.PDF 提供了一种简单有效的解决方案，可将 SVG 文件转换为 PDF，同时保持内容质量和布局。请按照以下步骤执行此转换。

## 先决条件
在开始之前，请确保满足以下先决条件：

- C# 编程语言的基础知识。
- .NET 的 Aspose.PDF 库安装在您的系统上。
- 开发环境，例如 Visual Studio。

## 第 1 步：加载 SVG 文件
第一步是将 SVG 文件加载到`Document`使用 SVG 加载选项的对象 (`SvgLoadOptions`).使用以下代码：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//使用 SVG 加载选项实例化 LoadOption 对象
Aspose.Pdf.LoadOptions loadopt = new Aspose.Pdf.SvgLoadOptions();

//创建文档对象
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "SVGToPDF.svg", loadopt);
```

务必更换`"YOUR DOCUMENTS DIRECTORY"`使用您的 SVG 文件所在的实际目录。

## 第 2 步：转换为 PDF
第二步是将 SVG 文档转换为 PDF 文档，使用`Save`的方法`Document`目的。使用以下代码：

```csharp
//保存生成的 PDF 文档
doc.Save(dataDir + "SVGToPDF_out.pdf");
```

请务必为生成的 PDF 文件指定所需的路径和文件名。

### 使用 Aspose.Words for .NET 将 SVG 转换为 PDF 的示例源代码

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//使用 SVG 加载选项实例化 LoadOption 对象
Aspose.Pdf.LoadOptions loadopt = new Aspose.Pdf.SvgLoadOptions();

//创建文档对象
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "SVGToPDF.svg", loadopt);

//保存生成的 PDF 文档
doc.Save(dataDir + "SVGToPDF_out.pdf");
```

## 结论
在本教程中，我们学习了如何使用 Aspose.PDF for .NET 将 SVG 文件转换为 PDF 文件。按照上面给出的步骤，您可以轻松地执行此转换。使用此方法将您的 SVG 文件转换为 PDF，并享受 Aspose.PDF 的灵活性和质量。