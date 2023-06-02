---
title: 设置默认字体
linktitle: 设置默认字体
second_title: Aspose.PDF for .NET API 参考
description: 通过此分步指南了解如何使用 Aspose.PDF for .NET 为 PDF 文档设置默认字体。
type: docs
weight: 280
url: /zh/net/programming-with-document/setdefaultfont/
---
如果您在 .NET 中处理 PDF 文档，您可能会遇到 PDF 中使用的字体在查看或打印它的系统上不可用的问题。这可能导致文本显示不正确或根本不显示。 Aspose.PDF for .NET 通过允许您为文档设置默认字体来解决此问题。在此示例中，如何使用 Aspose.PDF for .NET 设置默认字体。

## 第一步：设置文档目录路径

我们需要将路径设置为我们的 PDF 文档所在的目录。我们将把这个路径存储在一个名为“dataDir”的变量中。

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：加载 PDF 文档

我们将从加载缺少字体的现有 PDF 文档开始。在此示例中，我们假设 PDF 文档位于由`dataDir`多变的。

```csharp
string documentName = dataDir + "input.pdf";
using (System.IO.FileStream fs = new System.IO.FileStream(documentName, System.IO.FileMode.Open))
using (Document document = new Document(fs))
{
    //代码在这里
}
```

## 第三步：设置默认字体

接下来，我们将使用`PdfSaveOptions`班级。在此示例中，我们将默认字体设置为“Arial”。

```csharp
PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
pdfSaveOptions.DefaultFontName = "Arial";
```

## 第 4 步：保存更新后的文档

最后，我们将更新后的文档保存到一个新文件中。在此示例中，我们将更新后的文档保存到与输入文件位于同一目录中的名为“output_out.pdf”的文件中。

```csharp
document.Save(dataDir + "output_out.pdf", pdfSaveOptions);
```

### 使用 Aspose.PDF for .NET 设置默认字体的示例源代码

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//加载缺少字体的现有 PDF 文档
string documentName = dataDir + "input.pdf";
string newName = "Arial";
using (System.IO.FileStream fs = new System.IO.FileStream(documentName, System.IO.FileMode.Open))
using (Document document = new Document(fs))
{
	PdfSaveOptions pdfSaveOptions = new PdfSaveOptions();
	//指定默认字体名称
	pdfSaveOptions.DefaultFontName = newName;
	document.Save(dataDir + "output_out.pdf", pdfSaveOptions);
}
```
