---
title: 缩小图像
linktitle: 缩小图像
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 缩小 PDF 文档中图像大小的分步指南。
type: docs
weight: 280
url: /zh/net/programming-with-images/shrink-images/
---

在本教程中，我们将告诉您如何使用 Aspose.PDF for .NET 缩小 PDF 文档中图像的大小。按照以下步骤轻松执行此操作。

## 先决条件

在开始之前，请确保您具备以下条件：

- 安装和配置 Visual Studio 或任何其他开发环境。
- C# 编程语言的基本知识。
- 安装了 .NET 的 Aspose.PDF 库。可以从Aspose官网下载。

## 第 1 步：加载 PDF 文档

首先，使用以下代码加载 PDF 文档：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
//打开文档
Document pdfDocument = new Document(dataDir + "Shrinkimage.pdf");
```

请务必提供 PDF 文档的正确路径。

## 第二步：优化选项初始化

接下来，我们将初始化优化选项以减小图像的大小。使用以下代码：

```csharp
//初始化优化选项
var optimizeOptions = new Pdf.Optimization.OptimizationOptions();

//激活 CompressImages 选项
optimizeOptions.ImageCompressionOptions.CompressImages = true;

//设置图像质量
optimizeOptions.ImageCompressionOptions.ImageQuality = 50;
```

您可以根据需要调整优化设置。

## 第三步：优化PDF文档

现在我们要通过减小图像的大小来优化 PDF 文档。使用以下代码：

```csharp
//使用 OptimizationOptions 优化 PDF 文档
pdfDocument.OptimizeResources(optimizeOptions);

dataDir = dataDir + "Shrinkimage_out.pdf";
//保存更新的文档
pdfDocument.Save(dataDir);
Console.WriteLine("\nImages successfully reduced.\nFile saved as: " + dataDir);
```

请务必为更新的 PDF 文档提供所需的路径和文件名。

### 使用 Aspose.PDF for .NET 缩小图像的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//打开文档
Document pdfDocument = new Document(dataDir + "Shrinkimage.pdf");
//初始化优化选项
var optimizeOptions = new Pdf.Optimization.OptimizationOptions();
//设置 CompressImages 选项
optimizeOptions.ImageCompressionOptions.CompressImages = true;
//设置图像质量选项
optimizeOptions.ImageCompressionOptions.ImageQuality = 50;
//使用 OptimizationOptions 优化 PDF 文档
pdfDocument.OptimizeResources(optimizeOptions);
dataDir = dataDir + "Shrinkimage_out.pdf";
//保存更新的文档
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage shrinked successfully.\nFile saved at " + dataDir);
```

## 结论

恭喜！您已经使用 Aspose.PDF for .NET 成功缩小了 PDF 文档中的图像大小。您现在可以将此方法应用于您自己的项目，以优化 PDF 文件中图像的大小。