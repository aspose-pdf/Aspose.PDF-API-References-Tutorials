---
title: 创建文档时嵌入字体
linktitle: 创建文档时嵌入字体
second_title: Aspose.PDF for .NET API 参考
description: 了解如何在使用 Aspose.PDF for .NET 创建 PDF 文档时嵌入字体。确保在不同设备上正确显示。
type: docs
weight: 140
url: /zh/net/programming-with-document/embedfontwhiledoccreation/
---

在本教程中，我们将讨论如何在使用 Aspose.PDF for .NET 创建 PDF 文档时嵌入字体。 Aspose.PDF for .NET 是一个功能强大的库，允许开发人员以编程方式创建、编辑和操作 PDF 文档。这个库提供了广泛的功能来处理 PDF 文档，包括添加文本、图像、表格等等。在创建 PDF 文档时嵌入字体是开发人员的常见要求，他们希望确保 PDF 文档在不同设备上正确显示，而不管这些设备上是否安装了所需的字体。

## 第 1 步：创建一个新的 C# 控制台应用程序
首先，在 Visual Studio 中创建一个新的 C# 控制台应用程序。您可以随意命名。创建项目后，您需要添加对 Aspose.PDF for .NET 库的引用。

## 第 2 步：导入 Aspose.PDF 命名空间
在 C# 文件的顶部添加以下代码行以导入 Aspose.PDF 命名空间：

```csharp
using Aspose.Pdf;
```

## 第 3 步：实例化一个 Pdf 对象
通过调用其空构造函数来实例化 Pdf 对象：

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

## 第 4 步：在 Pdf 对象中创建一个部分
在 Pdf 对象中创建一个部分：

```csharp
Aspose.Pdf.Page page = doc.Pages.Add();
```

## 第 5 步：向部分添加文本
向该部分添加文本：

```csharp
Aspose.Pdf.Text.TextFragment fragment = new Aspose.Pdf.Text.TextFragment("");
Aspose.Pdf.Text.TextSegment segment = new Aspose.Pdf.Text.TextSegment(" This is a sample text using Custom font.");
```

## 第 6 步：设置字体并嵌入
设置字体并嵌入：

```csharp
Aspose.Pdf.Text.TextState ts = new Aspose.Pdf.Text.TextState();
ts.Font = FontRepository.FindFont("Arial");
ts.Font.IsEmbedded = true;
segment.TextState = ts;
fragment.Segments.Add(segment);
page.Paragraphs.Add(fragment);
```

## 步骤 7：保存 PDF 文档
在创建 PDF 文档时嵌入字体后，您需要保存文档：

```csharp
dataDir = dataDir + "EmbedFontWhileDocCreation_out.pdf";
//保存 PDF 文档
doc.Save(dataDir);
```

### 使用 Aspose.PDF for .NET 创建文档时嵌入字体的示例源代码

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//通过调用其空构造函数来实例化 Pdf 对象
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

//在 Pdf 对象中创建一个部分
Aspose.Pdf.Page page = doc.Pages.Add();

Aspose.Pdf.Text.TextFragment fragment = new Aspose.Pdf.Text.TextFragment("");

Aspose.Pdf.Text.TextSegment segment = new Aspose.Pdf.Text.TextSegment(" This is a sample text using Custom font.");
Aspose.Pdf.Text.TextState ts = new Aspose.Pdf.Text.TextState();
ts.Font = FontRepository.FindFont("Arial");
ts.Font.IsEmbedded = true;
segment.TextState = ts;
fragment.Segments.Add(segment);
page.Paragraphs.Add(fragment);

dataDir = dataDir + "EmbedFontWhileDocCreation_out.pdf";
//保存 PDF 文档
doc.Save(dataDir);
```

## 结论
在本教程中，我们讨论了如何在使用 Aspose.PDF for .NET 创建 PDF 文档时嵌入字体。 Aspose.PDF for .NET 提供了一个简单易用的 API 来处理 PDF 文档，包括添加和嵌入字体。在创建 PDF 文档时嵌入字体是确保文档在不同设备上正确显示的重要步骤，无论这些设备上是否安装了所需的字体。

