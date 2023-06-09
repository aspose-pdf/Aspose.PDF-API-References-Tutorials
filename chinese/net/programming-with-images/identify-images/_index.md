---
title: 识别图像
linktitle: 识别图像
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 轻松识别 PDF 文件中的图像并确定它们的颜色类型。
type: docs
weight: 150
url: /zh/net/programming-with-images/identify-images/
---

本指南将逐步指导您如何使用 Aspose.PDF for .NET 识别 PDF 文件中的图像。确保您已经设置了环境并按照以下步骤操作：

## 第一步：定义文档目录

确保设置正确的文档目录。代替`"YOUR DOCUMENT DIRECTORY"`在代码中包含 PDF 文档所在目录的路径。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：初始化计数器

在这一步中，我们将初始化灰度图像和 RGB 图像的计数器。

```csharp
int grayscaled = 0; //灰度图像计数器
int rdg = 0; //RGB 图像计数器
```

## 第 3 步：打开 PDF 文档

在此步骤中，我们将使用`Document` Aspose.PDF 类。使用`Document`构造函数并将路径传递给 PDF 文档。

```csharp
using (Document document = new Document(dataDir + "ExtractImages.pdf"))
{
```

## 第 4 步：浏览文档页面

在此步骤中，我们将遍历 PDF 文档的所有页面并识别每一页上的图像。

```csharp
foreach(Page page in document.Pages)
{
```

## 第 5 步：检索图像展示位置

在这一步中，我们将使用`ImagePlacementAbsorber`检索每个页面上的图像展示位置。

```csharp
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
page. Accept(abs);
```

## 第 6 步：对图像进行计数并确定其颜色类型

在这一步中，我们将计算每页上的图像数量并确定它们的颜色类型（灰度或 RGB）。

```csharp
Console.WriteLine("Total Images = {0} on page number {1}", abs.ImagePlacements.Count, page.Number);
int image_counter = 1;
foreach(ImagePlacement ia in abs.ImagePlacements)
{
     ColorType colorType = ia.Image.GetColorType();
     switch (colorType)
     {
         ColorType.Grayscale box:
             ++grayscaled;
             Console.WriteLine("Image {0} is grayscale...", image_counter);
             break;
         box ColorType.Rgb:
             ++rgd;
             Console.WriteLine("Image {0} is RGB...", image_counter);
             break;
     }
     image_counter += 1;
}
```

### 使用 Aspose.PDF for .NET 识别图像的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//灰度图像计数器
int grayscaled = 0;
//RGB 图像计数器
int rgd = 0;
using (Document document = new Document(dataDir + "ExtractImages.pdf"))
{
	foreach (Page page in document.Pages)
	{
		Console.WriteLine("--------------------------------");
		ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
		page.Accept(abs);
		//获取特定页面上的图像数
		Console.WriteLine("Total Images = {0} over page number {1}", abs.ImagePlacements.Count, page.Number);
		//文件.Pages[29].Accept(abs);
		int image_counter = 1;
		foreach (ImagePlacement ia in abs.ImagePlacements)
		{
			ColorType colorType = ia.Image.GetColorType();
			switch (colorType)
			{
				case ColorType.Grayscale:
					++grayscaled;
					Console.WriteLine("Image {0} is GrayScale...", image_counter);
					break;
				case ColorType.Rgb:
					++rgd;
					Console.WriteLine("Image {0} is RGB...", image_counter);
					break;
			}
			image_counter += 1;
		}
	}
}
```

## 结论

恭喜！您已经使用 Aspose.PDF for .NET 成功识别了 PDF 中的图像。对图像进行计数并识别其颜色类型（灰度或 RGB）。您现在可以使用此信息来满足您的特定需求。