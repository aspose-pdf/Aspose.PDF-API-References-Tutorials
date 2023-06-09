---
title: 搜索并获取图像
linktitle: 搜索并获取图像
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 在 PDF 文档中搜索和获取图像的分步指南。
type: docs
weight: 260
url: /zh/net/programming-with-images/search-and-get-images/
---

在本教程中，我们将带您了解如何使用 Aspose.PDF for .NET 在 PDF 文档中搜索和获取图像。按照以下步骤轻松执行此操作。

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
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "SearchAndGetImages.pdf");
```

请务必提供 PDF 文档的正确路径。

## 第 2 步：搜索图像位置

要在 PDF 文档中搜索图像的位置，请使用以下代码：

```csharp
//创建一个 ImagePlacementAbsorber 对象来搜索图像位置
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();

//接受文档所有页面的吸收器
doc.Pages.Accept(abs);
```

这将收集吸收器中图像的位置。

## 第 3 步：浏览图像位置并获取图像及其属性

接下来，我们将浏览收集的图像位置并获取图像及其属性。使用以下代码：

```csharp
foreach(ImagePlacement imagePlacement in abs.ImagePlacements)
{
     //使用 ImagePlacement 对象获取图像
     XImage image = imagePlacement.Image;

     //显示图像位置属性
     Console.Out.WriteLine("Image Width: " + imagePlacement.Rectangle.Width);
     Console.Out.WriteLine("Image Height: " + imagePlacement.Rectangle.Height);
     Console.Out.WriteLine("LLX of image: " + imagePlacement.Rectangle.LLX);
     Console.Out.WriteLine("LLY of image: " + imagePlacement.Rectangle.LLY);
     Console.Out.WriteLine("Horizontal image resolution: " + imagePlacement.Resolution.X);
     Console.Out.WriteLine("Vertical image resolution: " + imagePlacement.Resolution.Y);
}
```

这将浏览所有图像位置，获取匹配图像并显示它们的属性。

### 使用 Aspose.PDF for .NET 搜索和获取图像的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//打开文档
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir+ "SearchAndGetImages.pdf");
//创建 ImagePlacementAbsorber 对象以执行图像放置搜索
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
//接受所有页面的吸收器
doc.Pages.Accept(abs);
//循环遍历所有 ImagePlacements，获取图像和 ImagePlacement 属性
foreach (ImagePlacement imagePlacement in abs.ImagePlacements)
{
	//使用 ImagePlacement 对象获取图像
	XImage image = imagePlacement.Image;
	//显示所有展示位置的图片展示位置属性
	Console.Out.WriteLine("image width:" + imagePlacement.Rectangle.Width);
	Console.Out.WriteLine("image height:" + imagePlacement.Rectangle.Height);
	Console.Out.WriteLine("image LLX:" + imagePlacement.Rectangle.LLX);
	Console.Out.WriteLine("image LLY:" + imagePlacement.Rectangle.LLY);
	Console.Out.WriteLine("image horizontal resolution:" + imagePlacement.Resolution.X);
	Console.Out.WriteLine("image vertical resolution:" + imagePlacement.Resolution.Y);
}
```

## 结论

恭喜！您已经成功地使用 Aspose.PDF for .NET 在 PDF 文档中搜索并获取图像。现在您可以将此方法应用到您自己的项目中，以从 PDF 文件中提取图像并获取它们的属性。