---
title: 取消嵌入字体并优化 PDF 文件
linktitle: 取消嵌入字体并优化 PDF 文件
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 获取非嵌入字体并优化 PDF 文件。分步指南。
type: docs
weight: 370
url: /zh/net/programming-with-document/unembedfonts/
---
Aspose.PDF for .NET 是一个功能强大的库，提供了广泛的处理 PDF 文档的功能。它的功能之一是从 PDF 文档中获取未嵌入的字体。如果您需要从 PDF 文档中提取字体并在其他应用程序中使用它们，这会很有用。

我们将提供分步指南来解释 Aspose.PDF for .NET 的获取非嵌入字体功能的以下 C# 源代码。

## 第一步：设置文档目录路径

在开始之前，我们需要设置 PDF 文档所在目录的路径。我们将该路径存储在名为“dataDir”的变量中。

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

将“您的文档目录”替换为 PDF 文档所在目录的实际路径。

## 第 2 步：打开 PDF 文档

第一步是加载您想要执行此操作的 PDF 文档，使用`Document`.NET 的 Aspose.PDF 类。以下代码片段展示了如何加载 PDF 文档：

```csharp
//打开文档
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## 步骤 3：设置 UnembedFonts 选项

要从 PDF 文档中获取未嵌入的字体，您需要设置`UnembedFonts`选项`true`。此选项可在`OptimizationOptions`班级。以下代码片段展示了如何设置`UnembedFonts`选项：

```csharp
//设置取消嵌入字体选项
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
```

## 步骤 4：优化 PDF 文档

设置后`UnembedFonts`选项，您可以使用以下命令优化 PDF 文档`OptimizeResources`的方法`Document`班级。以下代码片段展示了如何优化 PDF 文档：

```csharp
//使用 OptimizationOptions 优化 PDF 文档
pdfDocument.OptimizeResources(optimizeOptions);
```

## 第5步：保存更新后的文档

 PDF 文档优化后，您可以使用以下命令保存更新后的文档：`Save`的方法`Document`班级。以下代码片段显示了如何保存更新的文档：

```csharp
//保存更新的文档
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
```

## 第 6 步：获取原始文件大小和缩小后的文件大小

最后，您可以使用以下命令获取 PDF 文档的原始文件大小和缩小后的文件大小`FileInfo`System.IO 类。以下代码片段显示了如何获取原始文件大小和缩小后的文件大小：

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
//设置取消嵌入字体选项
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

在本教程中，我们演示了如何使用 Aspose.PDF for .NET 从 PDF 文档中获取未嵌入的字体。通过遵循分步指南，您可以在 C# 应用程序中轻松实现此功能。当您需要单独使用提取的字体或确保跨不同平台的字体使用一致时，取消嵌入字体可能会很有用。

## 常见问题解答

#### 问：从 PDF 文档中取消嵌入字体的目的是什么？

答：从 PDF 文档中取消嵌入字体允许您提取嵌入的字体并在其他应用程序中使用它们。这对于确保一致的字体渲染和保留文档的视觉外观非常有用。

#### Q：如何在C#代码中指定文档目录的路径？

 A：要指定文档目录的路径，替换`"YOUR DOCUMENT DIRECTORY"`在代码中添加 PDF 文档所在目录的实际路径。

#### 问：什么是`UnembedFonts` option do, and where is it set?

答： 的`UnembedFonts`选项，可在`OptimizationOptions`类，启用或禁用从 PDF 文档中取消嵌入字体。将此选项设置为`true`，使用以下代码：

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	UnembedFonts = true
};
```

#### 问：我可以恢复优化过程中所做的更改吗？

答：Aspose.PDF for .NET 在优化过程中不会对原始 PDF 文档进行永久性更改。优化过程是在文档的副本上执行的，保持原始文档不变。

#### Q：如何查看优化后的原始文件大小和缩小后的文件大小？

答：您可以使用`FileInfo`类的`System.IO`获取原始文件大小和缩小后的文件大小。下面是实现此目的的示例代码片段：

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```