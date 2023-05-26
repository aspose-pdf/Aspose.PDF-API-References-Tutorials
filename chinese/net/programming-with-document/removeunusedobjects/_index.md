---
title: 删除未使用的对象
linktitle: 删除未使用的对象
second_title: Aspose.PDF for .NET API 参考
description: 通过此分步指南，了解如何使用 Aspose.PDF for .NET 从 PDF 文档中删除未使用的对象。
type: docs
weight: 260
url: /zh/net/programming-with-document/removeunusedobjects/
---
如果您正在寻找一种使用 Aspose.PDF for .NET 删除 PDF 文档中未使用的对象的方法，那么您来对地方了。本分步指南将向您展示如何使用提供的 C# 源代码来完成此任务。

## 第一步：设置目录路径

首先，您需要通过将“您的文档目录”替换为适当的路径来设置文档目录的路径。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：打开 PDF 文档

接下来，您需要使用以下代码打开要优化的 PDF 文档：

```csharp
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## 第 3 步：设置 RemoveUnusedObjects 选项

要删除 PDF 文档中未使用的对象，您需要将 RemoveUnusedObjects 选项设置为“true”，如下所示：

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	RemoveUnusedObjects = true
};
```

## 第 4 步：使用 OptimizationOptions 优化 PDF 文档

现在，您可以使用 OptimizeResources 方法和刚刚设置的优化选项来优化您的 PDF 文档：

```csharp
pdfDocument.OptimizeResources(optimizeOptions);
```

## 第 5 步：保存更新后的文档

最后，您可以使用以下代码保存更新的文档：

```csharp
dataDir = dataDir + "OptimizeDocument_out.pdf";
pdfDocument.Save(dataDir);
```

就是这样！您已经使用 Aspose.PDF for .NET 成功地从 PDF 文档中删除了未使用的对象。

### 使用 Aspose.PDF for .NET 删除未使用对象的示例源代码：

```csharp

	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	//打开文档
	Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
	//设置 RemoveUsedObject 选项
	var optimizeOptions = new Pdf.Optimization.OptimizationOptions
	{
		RemoveUnusedObjects = true
	};
	//使用 OptimizationOptions 优化 PDF 文档
	pdfDocument.OptimizeResources(optimizeOptions);
	dataDir = dataDir + "OptimizeDocument_out.pdf";
	//保存更新的文档
	pdfDocument.Save(dataDir);

```
