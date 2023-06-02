---
title: 删除未使用的流
linktitle: 删除未使用的流
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 从 PDF 文件中删除未使用的流。我们的分步指南。
type: docs
weight: 270
url: /zh/net/programming-with-document/removeunusedstreams/
---
在本例中，我们将讨论如何使用 Aspose.PDF for .NET 从 PDF 文档中删除未使用的流。我们将提供有关如何执行此操作的分步指南，包括带有解释的完整源代码。

## 第一步：文档目录路径

代码的第一行设置 PDF 文档所在目录的路径。确保用实际目录路径替换“您的文档目录”。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：打开文档

下一行代码使用 Aspose.PDF for .NET 库打开 PDF 文档。

```csharp
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## 第 3 步：设置 RemoveUnusedStreams 选项

下一步是将 RemoveUnusedStreams 选项设置为 true。这将从 PDF 文档中删除任何未使用的流。

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	RemoveUnusedStreams = true
};
```

## 第 4 步：使用 OptimizationOptions 优化 PDF 文档

现在我们已经设置了优化选项，我们可以使用以下代码行优化 PDF 文档。

```csharp
pdfDocument.OptimizeResources(optimizeOptions);
```

## 第 5 步：保存更新的文档

最后，我们可以使用 Document 类的 Save 方法保存更新后的文档。

```csharp
dataDir = dataDir + "OptimizeDocument_out.pdf";
pdfDocument.Save(dataDir);
```

### 使用 Aspose.PDF for .NET 删除未使用的流的示例源代码

下面是使用 Aspose.PDF for .NET 删除未使用流的示例源代码。

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//打开文档
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
//设置 RemoveUsedStreams 选项
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	RemoveUnusedStreams = true
};
//使用 OptimizationOptions 优化 PDF 文档
pdfDocument.OptimizeResources(optimizeOptions);
dataDir = dataDir + "OptimizeDocument_out.pdf";
//保存更新的文档
pdfDocument.Save(dataDir);
```
