---
title: 调整图像大小
linktitle: 调整图像大小
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 调整 PDF 文档中图像大小的分步指南。
type: docs
weight: 250
url: /zh/net/programming-with-images/resize-images/
---

在本教程中，我们将带您了解如何使用 Aspose.PDF for .NET 调整 PDF 文档中图像的大小。按照以下步骤轻松执行此操作。

## 先决条件

在开始之前，请确保您具备以下条件：

- 安装和配置 Visual Studio 或任何其他开发环境。
- C# 编程语言的基本知识。
- 安装了 .NET 的 Aspose.PDF 库。可以从Aspose官网下载。

## 第 1 步：加载 PDF 文档

首先，使用以下代码加载 PDF 文档：

```csharp
//初始化时间
var time = DateTime.Now.Ticks;

string dataDir = "YOUR DOCUMENTS DIRECTORY";
//打开文档
Document pdfDocument = new Document(dataDir + "ResizeImage.pdf");
```

请务必提供 PDF 文档的正确路径。

## 第二步：优化选项初始化

在调整图像大小之前，我们需要初始化优化选项。使用以下代码：

```csharp
//初始化优化选项
var optimizeOptions = new Pdf.Optimization.OptimizationOptions();

//激活 CompressImages 选项
optimizeOptions.ImageCompressionOptions.CompressImages = true;

//设置图像质量
optimizeOptions.ImageCompressionOptions.ImageQuality = 75;

//激活 ResizeImages 选项
optimizeOptions.ImageCompressionOptions.ResizeImages = true;

//设置最大分辨率
optimizeOptions.ImageCompressionOptions.MaxResolution = 300;
```

您可以根据需要调整优化设置。

## 第三步：优化PDF文档

现在我们将使用我们定义的优化选项来优化 PDF 文档。使用以下代码：

```csharp
//使用 OptimizationOptions 优化 PDF 文档
pdfDocument.OptimizeResources(optimizeOptions);

dataDir = dataDir + "ResizeImages_out.pdf";
//保存更新的文档
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage resized successfully.\nFile saved as: " + dataDir);
```

请务必为更新的 PDF 文档提供所需的路径和文件名。

### 使用 Aspose.PDF for .NET 调整图像大小的示例源代码 
```csharp
//初始化时间
var time = DateTime.Now.Ticks;
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//打开文档
Document pdfDocument = new Document(dataDir + "ResizeImage.pdf");
//初始化优化选项
var optimizeOptions = new Pdf.Optimization.OptimizationOptions();            
//设置 CompressImages 选项
optimizeOptions.ImageCompressionOptions.CompressImages = true;            
//设置图像质量选项
optimizeOptions.ImageCompressionOptions.ImageQuality = 75;            
//设置 ResizeImage 选项
optimizeOptions.ImageCompressionOptions.ResizeImages = true;            
//设置 MaxResolution 选项
optimizeOptions.ImageCompressionOptions.MaxResolution = 300;
//使用 OptimizationOptions 优化 PDF 文档
pdfDocument.OptimizeResources(optimizeOptions);
dataDir = dataDir + "ResizeImages_out.pdf";
//保存更新的文档
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage resized successfully.\nFile saved at " + dataDir);
```

## 结论

恭喜！您已经使用 Aspose.PDF for .NET 成功地调整了 PDF 文档中图像的大小。您现在可以将此方法应用于您自己的项目以更改 PDF 文件中图像的大小。