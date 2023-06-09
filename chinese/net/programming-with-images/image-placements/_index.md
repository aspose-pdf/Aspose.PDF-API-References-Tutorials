---
title: 图片展示位置
linktitle: 图片展示位置
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 文档中放置图像。
type: docs
weight: 170
url: /zh/net/programming-with-images/image-placements/
---

在本教程中，我们将使用 .NET 的 Aspose.PDF 库处理 PDF 文档并对图像执行操作。我们将加载 PDF 文档，提取图像放置信息，并检索尺寸可见的图像。

## 第 1 步：设置环境
在开始之前，请确保您已使用以下内容设置开发环境：
- Aspose.PDF for .NET 安装在您的机器上。
- 可以使用的 AC# 项目。

## 第 2 步：加载 PDF 文档
首先，我们需要加载要处理的 PDF 文档。确保您具有指向包含 PDF 文档的目录的正确路径。

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
//加载源 PDF 文档
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "PlacementImage.pdf");
```

务必更换`"YOUR DOCUMENTS DIRECTORY"`包含 PDF 文件的文档目录的实际路径。

## 第 3 步：从图像中提取放置信息
现在我们已经加载了 PDF 文档，我们可以从图像中提取位置信息。我们将使用`ImagePlacementAbsorber`从文档的第一页吸收图像位置。

```csharp
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
//加载第一页的内容
doc.Pages[1].Accept(abs);
```

我们现在已经从文档的第一页中提取了图像放置信息。

## 第 4 步：检索具有可见尺寸的图像
现在我们将从我们之前提取的放置信息中检索具有可见尺寸的图像。

```csharp
foreach(ImagePlacement imagePlacement in abs.ImagePlacements)
{
     //获取图像属性
     Console.Out.WriteLine("Image Width: " + imagePlacement.Rectangle.Width);
     Console.Out.WriteLine("Image Height: " + imagePlacement.Rectangle.Height);
     Console.Out.WriteLine("LLX of image: " + imagePlacement.Rectangle.LLX);
     Console.Out.WriteLine("LLY of image: " + imagePlacement.Rectangle.LLY);
     Console.Out.WriteLine("Horizontal resolution of the image

  : " + imagePlacement.Resolution.X);
     Console.Out.WriteLine("Vertical image resolution: " + imagePlacement.Resolution.Y);

     //检索具有可见尺寸的图像
     Bitmap scaledImage;
     using (MemoryStream imageStream = new MemoryStream())
     {
         //从资源中获取图像
         imagePlacement.Image.Save(imageStream, System.Drawing.Imaging.ImageFormat.Png);
         Bitmap resourceImage = (Bitmap)Bitmap.FromStream(imageStream);

         //创建具有实际尺寸的图像
         scaledImage = new Bitmap(resourceImage, (int)imagePlacement.Rectangle.Width, (int)imagePlacement.Rectangle.Height);
     }
}
```

在这个循环中，我们检索每个图像的属性，例如宽度、高度、左下角的 X 和 Y 坐标以及水平和垂直分辨率。然后我们使用放置信息检索每个图像及其可见尺寸。

### 使用 Aspose.PDF for .NET 的图像放置示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//加载源 PDF 文档
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir+ "ImagePlacement.pdf");
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
//加载第一页的内容
doc.Pages[1].Accept(abs);
foreach (ImagePlacement imagePlacement in abs.ImagePlacements)
{
	//获取图像属性
	Console.Out.WriteLine("image width:" + imagePlacement.Rectangle.Width);
	Console.Out.WriteLine("image height:" + imagePlacement.Rectangle.Height);
	Console.Out.WriteLine("image LLX:" + imagePlacement.Rectangle.LLX);
	Console.Out.WriteLine("image LLY:" + imagePlacement.Rectangle.LLY);
	Console.Out.WriteLine("image horizontal resolution:" + imagePlacement.Resolution.X);
	Console.Out.WriteLine("image vertical resolution:" + imagePlacement.Resolution.Y);
	//检索具有可见尺寸的图像
	Bitmap scaledImage;
	using (MemoryStream imageStream = new MemoryStream())
	{
		//从资源中检索图像
		imagePlacement.Image.Save(imageStream, System.Drawing.Imaging.ImageFormat.Png);
		Bitmap resourceImage = (Bitmap)Bitmap.FromStream(imageStream);
		//创建具有实际尺寸的位图
		scaledImage = new Bitmap(resourceImage, (int)imagePlacement.Rectangle.Width, (int)imagePlacement.Rectangle.Height);
	}
}
```

## 结论
恭喜！您现在已经学习了如何使用 Aspose.PDF for .NET 在 PDF 文档中执行图像放置。我们解释了所提供的 C# 源代码，它允许您加载 PDF 文档、从图像中提取位置信息以及检索尺寸可见的图像。随意尝试更多 Aspose.PDF 来探索它的许多其他功能。