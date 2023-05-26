---
title: 链接重复流
linktitle: 链接重复流
second_title: Aspose.PDF for .NET API 参考
description: 通过此分步指南了解如何使用 Aspose.PDF for .NET Link Duplicate Streams 功能来优化您的 PDF 文档。
type: docs
weight: 230
url: /zh/net/programming-with-document/linkduplicatestreams/
---
Aspose.PDF for .NET 是一个全面而强大的库，它提供了处理 PDF 文件的各种功能。它的主要功能之一是能够优化 PDF 文件。在本文中，我们将解释如何使用 Aspose.PDF for .NET 的 Link Duplicate Streams 功能来优化 PDF 文件。我们将提供分步说明并包含完整的源代码示例，以便开发人员可以轻松跟进。

## 步骤 1：打开 PDF 文档

要使用 Aspose.PDF for .NET 打开 PDF 文档，请执行以下步骤：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//打开文档
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

在上面的代码中，将“您的文档目录”替换为您的项目目录的路径。

## 第 2 步：设置 LinkDuplicateStreams 选项

要设置 LinkDuplicateStreams 选项，请执行以下步骤：

```csharp
//设置 LinkDuplcateStreams 选项
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
    LinkDuplcateStreams = true
};
```

在上面的代码中，我们创建了一个新的 OptimizationOptions 实例并将 LinkDuplicateStreams 选项设置为 true。

## 第 3 步：优化 PDF 文档

要优化 PDF 文档，请执行以下步骤：

```csharp
//使用 OptimizationOptions 优化 PDF 文档
pdfDocument.OptimizeResources(optimizeOptions);
```

在上面的代码中，我们使用了 pdfDocument 对象的 OptimizeResources 方法，使用我们之前创建的 OptimizationOptions 来优化 PDF 文档。

## 第 4 步：保存更新的文档

要保存更新的文档，请执行以下步骤：

```csharp
dataDir = dataDir + "OptimizeDocument_out.pdf";
//保存更新的文档
pdfDocument.Save(dataDir);
```

在上面的代码中，我们使用 pdfDocument 对象的 Save 方法将更新的文档保存到项目目录中名为“OptimizeDocument_out.pdf”的新文件中。

### 使用 Aspose.PDF for .NET 链接重复流的示例源代码

```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	//打开文档
	Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
	//设置 LinkDuplcateStreams 选项
	var optimizeOptions = new Pdf.Optimization.OptimizationOptions
	{
		LinkDuplcateStreams = true
	};
	//使用 OptimizationOptions 优化 PDF 文档
	pdfDocument.OptimizeResources(optimizeOptions);
	dataDir = dataDir + "OptimizeDocument_out.pdf";
	//保存更新的文档
	pdfDocument.Save(dataDir);
	
```
