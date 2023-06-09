---
title: 布拉德利算法
linktitle: 布拉德利算法
second_title: Aspose.PDF for .NET API 参考
description: 使用 Bradley 算法和 Aspose.PDF for .NET 转换 PDF 文档。
type: docs
weight: 30
url: /zh/net/programming-with-images/bradley-algorithm/
---

本分步指南解释了如何将 Bradley 算法与 Aspose.PDF for .NET 结合使用。确保您已经设置了环境并按照以下步骤操作：

## 第一步：定义文档目录

在开始之前，请确保为文档设置了正确的目录。代替`"YOUR DOCUMENT DIRECTORY"`在代码中包含 PDF 文档所在目录的路径。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：打开文档

在此步骤中，我们将使用`Document` Aspose.PDF 类。使用`Document`构造函数并将路径传递给 PDF 文档。

```csharp
Document pdfDocument = new Document(dataDir + "PageToTIFF.pdf");
```

## 第 3 步：定义输出文件

为生成的图像和二进制图像定义输出文件名。代替`"resultant_out.tif"`和`"37116-bin_out.tif"`具有输出文件所需的名称。

```csharp
string outputImageFile = dataDir + "resultant_out.tif";
string outputBinImageFile = dataDir + "37116-bin_out.tif";
```

## 第 4 步：创建分辨率对象

创建一个`Resolution`对象来设置 TIFF 图像的分辨率。在此示例中，我们使用 300 dpi 的分辨率。

```csharp
Resolution resolution = new Resolution(300);
```

## 第 5 步：创建 TiffSettings 对象

创建一个`TiffSettings`对象指定输出 TIFF 文件的设置。在此示例中，我们使用 LZW 压缩和每像素 1 位的颜色深度（1 bpp 格式）。

```csharp
TiffSettings tiffSettings = new TiffSettings();
tiffSettings.Compression = CompressionType.LZW;
tiffSettings.Depth = Aspose.Pdf.Devices.ColorDepth.Format1bpp;
```

## 第 6 步：创建 TIFF 设备

使用创建 TIFF 设备`TiffDevice`对象，指定分辨率和 TIFF 设置。

```csharp
TiffDevice tiffDevice = new TiffDevice(resolution, tiffSettings);
```

## 第七步：转换特定页面并保存图像

使用`Process`TIFF 设备转换 PDF 文档的特定页面并将图像保存为 TIFF 文件的方法。指定文件输出路径。

```csharp
tiffDevice.Process(pdfDocument, outputImageFile);
```

## 步骤 8：使用 Bradley 算法对图像进行二值化

使用`BinarizeBradley`TIFF 设备使用 Bradley 算法对图像进行二值化的方法。此方法采用原始图像的输入流和二值图像的输出流。指定二值化阈值（本例中为 0.1）。

```csharp
using (FileStream

  inStream = new FileStream(outputImageFile, FileMode.Open))
{
using (FileStream outStream = new FileStream(outputBinImageFile, FileMode.Create))
{
tiffDevice. Binarize Bradley(inStream, outStream, 0.1);
}
}
```

### 使用 Aspose.PDF for .NET 的 Bradley 算法示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//打开文档
Document pdfDocument = new Document(dataDir+ "PageToTIFF.pdf");
string outputImageFile = dataDir + "resultant_out.tif";
string outputBinImageFile = dataDir + "37116-bin_out.tif";
//创建分辨率对象
Resolution resolution = new Resolution(300);
//创建 TiffSettings 对象
TiffSettings tiffSettings = new TiffSettings();
tiffSettings.Compression = CompressionType.LZW;
tiffSettings.Depth = Aspose.Pdf.Devices.ColorDepth.Format1bpp;
//创建 TIFF 设备
TiffDevice tiffDevice = new TiffDevice(resolution, tiffSettings);
//转换特定页面并将图像保存到流
tiffDevice.Process(pdfDocument, outputImageFile);
using (FileStream inStream = new FileStream(outputImageFile, FileMode.Open))
{
	using (FileStream outStream = new FileStream(outputBinImageFile, FileMode.Create))
	{
		tiffDevice.BinarizeBradley(inStream, outStream, 0.1);
	}
}
System.Console.WriteLine("Conversion using bradley algorithm performed successfully!");
```

## 结论

恭喜！您已经使用 Bradley 算法和 Aspose.PDF for .NET 成功完成了转换。您现在可以在您的项目或应用程序中使用生成的图像。