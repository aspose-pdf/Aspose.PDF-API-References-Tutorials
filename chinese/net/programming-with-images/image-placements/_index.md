---
title: 图片展示位置
linktitle: 图片展示位置
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 将图像放入 PDF 文档中。
type: docs
weight: 170
url: /zh/net/programming-with-images/image-placements/
---
在本教程中，我们将使用 .NET 的 Aspose.PDF 库来处理 PDF 文档并对图像执行操作。我们将加载 PDF 文档，提取图像位置信息，并检索尺寸可见的图像。

## 第一步：搭建环境
在开始之前，请确保您已使用以下内容设置开发环境：
- Aspose.PDF for .NET 安装在您的计算机上。
- AC# 项目可供使用。

## 第 2 步：加载 PDF 文档
首先，我们需要加载要处理的 PDF 文档。确保您拥有包含 PDF 文档的目录的正确路径。

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
//加载源PDF文档
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "PlacementImage.pdf");
```

一定要更换`"YOUR DOCUMENTS DIRECTORY"`包含 PDF 文件的文档目录的实际路径。

## 步骤 3：从图像中提取位置信息
现在我们已经加载了 PDF 文档，我们可以从图像中提取位置信息。我们将使用`ImagePlacementAbsorber`从文档的第一页吸收图像位置。

```csharp
ImagePlacementAbsorber abs = new ImagePlacementAbsorber();
//加载第一页的内容
doc.Pages[1].Accept(abs);
```

我们现在已经从文档的第一页中提取了图像放置信息。

## 步骤 4：检索具有可见尺寸的图像
现在，我们将从之前提取的放置信息中检索图像及其可见尺寸。

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
         //从资源中获取图片
         imagePlacement.Image.Save(imageStream, System.Drawing.Imaging.ImageFormat.Png);
         Bitmap resourceImage = (Bitmap)Bitmap.FromStream(imageStream);

         //创建具有实际尺寸的图像
         scaledImage = new Bitmap(resourceImage, (int)imagePlacement.Rectangle.Width, (int)imagePlacement.Rectangle.Height);
     }
}
```

在此循环中，我们检索每个图像的属性，例如宽度、高度、左下角的 X 和 Y 坐标以及水平和垂直分辨率。然后，我们使用放置信息检索每个图像及其可见尺寸。

### 使用 Aspose.PDF for .NET 进行图像放置的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//加载源PDF文档
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
恭喜！您现在已经了解了如何使用 Aspose.PDF for .NET 在 PDF 文档中执行图像放置。我们解释了提供的 C# 源代码，它允许您加载 PDF 文档、从图像中提取位置信息以及检索尺寸可见的图像。请随意尝试更多 Aspose.PDF 以探索它的许多其他功能。

### 常见问题解答

#### 问：使用 Aspose.PDF for .NET 从 PDF 文档中提取图像位置信息的目的是什么？

答：提取图像位置信息可以让您检索 PDF 文档中图像的位置、尺寸和分辨率。该信息对于精确的图像处理和分析至关重要。

#### 问：Aspose.PDF for .NET 如何促进从 PDF 文档中提取图像放置信息？

答：Aspose.PDF for .NET 提供了`ImagePlacementAbsorber`类，可用于从 PDF 文档中吸收图像放置细节。提供的代码演示了如何利用此类来检索图像放置信息。

#### 问：图像放置信息在现实场景中可以用来做什么？

答：图像放置信息对于确保准确的图像对齐、计算图像尺寸、验证图像质量以及生成 PDF 文档中图像使用情况的报告等任务非常有价值。

#### Q：代码示例如何保证图片投放信息的准确提取？

答：代码示例采用了`ImagePlacementAbsorber`类来遍历指定页面的内容、识别图像位置并检索其属性，例如宽度、高度、坐标和分辨率。

#### 问：代码可以扩展以处理跨多个页面或文档的图像吗？

答：是的，可以通过迭代多个页面或文档来扩展代码，以提取图像放置信息并执行与图像相关的任务。

#### 问：代码如何根据放置信息检索图像及其可见尺寸？

答：代码示例从资源中提取图像数据，创建具有实际尺寸的位图图像，并提供宽度、高度、坐标和分辨率等属性。

#### 问：这种方法对于包含大量图像的大型 PDF 文档有效吗？

答：是的，Aspose.PDF for .NET 针对性能和资源使用进行了优化。它甚至可以从大型 PDF 文档中有效地提取图像位置信息。

#### 问：开发人员如何从理解和利用图像放置信息中受益？

答：开发人员可以确保 PDF 文档中精确的图像操作、对齐和分析。这些信息使他们能够创建用于图像处理、报告和质量保证的应用程序。

#### 问：是否可以自定义代码以提取其他与图像相关的属性或元数据？

答：当然，可以通过利用 Aspose.PDF for .NET 提供的适当类和方法来增强代码以提取其他属性，例如图像类型、色彩空间、压缩等。

#### 问：本教程中提供的结论有何意义？

答：结论总结了教程的内容，并鼓励进一步探索 Aspose.PDF for .NET，以利用其图像放置之外的功能，为各种 PDF 相关任务打开大门。