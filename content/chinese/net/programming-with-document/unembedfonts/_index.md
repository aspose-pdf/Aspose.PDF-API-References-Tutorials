---
title: 取消嵌入字体并优化 PDF 文件
linktitle: 取消嵌入字体并优化 PDF 文件
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 获取未嵌入字体并优化 PDF 文件。分步指南。
type: docs
weight: 370
url: /zh/net/programming-with-document/unembedfonts/
---
Aspose.PDF for .NET 是一个功能强大的库，它提供了处理 PDF 文档的各种功能。它的一个功能是从 PDF 文档中获取未嵌入的字体。如果您需要从 PDF 文档中提取字体并在其他应用程序中使用它们，这将非常有用。

我们将提供分步指南来解释 Aspose.PDF for .NET 获取未嵌入字体功能的以下 C# 源代码。

## 步骤1：设置文档目录的路径

在开始之前，我们需要设置 PDF 文档所在目录的路径。我们将此路径存储在名为“dataDir”的变量中。

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

将“您的文档目录”替换为您的 PDF 文档所在目录的实际路径。

## 第 2 步：打开 PDF 文档

第一步是加载要执行此操作的 PDF 文档，使用`Document`Aspose.PDF for .NET 的类。以下代码片段显示了如何加载 PDF 文档：

```csharp
//打开文档
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## 步骤3：设置 UnembedFonts 选项

要从 PDF 文档中获取未嵌入的字体，您需要设置`UnembedFonts`选择`true`。此选项在`OptimizationOptions`类。以下代码片段显示了如何设置`UnembedFonts`选项：

```csharp
//设置 UnembedFonts 选项
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
```

## 步骤4：优化PDF文档

设置后`UnembedFonts`选项，您可以使用`OptimizeResources`方法`Document`类。以下代码片段显示了如何优化PDF文档：

```csharp
//使用 OptimizationOptions 优化 PDF 文档
pdfDocument.OptimizeResources(optimizeOptions);
```

## 步骤 5：保存更新后的文档

 PDF 文档优化完成后，您可以使用`Save`方法`Document`类。以下代码片段显示了如何保存更新后的文档：

```csharp
//保存更新的文档
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
```

## 步骤 6：获取原始文件和缩小的文件大小

最后，您可以使用以下方法获取 PDF 文档的原始文件和缩小文件大小：`FileInfo` System.IO 类。以下代码片段显示了如何获取原始文件大小和缩小后的文件大小：

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

## 结论

在本教程中，我们演示了如何使用 Aspose.PDF for .NET 从 PDF 文档中获取未嵌入的字体。按照分步指南，您可以轻松地在 C# 应用程序中实现此功能。当您需要单独使用提取的字体或确保在不同平台上使用一致的字体时，取消嵌入字体会很有用。

## 常见问题解答

#### 问：从 PDF 文档中取消嵌入字体的目的是什么？

答：从 PDF 文档中取消嵌入字体允许您提取嵌入的字体并在其他应用程序中使用它们。这对于确保字体渲染的一致性和保留文档的视觉外观非常有用。

#### 问：如何在 C# 代码中指定文档目录的路径？

答：要指定文档目录的路径，请替换`"YOUR DOCUMENT DIRECTORY"`在代码中使用 PDF 文档所在目录的实际路径。

#### 问：`UnembedFonts` option do, and where is it set?

答：`UnembedFonts`选项，可在`OptimizationOptions`类，启用或禁用从 PDF 文档中取消嵌入字体。要将此选项设置为`true`，使用以下代码：

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
```

#### 问：我可以撤消优化过程中所做的更改吗？

答：Aspose.PDF for .NET 在优化过程中不会对原始 PDF 文档进行永久性更改。优化过程是在文档的副本上进行的，原始文档保持不变。

#### 问：如何查看优化后文件的原始大小和缩小后的大小？

答：您可以使用`FileInfo`类`System.IO`以获得原始文件大小和缩小后的文件大小。以下是实现此目的的示例代码片段：

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```