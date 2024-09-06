---
title: 删除 PDF 文件中未使用的流
linktitle: 删除 PDF 文件中未使用的流
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 删除 PDF 文件中未使用的流。我们的分步指南。
type: docs
weight: 270
url: /zh/net/programming-with-document/removeunusedstreams/
---
在此示例中，我们将讨论如何使用 Aspose.PDF for .NET 删除 PDF 文件中未使用的流。我们将提供有关如何执行此操作的分步指南，包括带有说明的完整源代码。

## 步骤 1：文档目录的路径

代码的第一行设置了 PDF 文档所在目录的路径。请确保将“您的文档目录”替换为实际目录路径。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：打开文档

下一行代码使用 Aspose.PDF for .NET 库打开 PDF 文档。

```csharp
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## 步骤 3：设置 RemoveUnusedStreams 选项

下一步是将 RemoveUnusedStreams 选项设置为 true。这将从 PDF 文档中删除所有未使用的流。

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	RemoveUnusedStreams = true
};
```

## 步骤 4：使用 OptimizationOptions 优化 PDF 文档

现在我们已经设置了优化选项，我们可以使用下面一行代码来优化 PDF 文档。

```csharp
pdfDocument.OptimizeResources(optimizeOptions);
```

## 步骤 5：保存更新后的文档

最后，我们可以使用 Document 类的 Save 方法保存更新的文档。

```csharp
dataDir = dataDir + "OptimizeDocument_out.pdf";
pdfDocument.Save(dataDir);
```

### 使用 Aspose.PDF for .NET 删除未使用的流的示例源代码

以下是使用 Aspose.PDF for .NET 删除未使用流的示例源代码。

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

## 结论

通过删除未使用的流来优化 PDF 文档对于提高性能和减小文件大小至关重要。Aspose.PDF for .NET 通过提供一种方便的方法来删除未使用的流，从而简化了此过程，方法是使用`OptimizationOptions`。分步指南和提供的 C# 源代码使开发人员可以轻松地在其 .NET 应用程序中实现此功能。通过遵循这些说明，开发人员可以有效地优化他们的 PDF 文件并改善其 .NET 项目中的整体 PDF 处理。

### 关于删除 PDF 文件中未使用的流的常见问题解答

#### 问：PDF 文档中未使用的流是什么？

答：PDF 文档中未使用的流是文档内容中未引用或使用的文件部分。这些流可能包括不再需要但仍存在于 PDF 文件中的图像、字体或其他资源。

#### 问：删除未使用的流对 PDF 文档有何好处？

答：从 PDF 文档中删除未使用的流可减小其文件大小，从而缩短加载时间并提高性能。它有助于优化 PDF 文件，从而提供更好的用户体验和高效的存储。

#### 问：开发人员可以指定使用 Aspose.PDF for .NET 要删除哪些流吗？

答：是的，开发人员可以通过设置`RemoveUnusedStreams`选项中的`OptimizationOptions`。这样他们就可以根据自己的特定需求灵活地选择要删除哪些流。