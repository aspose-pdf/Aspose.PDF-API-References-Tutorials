---
title: 优化文件大小
linktitle: 优化文件大小
second_title: Aspose.PDF for .NET API 参考
description: 使用此分步指南了解如何使用 Aspose.PDF for .NET 优化 PDF 文档的文件大小。
type: docs
weight: 250
url: /zh/net/programming-with-document/optimizefilesize/
---
Aspose.PDF for .NET 是一个库，它使开发人员能够在其 .NET 应用程序中创建、编辑和操作 PDF 文件。该库最有用的功能之一是能够优化 PDF 文档的文件大小。在本文中，我们将提供使用 Aspose.PDF for .NET 优化 PDF 文档文件大小的分步指南。

## 第 1 步：加载 PDF 文档

优化 PDF 文档文件大小的第一步是将文档加载到您的应用程序中。您可以使用`Document`Aspose.PDF for .NET 库提供的类。以下是如何加载 PDF 文档的示例：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//打开文档
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

确保更换`YOUR DOCUMENT DIRECTORY`包含 PDF 文档的目录路径。

## 第 2 步：设置优化选项

加载 PDF 文档后，您可以设置优化选项以指定要优化文档的哪些部分。这`OptimizationOptions`Aspose.PDF for .NET 库提供的类允许您指定各种选项来优化 PDF 文档的文件大小。以下是如何设置一些优化选项的示例：

```csharp
OptimizationOptions optimizationOptions = new OptimizationOptions();
optimizationOptions.LinkDuplcateStreams = true;
optimizationOptions.RemoveUnusedObjects = true;
optimizationOptions.RemoveUnusedStreams = true;
optimizationOptions.ImageCompressionOptions.CompressImages = true;
optimizationOptions.ImageCompressionOptions.ImageQuality = 10;
```

在此示例中，我们设置以下选项：
- `LinkDuplcateStreams`：此选项可以删除 PDF 文档中的重复流，这有助于减小文件大小。
- `RemoveUnusedObjects`：此选项可以删除 PDF 文档中任何未使用的对象，这也有助于减小文件大小。
- `RemoveUnusedStreams`：此选项可以删除 PDF 文档中任何未使用的流，这可以进一步减小文件大小。
- `CompressImages`：此选项启用 PDF 文档中的图像压缩，这可以显着减小文件大小。
- `ImageQuality`：此选项设置压缩图像的质量。较低的质量设置会导致较小的文件大小，但也可能导致图像质量较低。

## 步骤 4：优化 PDF 文档

现在您已经设置了优化选项，您可以使用`OptimizeResources`提供的方法`Document`班级。以下是如何优化 PDF 文档的示例：

```csharp
//通过删除未使用的对象来优化文件大小
pdfDocument.OptimizeResources(optimizationOptions);
```

## 步骤 5：保存优化后的 PDF 文档

优化 PDF 文档后，您可以将优化后的版本保存到新文件中。以下是如何保存优化后的 PDF 文档的示例：

```csharp
dataDir = dataDir + "OptimizeFileSize_out.pdf";
//保存输出文件
pdfDocument.Save(dataDir);
```

### 使用 Aspose.PDF for .NET 优化文件大小的示例源代码

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//打开文档
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");

OptimizationOptions optimizationOptions = new OptimizationOptions();
optimizationOptions.LinkDuplcateStreams = true;
optimizationOptions.RemoveUnusedObjects = true;
optimizationOptions.RemoveUnusedStreams = true;
optimizationOptions.ImageCompressionOptions.CompressImages = true;
optimizationOptions.ImageCompressionOptions.ImageQuality = 10;
//通过删除未使用的对象来优化文件大小
pdfDocument.OptimizeResources(optimizationOptions);
dataDir = dataDir + "OptimizeFileSize_out.pdf";
//保存输出文件
pdfDocument.Save(dataDir);
```
