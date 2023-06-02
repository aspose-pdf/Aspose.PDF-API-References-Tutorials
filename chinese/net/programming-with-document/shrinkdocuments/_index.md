---
title: 收缩文件
linktitle: 收缩文件
second_title: Aspose.PDF for .NET API 参考
description: 通过此分步指南了解如何使用 Aspose.PDF for .NET 来缩小 PDF 文档。
type: docs
weight: 350
url: /zh/net/programming-with-document/shrinkdocuments/
---
Aspose.PDF for .NET 是一个功能强大的库，它使开发人员能够使用 C# 创建、操作和优化 PDF 文档。在本教程中，我们将通过一个示例介绍如何使用 Aspose.PDF 来缩小 PDF 文档。

## 第 1 步：加载 PDF 文档

要缩小 PDF 文档，我们首先需要使用 Aspose.PDF 将其加载到我们的 C# 应用程序中。在下面的代码中，我们指定了 PDF 文档的路径并创建了一个新的实例`Document`班级。

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//打开文档
Document pdfDocument = new Document(dataDir + "ShrinkDocument.pdf");
```

## 第 2 步：缩小 PDF 文档

一旦我们加载了 PDF 文档，我们就可以使用`OptimizeResources`的方法`Document`类来优化文档并可能缩小其大小。请注意，此方法不能保证文档缩小，因为某些 PDF 文档可能已经高度优化。

```csharp
//优化PDF文档。但请注意，此方法不能保证文档缩小
pdfDocument.OptimizeResources();
```

## 第 3 步：保存更新后的 PDF 文档

优化 PDF 文档后，我们可以使用`Save`的方法`Document`班级。在下面的代码中，我们指定输出文件的路径和文件名。

```csharp
//指定输出文件路径
string outputFilePath = dataDir + "ShrinkDocument_out.pdf";
//保存更新的文档
pdfDocument.Save(outputFilePath);
```

### 使用 Aspose.PDF for .NET 收缩文档的示例源代码

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//打开文档
Document pdfDocument = new Document(dataDir + "ShrinkDocument.pdf");
//优化PDF文档。但请注意，此方法不能保证文档缩小
pdfDocument.OptimizeResources();
dataDir = dataDir + "ShrinkDocument_out.pdf";
//保存更新的文档
pdfDocument.Save(dataDir);
```
