---
title: 允许重新使用页面内容
linktitle: 允许重新使用页面内容
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 启用“允许重新使用页面内容”功能来优化 PDF。减小文件大小并提高性能。
type: docs
weight: 50
url: /zh/net/programming-with-document/allowresusepagecontent/
---

在本教程中，我们将解释如何使用 Aspose.PDF for .NET 启用“允许重新使用页面内容”功能。此功能通过重用页面内容、减小文件大小和提高性能来优化 PDF 文档。请按照以下分步指南操作：

## 第 1 步：加载 PDF 文档

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## 第 2 步：设置 AllowReusePageContent 选项

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
    AllowReusePageContent = true
};
```

## 第 3 步：优化 PDF 文档

```csharp
pdfDocument.OptimizeResources(optimizeOptions);
```

## 第 4 步：保存更新后的文档

```csharp
pdfDocument.Save(dataDir + "OptimizeDocument_out.pdf");
```

## 第 5 步：检查文件大小减小

```csharp
var fi1 = new System.IO.FileInfo(dataDir + "OptimizeDocument.pdf");
var fi2 = new System.IO.FileInfo(dataDir + "OptimizeDocument_out.pdf");
Console.WriteLine("Original file size: {0}. Reduced file size: {1}", fi1.Length, fi2.Length);
```

恭喜！您已成功允许在 PDF 文档中重复使用页面内容。

### 允许使用 Aspose.PDF for .NET 重用页面内容的示例源代码：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//打开文档
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");

//设置 AllowReusePageContent 选项
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

现在您可以通过允许重复使用页面内容来有效地优化您的 PDF 文档。
