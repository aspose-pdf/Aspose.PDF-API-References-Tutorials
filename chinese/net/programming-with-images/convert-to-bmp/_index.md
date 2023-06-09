---
title: 转换为 BMP
linktitle: 转换为 BMP
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 轻松将 PDF 转换为单独的 BMP 图像。
type: docs
weight: 90
url: /zh/net/programming-with-images/convert-to-bmp/
---

本指南将逐步指导您如何使用 Aspose.PDF for .NET 将 PDF 文件转换为单个 BMP 图像。确保您已经设置了环境并按照以下步骤操作：

## 第一步：定义文档目录

在开始之前，请确保为文档设置了正确的目录。代替`"YOUR DOCUMENT DIRECTORY"`在代码中包含 PDF 文档所在目录的路径。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：打开文档

在此步骤中，我们将使用`Document` Aspose.PDF 类。使用`Document`构造函数并将路径传递给 PDF 文档。

```csharp
Document pdfDocument = new Document(dataDir + "AddImage.pdf");
```

## 第 3 步：将每个页面转换为 BMP

在此步骤中，我们将浏览 PDF 文档的每一页并将它们转换为单独的 BMP 图像。我们将使用一个`for`循环遍历所有页面。

```csharp
for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
{
     //创建流以保存 BMP 图像
     using (FileStream imageStream = new FileStream("image" + pageCount + "_out" + ".bmp", FileMode.Create))
     {
         //创建分辨率对象
         Resolution resolution = new Resolution(300);
        
         //创建具有指定属性的 BMP 设备
         //宽度、高度、分辨率、页面大小
         BmpDevice bmpDevice = new BmpDevice(resolution);
        
         //转换特定页面并将图像保存到流中
         bmpDevice.Process(pdfDocument.Pages[pageCount], imageStream);
        
         //关闭流
         imageStream.Close();
     }
}
```

### 使用 Aspose.PDF for .NET 转换为 BMP 的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//打开文档
Document pdfDocument = new Document(dataDir + "AddImage.pdf");
for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
{
	using (FileStream imageStream = new FileStream("image" + pageCount + "_out" + ".bmp", FileMode.Create))
	{
		//创建分辨率对象
		Resolution resolution = new Resolution(300);
		//创建具有指定属性的 BMP 设备
		//宽度、高度、分辨率、页面大小
		BmpDevice bmpDevice = new BmpDevice(resolution);
		//转换特定页面并将图像保存到流
		bmpDevice.Process(pdfDocument.Pages[pageCount], imageStream);
		//关闭流
		imageStream.Close();
	}
} 
Console.WriteLine("\nPDF file converted to bmp successfully!"); 
```

## 结论

恭喜！您已经使用 Aspose.PDF for .NET 成功地将 PDF 文件转换为单独的 BMP 图像。 BMP 图像保存在指定的目录中。您现在可以在您的项目或应用程序中使用这些图像。