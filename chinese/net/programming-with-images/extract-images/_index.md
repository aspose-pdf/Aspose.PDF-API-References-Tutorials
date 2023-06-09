---
title: 提取图像
linktitle: 提取图像
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 轻松地从 PDF 文件中提取图像。
type: docs
weight: 120
url: /zh/net/programming-with-images/extract-images/
---

本指南将逐步指导您如何使用 Aspose.PDF for .NET 从 PDF 文件中提取图像。确保您已经设置了环境并按照以下步骤操作：

## 第一步：定义文档目录

在开始之前，请确保为文档设置了正确的目录。代替`"YOUR DOCUMENT DIRECTORY"`在代码中包含 PDF 文档所在目录的路径。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：打开 PDF 文档

在此步骤中，我们将使用`Document` Aspose.PDF 类。使用`Document`构造函数并将路径传递给 PDF 文档。

```csharp
Document pdfDocument = new Document(dataDir + "ExtractImages.pdf");
```

## 第 3 步：提取特定图像

在这一步中，我们将从特定页面中提取特定图像。使用`Images`页面集合`s `Resources` 对象访问所需的图像。在下面的示例中，我们从第一页中提取索引为 1 的图像。

```csharp
XImage xImage = pdfDocument.Pages[1].Resources.Images[1];
```

## 第 4 步：保存提取的图像

将提取的图像保存到文件中，使用`Save`的方法`xImage`目的。指定输出路径和图像格式（在本例中我们使用 JPEG 格式）。

```csharp
FileStream outputImage = new FileStream(dataDir + "output.jpg", FileMode.Create);
xImage.Save(outputImage, ImageFormat.Jpeg);
outputImage.Close();
```

## 第 5 步：保存更新后的 PDF 文件

使用保存更新的 PDF 文件`Save`的方法`pdfDocument`目的。指定 PDF 文件的输出路径。

```csharp
dataDir = dataDir + "ExtractImages_out.pdf";
pdfDocument.Save(dataDir);
```

### 使用 Aspose.PDF for .NET 提取图像的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//打开文档
Document pdfDocument = new Document(dataDir+ "ExtractImages.pdf");
//提取特定图像
XImage xImage = pdfDocument.Pages[1].Resources.Images[1];
FileStream outputImage = new FileStream(dataDir + "output.jpg", FileMode.Create);
//保存输出图像
xImage.Save(outputImage, ImageFormat.Jpeg);
outputImage.Close();
dataDir = dataDir + "ExtractImages_out.pdf";
//保存更新的 PDF 文件
pdfDocument.Save(dataDir);
Console.WriteLine("\nImages extracted successfully.\nFile saved at " + dataDir); 
```

## 结论

恭喜！您已成功使用 Aspose.PDF for .NET 从 PDF 中提取图像。提取的图像保存在指定目录中，同时保存更新的 PDF 文件。您现在可以使用这些文件来满足您的特定需求。