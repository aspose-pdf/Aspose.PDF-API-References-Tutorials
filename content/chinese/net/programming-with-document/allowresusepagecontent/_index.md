---
title: 允许重复使用页面内容
linktitle: 允许重复使用页面内容
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 启用“允许重复使用页面内容”功能来优化 PDF。减小文件大小并提高性能。
type: docs
weight: 50
url: /zh/net/programming-with-document/allowresusepagecontent/
---
在本教程中，我们将解释如何使用 Aspose.PDF for .NET 启用“允许重用页面内容”功能。此功能通过重用页面内容、减小文件大小并提高性能来优化 PDF 文档。请按照以下分步指南进行操作：

## 第 1 步：加载 PDF 文档

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## 步骤 2：设置AllowReusePageContent 选项

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
    AllowReusePageContent = true
};
```

## 步骤 3：优化 PDF 文档

```csharp
pdfDocument.OptimizeResources(optimizeOptions);
```

## 步骤 4：保存更新后的文档

```csharp
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
```

## 步骤 5：检查文件大小减少情况

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

恭喜！您已成功允许重复使用 PDF 文档中的页面内容。

### 使用 Aspose.PDF for .NET 允许重用页面内容的示例源代码：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//打开文档
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");

//设置允许重用页面内容选项
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
    AllowReusePageContent = true
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

Console.WriteLine("\nAllowed reuse of page content successfully.\nFile saved at " + dataDir);
```

现在，您可以通过允许重复使用页面内容来有效优化 PDF 文档。

## 结论

在本教程中，我们解释了如何使用 Aspose.PDF for .NET 启用“允许重用页面内容”功能。通过遵循提供的分步指南并利用 C# 源代码，您可以通过允许重用页面内容来有效优化 PDF 文档。此优化会生成更小的 PDF 文件，从而在处理大型 PDF 文档时加快加载时间并提高性能。 Aspose.PDF for .NET 为 PDF 优化提供了强大且用户友好的解决方案，使您能够轻松创建高效且高质量的 PDF 文件。

### 常见问题解答

#### 问：在 PDF 文档中启用“允许重复使用页面内容”功能的目的是什么？

答：在 PDF 文档中启用“允许重用页面内容”功能可以通过重用页面内容来优化文件，从而减小文件大小并提高整体性能。此优化可生成更小的 PDF 文件，而不会影响内容质量。

#### 问：“允许重复使用页面内容”功能如何工作？

答：启用“允许重用页面内容”功能后，PDF 文档中的相同页面对象将被共享和重用，而不是每次出现时都重复。这种页面内容的共享显着减少了总体文件大小。

#### 问：我可以恢复优化并恢复原始文档吗？

答：不会，一旦执行“允许重用页面内容”优化并保存 PDF 文档，所做的更改就是永久性的。建议在执行任何优化之前保留原始文档的备份。

#### 问：启用此功能是否会影响 PDF 文档的视觉外观或内容？

答：启用“允许重复使用页面内容”功能不会影响 PDF 文档的视觉外观或内容。它仅优化文件的内部结构，以减少冗余并提高效率。

#### 问：Aspose.PDF for .NET 是 PDF 优化和操作的可靠解决方案吗？

答：是的，Aspose.PDF for .NET 是一个可靠且功能丰富的 PDF 优化和操作库。它提供了广泛的选项来优化 PDF 文件，包括减小文件大小、删除未使用的资源以及增强整体性能。