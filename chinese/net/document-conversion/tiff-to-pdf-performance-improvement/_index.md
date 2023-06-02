---
title: TIFF 到 PDF 的性能改进
linktitle: TIFF 到 PDF 的性能改进
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 改进 TIFF 到 PDF 转换性能的分步指南。
type: docs
weight: 310
url: /zh/net/document-conversion/tiff-to-pdf-performance-improvement/
---

在本教程中，我们将逐步引导您了解如何使用适用于 .NET 的 Aspose.PDF 库提高将 TIFF 文件转换为 PDF 的性能。我们将详细介绍所提供的 C# 源代码，并向您展示如何在您自己的项目中实施它。到本教程结束时，您将能够更快、更高效地将 TIFF 文件转换为 PDF。

## 第一步：设置文件目录
```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```
代替`"YOUR DOCUMENTS DIRECTORY"`使用您保存文件的路径。

## 第 2 步：获取 TIFF 文件列表
```csharp
string[] files = System.IO.Directory.GetFiles(dataDir, "*.tif");
```
获取指定目录中存在的 TIFF 文件列表。

## 第 3 步：实例化一个 Document 对象
```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```
创建文档对象的实例。

## 第 4 步：浏览文件并添加到 PDF 文档
```csharp
foreach (string myFile in files)
{
     FileStream fs = new FileStream(myFile, FileMode.Open, FileAccess.Read);
     byte[] tmpBytes = new byte[fs.Length];
     fs.Read(tmpBytes, 0, Convert.ToInt32(fs.Length));

     MemoryStream mystream = new MemoryStream(tmpBytes);
     Bitmap b = new Bitmap(mystream);
     Aspose.Pdf.Page currpage = doc.Pages.Add();

     currpage.PageInfo.Margin.Top = 5;
     currpage.PageInfo.Margin.Bottom = 5;
     currpage.PageInfo.Margin.Left = 5;
     currpage.PageInfo.Margin.Right = 5;

     currpage.PageInfo.Width = (b.Width / b.HorizontalResolution) * 72;
     currpage.PageInfo.Height = (b.Height / b.VerticalResolution) * 72;

     Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

     currpage.Paragraphs.Add(image1);

     image1.IsBlackWhite = true;
     image1.ImageStream = mystream;
     image1.ImageScale = 0.95F;
}
```
遍历每个 TIFF 文件，将其加载为`Bitmap`对象，然后将其添加到 PDF 文档中。还配置了图像的边距、分辨率和比例等参数。

## 第 5 步：保存生成的 PDF 文件
```csharp
doc.Save(dataDir + "PerformaceImprovement_out.pdf");
```
将生成的 PDF 文档保存到指定目录。

### 使用 Aspose.Words for .NET 的 TIFF 到 PDF 性能改进的示例源代码

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//获取 tiff 图像文件列表
string[] files = System.IO.Directory.GetFiles(dataDir, "*.tif");

//实例化一个文档对象
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

//在 pdf 文件中浏览文件和它们
foreach (string myFile in files)
{

	//加载字节数组中的所有 tiff 文件
	FileStream fs = new FileStream(myFile, FileMode.Open, FileAccess.Read);
	byte[] tmpBytes = new byte[fs.Length];
	fs.Read(tmpBytes, 0, Convert.ToInt32(fs.Length));

	MemoryStream mystream = new MemoryStream(tmpBytes);
	Bitmap b = new Bitmap(mystream);
	//在 Pdf 文档中新建 Page
	Aspose.Pdf.Page currpage = doc.Pages.Add();

	//设置边距使图像适合等。
	currpage.PageInfo.Margin.Top = 5;
	currpage.PageInfo.Margin.Bottom = 5;
	currpage.PageInfo.Margin.Left = 5;
	currpage.PageInfo.Margin.Right = 5;

	currpage.PageInfo.Width = (b.Width / b.HorizontalResolution) * 72;
	currpage.PageInfo.Height = (b.Height / b.VerticalResolution) * 72;

	//创建图像对象
	Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();

	//将图像添加到页面的段落集合中
	currpage.Paragraphs.Add(image1);

	//将 IsBlackWhite 属性设置为 true 以提高性能
	image1.IsBlackWhite = true;
	//将 ImageStream 设置为 MemoryStream 对象
	image1.ImageStream = mystream;
	//设置所需的图像比例
	image1.ImageScale = 0.95F;
}

//保存 PDF
doc.Save(dataDir + "PerformaceImprovement_out.pdf");
```

## 结论
在本教程中，我们学习了如何使用 .NET 的 Aspose.PDF 库提高将 TIFF 文件转换为 PDF 的性能。按照提供的步骤操作，您将能够更快、更高效地将 TIFF 文件转换为 PDF。在优化应用程序性能的同时获得精确和专业的结果