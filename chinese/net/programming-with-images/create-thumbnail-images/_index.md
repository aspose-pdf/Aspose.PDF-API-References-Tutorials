---
title: 创建缩略图
linktitle: 创建缩略图
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 从 PDF 文件轻松创建图像缩略图。
type: docs
weight: 100
url: /zh/net/programming-with-images/create-thumbnail-images/
---

本指南将逐步指导您如何使用 Aspose.PDF for .NET 从 PDF 文件创建图像缩略图。确保您已经设置了环境并按照以下步骤操作：

## 第一步：定义文档目录

在开始之前，请确保为文档设置了正确的目录。代替`"YOUR DOCUMENT DIRECTORY"`在代码中包含 PDF 文件所在目录的路径。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第二步：获取目录下所有PDF文件的名称

在此步骤中，我们将使用 C# 检索指定目录中存在的所有 PDF 文件的名称`Directory`班级。文件将存储在一个字符串数组中。

```csharp
string[] fileEntries = Directory.GetFiles(dataDir, "*.pdf");
```

## 第 3 步：浏览所有 PDF 文件及其页面

在此步骤中，我们将遍历所有 PDF 文件及其页面以创建图像缩略图。我们将使用一个`for`循环遍历所有文件。

```csharp
for (int counter = 0; counter < fileEntries.Length; counter++)
{
     //打开 PDF 文档
     Document pdfDocument = new Document(fileEntries[counter]);
    
     //浏览文档的所有页面
     for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
     {
         //创建流以保存缩略图
         using (FileStream imageStream = new FileStream(dataDir + "\\Thumbnails" + counter.ToString() + "_" + pageCount + ".jpg", FileMode.Create))
         {
             //创建分辨率对象
             Resolution resolution = new Resolution(300);
            
             //创建具有指定属性的 JPEG 设备
             JpegDevice jpegDevice = new JpegDevice(45, 59, resolution, 100);
            
             //转换特定页面并将图像保存到流中
             jpegDevice.Process(pdfDocument.Pages[pageCount], imageStream);
            
             //关闭流
             imageStream.Close();
         }
     }
}
```

### 使用 Aspose.PDF for .NET 创建缩略图的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//检索特定目录中所有 PDF 文件的名称
string[] fileEntries = Directory.GetFiles(dataDir, "*.pdf");
//遍历数组中的所有文件条目
for (int counter = 0; counter < fileEntries.Length; counter++)
{
	//打开文档
	Document pdfDocument = new Document(fileEntries[counter]);
	for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
	{
		using (FileStream imageStream = new FileStream(dataDir + "\\Thumbanils" + counter.ToString() + "_" + pageCount + ".jpg", FileMode.Create))
		{
			//创建分辨率对象
			Resolution resolution = new Resolution(300);
			//JpegDevice jpegDevice = new JpegDevice(500, 700, 分辨率, 100);
			JpegDevice jpegDevice = new JpegDevice(45, 59, resolution, 100);
			//转换特定页面并将图像保存到流
			jpegDevice.Process(pdfDocument.Pages[pageCount], imageStream);
			//关闭流
			imageStream.Close();
		}
	}
}
System.Console.WriteLine("PDF pages are converted to thumbnails successfully!");
```

## 结论

恭喜！您已经使用 Aspose.PDF for .NET 成功地从 PDF 文件创建了图像缩略图。图片缩略图保存在指定目录中。您现在可以使用这些缩略图来显示 PDF 文件的可视化预览。