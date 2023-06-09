---
title: 快速缩小图像
linktitle: 快速缩小图像
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 快速减小 PDF 文件中图像的大小。
type: docs
weight: 130
url: /zh/net/programming-with-images/fast-shrink-images/
---

本指南将逐步指导您如何使用 Aspose.PDF for .NET 快速减小 PDF 文件中图像的大小。确保您已经设置了环境并按照以下步骤操作：

## 第一步：初始化时间

在我们开始之前，我们将初始化测量压缩性能的时间。添加以下代码记录开始时间：

```csharp
var time = DateTime.Now.Ticks;
```

## 第二步：定义文档目录

确保设置正确的文档目录。代替`"YOUR DOCUMENT DIRECTORY"`在代码中包含 PDF 文档所在目录的路径。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 3 步：打开 PDF 文档

在此步骤中，我们将使用`Document` Aspose.PDF 类。使用`Document`构造函数并将路径传递给 PDF 文档。

```csharp
Document pdfDocument = new Document(dataDir + "Shrinkimage.pdf");
```

## 第 4 步：初始化优化选项

在此步骤中，我们将初始化图像压缩的优化选项。创建一个实例`OptimizationOptions`并设置合适的选项。在此示例中，我们启用图像压缩，将图像质量设置为 75，并使用快速压缩版本。

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions();
optimizeOptions.ImageCompressionOptions.CompressImages = true;
optimizeOptions.ImageCompressionOptions.ImageQuality = 75;
optimizeOptions.ImageCompressionOptions.Version = Pdf.Optimization.ImageCompressionVersion.Fast;
```

## 步骤 5：优化 PDF 文档

在此步骤中，我们将使用之前定义的优化选项来优化 PDF 文档。打电话给`OptimizeResources`的方法`pdfDocument`对象并传递优化选项。

```csharp
pdfDocument.OptimizeResources(optimizeOptions);
```

## 步骤 6：保存更新后的 PDF 文档

使用保存更新的 PDF 文档`Save`的方法`pdfDocument`目的。指定 PDF 文件的输出路径。

```csharp
dataDir = dataDir + "FastShrinkImages_out.pdf";
pdfDocument.Save(dataDir);
```

### 使用 Aspose.PDF for .NET 快速收缩图像的示例源代码 
```csharp
//初始化时间
var time = DateTime.Now.Ticks;
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//打开文档
Document pdfDocument = new Document(dataDir + "Shrinkimage.pdf");
//初始化优化选项
var optimizeOptions = new Pdf.Optimization.OptimizationOptions();
//设置 CompressImages 选项
optimizeOptions.ImageCompressionOptions.CompressImages = true;
//设置图像质量选项
optimizeOptions.ImageCompressionOptions.ImageQuality = 75;
//将 Imagae 压缩版本设置为快速
optimizeOptions.ImageCompressionOptions.Version = Pdf.Optimization.ImageCompressionVersion.Fast;
//使用 OptimizationOptions 优化 PDF 文档
pdfDocument.OptimizeResources(optimizeOptions);
dataDir = dataDir + "FastShrinkImages_out.pdf";
//保存更新的文档
pdfDocument.Save(dataDir);
Console.WriteLine("Ticks: {0}", DateTime.Now.Ticks - time);
Console.WriteLine("\nImage fast shrinked successfully.\nFile saved at " + dataDir);
```

## 结论

恭喜！您使用 Aspose.PDF for .NET 快速减小了 PDF 中图像的大小。优化后的 PDF 文件保存在指定目录中。您现在可以将此 PDF 文件与缩小的图像一起使用，以实现更高效的存储或共享需求。