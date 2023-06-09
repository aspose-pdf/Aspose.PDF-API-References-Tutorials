---
title: 平板解码压缩
linktitle: 平板解码压缩
second_title: Aspose.PDF for .NET API 参考
description: 使用 Flate Decode 压缩和 Aspose.PDF for .NET 有效地压缩 PDF 中的图像。
type: docs
weight: 140
url: /zh/net/programming-with-images/flate-decode-compression/
---

本指南将逐步指导您如何使用 Aspose.PDF for .NET 使用 Flate Decode 压缩将图像压缩为 PDF 文件。确保您已经设置了环境并按照以下步骤操作：

## 第一步：定义文档目录

确保设置正确的文档目录。代替`"YOUR DOCUMENT DIRECTORY"`在代码中包含 PDF 文档所在目录的路径。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：打开 PDF 文档

在此步骤中，我们将使用`Document` Aspose.PDF 类。使用`Document`构造函数并将路径传递给 PDF 文档。

```csharp
Document doc = new Document(dataDir + "AddImage.pdf");
```

## 第 3 步：初始化优化选项

在此步骤中，我们将初始化图像压缩的优化选项。创建一个实例`OptimizationOptions`并设置合适的选项。在此示例中，我们使用 Flate Decode 压缩来优化图像。

```csharp
var optimizationOptions = new Aspose.Pdf.Optimization.OptimizationOptions();
optimizationOptions.ImageCompressionOptions.Encoding = ImageEncoding.Flate;
```

## 第 4 步：优化 PDF 文档

在此步骤中，我们将使用之前定义的优化选项来优化 PDF 文档。打电话给`OptimizeResources`的方法`doc`对象并传递优化选项。

```csharp
doc.OptimizeResources(optimizationOptions);
```

## 步骤 5：保存更新后的 PDF 文档

使用保存更新的 PDF 文档`Save`的方法`doc`目的。指定 PDF 文件的输出路径。

```csharp
doc.Save(dataDir + "FlateDecodeCompression.pdf");
```

### 使用 Aspose.PDF for .NET 的 Flate 解码压缩示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//打开文件
Document doc = new Document(dataDir + "AddImage.pdf");
//初始化优化选项
var optimizationOptions = new Aspose.Pdf.Optimization.OptimizationOptions();
//要使用 FlateDecode Compression 优化图像，请将优化选项设置为 Flate
optimizationOptions.ImageCompressionOptions.Encoding = ImageEncoding.Flate;
//设置优化选项
doc.OptimizeResources(optimizationOptions);
//保存文件
doc.Save(dataDir + "FlateDecodeCompression.pdf");
```

## 结论

恭喜！您已经使用 Aspose.PDF for .NET 使用 Flate Decode 压缩成功地将图像压缩为 PDF。优化后的 PDF 文件保存在指定目录中。您现在可以使用此 PDF 文件来满足更高效的存储或共享需求。