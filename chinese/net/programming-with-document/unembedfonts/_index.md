---
title: 取消嵌入字体
linktitle: 取消嵌入字体
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 获取 Unembed Fonts 和优化 PDF 文件。分步指南。
type: docs
weight: 370
url: /zh/net/programming-with-document/unembedfonts/
---
Aspose.PDF for .NET 是一个功能强大的库，它提供了广泛的功能来处理 PDF 文档。它的功能之一是从 PDF 文档中获取未嵌入的字体。如果您需要从 PDF 文档中提取字体并在其他应用程序中使用它们，这将很有用。

我们将提供一个分步指南来解释以下 Aspose.PDF for .NET 的获取未嵌入字体功能的 C# 源代码。

## 第一步：设置文档目录路径

在我们开始之前，我们需要将路径设置为我们的 PDF 文档所在的目录。我们将把这个路径存储在一个名为“dataDir”的变量中。

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

将“您的文档目录”替换为您的 PDF 文档所在目录的实际路径。

## 第 2 步：打开 PDF 文档

第一步是加载您要执行此操作的 PDF 文档，使用`Document`.NET 的 Aspose.PDF 类。以下代码片段显示了如何加载 PDF 文档：

```csharp
//打开文档
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## 第 3 步：设置 UnembedFonts 选项

要从 PDF 文档中获取未嵌入的字体，您需要设置`UnembedFonts`选择权`true`.该选项在`OptimizationOptions`班级。下面的代码片段展示了如何设置`UnembedFonts`选项：

```csharp
//设置 UnembedFonts 选项
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
```

## 步骤 4：优化 PDF 文档

设置后`UnembedFonts`选项，您可以使用`OptimizeResources`的方法`Document`班级。以下代码片段显示了如何优化 PDF 文档：

```csharp
//使用 OptimizationOptions 优化 PDF 文档
pdfDocument.OptimizeResources(optimizeOptions);
```

## 第 5 步：保存更新的文档

优化 PDF 文档后，您可以使用`Save`的方法`Document`班级。以下代码片段显示了如何保存更新后的文档：

```csharp
//保存更新的文档
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
```

## 第 6 步：获取原始文件和缩小后的文件大小

最后，您可以使用`FileInfo`System.IO 类。以下代码片段显示了如何获取原始文件和缩小后的文件大小：

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

### 使用 Aspose.PDF for .NET 获取未嵌入字体的示例源代码

以下是使用 Aspose.PDF for .NET 从 PDF 文档获取未嵌入字体的完整示例源代码：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//打开文档
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
//设置 UnembedFonts 选项
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
Console.WriteLine("Start");
//使用 OptimizationOptions 优化 PDF 文档
pdfDocument.OptimizeResources(optimizeOptions);
//保存更新的文档
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Finished");
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```
