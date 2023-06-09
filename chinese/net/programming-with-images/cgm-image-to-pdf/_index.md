---
title: CGM 图像转 PDF
linktitle: CGM 图像转 PDF
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 轻松将 CGM 图像转换为 PDF。
type: docs
weight: 40
url: /zh/net/programming-with-images/cgm-image-to-pdf/
---

本分步指南解释了如何使用 Aspose.PDF for .NET 将 CGM 图像转换为 PDF。确保您已经设置了环境并按照以下步骤操作：

## 第一步：定义文档目录

在开始之前，请确保为文档设置了正确的目录。代替`"YOUR DOCUMENT DIRECTORY"`在代码中包含 CGM 文件所在目录的路径。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第二步：定义输入输出文件

设置 CGM 输入文件名和 PDF 输出文件名。代替`"corvette.cgm"`使用您的 CGM 文件的名称，并更新`dataDir`使用所需的输出目录和 PDF 文件名。

```csharp
string inputFile = dataDir + "corvette.cgm";
dataDir = dataDir + "CGMImageToPDF_out.pdf";
```

## 第 3 步：将 CGM 图像转换为 PDF

使用`Produce`的方法`PdfProducer`使用将 CGM 文件转换为 PDF 格式`ImportFormat.Cgm`.指定 CGM 输入文件和 PDF 输出文件。

```csharp
PdfProducer.Produce(inputFile, ImportFormat.Cgm, dataDir);
```

### 使用 Aspose.PDF for .NET 的 CGMImage 到 PDF 的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inputFile = dataDir + "corvette.cgm";
dataDir = dataDir + "CGMImageToPDF_out.pdf";
//将 CGM 保存为 PDF 格式
PdfProducer.Produce(inputFile, ImportFormat.Cgm, dataDir);
Console.WriteLine("\nCGM file converted to pdf successfully.\nFile saved at " + dataDir); 
```

## 结论

恭喜！您已成功使用 Aspose.PDF for .NET 将 CGM 文件转换为 PDF。您现在可以在您的项目或应用程序中使用生成的 PDF 文件。