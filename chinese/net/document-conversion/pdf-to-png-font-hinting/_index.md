---
title: PDF 到 PNG 字体提示
linktitle: PDF 到 PNG 字体提示
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 将 PDF 转换为带有字体提示的 PNG 的分步指南。
type: docs
weight: 160
url: /zh/net/document-conversion/pdf-to-png-font-hinting/
---

在本教程中，我们将引导您完成使用 Aspose.PDF for .NET 将 PDF 转换为 PNG 图像的过程，同时启用字体提示。字体提示是一种提高小字体可读性的技术。按照以下步骤，您将能够将 PDF 的每一页转换为带有字体提示的 PNG 图像。

## 先决条件
在开始之前，请确保满足以下先决条件：

- C# 编程语言的基础知识。
- .NET 的 Aspose.PDF 库安装在您的系统上。
- 开发环境，例如 Visual Studio。

## 第 1 步：打开源 PDF 文档
在此步骤中，我们将使用 Aspose.PDF for .NET 打开源 PDF 文件。请遵循以下代码：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
//打开文档
Document pdfDocument = new Document(dataDir + "input.pdf");
```

务必更换`"YOUR DOCUMENTS DIRECTORY"`使用您的 PDF 文件所在的实际目录。

## 第 2 步：启用字体提示
打开 PDF 文件后，我们将使用渲染选项启用字体提示。使用以下代码：

```csharp
//创建呈现选项以启用字体提示
RenderingOptions opts = new RenderingOptions();
opts. UseFontHinting = true;
```

## 第 3 步：转换为 PNG 图像
现在我们要将 PDF 的每一页转换为带有字体提示的 PNG 图像。使用以下代码：

```csharp
for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
{
     using (FileStream imageStream = new FileStream(dataDir + "image" + pageCount + "_out" + ".png", FileMode.Create))
     {
         //创建具有指定属性的 PNGDevice 对象
         //宽度、高度、分辨率、质量
         //质量[0-100]，100为最大值
         //创建分辨率对象
         Resolution resolution = new Resolution(300);
         PngDevice pngDevice = new PngDevice(resolution);
         //设置预定义的渲染选项
         pngDevice.RenderingOptions = opts;

         //转换特定页面并将图像保存到流中
         pngDevice.Process(pdfDocument.Pages[pageCount], imageStream);

         //关闭流
         imageStream.Close();
     }
}
```

上面的代码将 PDF 的每一页转换为带有字体提示的 PNG 图像，并将每个图像保存为单独的 PNG 文件。

### 使用 Aspose.PDF for .NET 的 PDF 到 PNGFont 提示的示例源代码

```csharp
try
{
	
	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	//打开文档
	Document pdfDocument = new Document(dataDir + "input.pdf");
	//创建 Aspose.Pdf.RenderingOptions 以启用字体提示
	RenderingOptions opts = new RenderingOptions();
	opts.UseFontHinting = true;
	
	for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
	{
		using (FileStream imageStream = new FileStream(dataDir + "image" + pageCount + "_out" + ".png", FileMode.Create))
		{
			//创建具有指定属性的 PNG 设备
			//宽度、高度、分辨率、质量
			//质量 [0-100]，100 是最大值
			//创建分辨率对象
			Resolution resolution = new Resolution(300);
			PngDevice pngDevice = new PngDevice(resolution);
			//设置预定义的渲染选项
			pngDevice.RenderingOptions = opts;

			//转换特定页面并将图像保存到流
			pngDevice.Process(pdfDocument.Pages[pageCount], imageStream);

			//关闭流
			imageStream.Close();
		}
	}
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## 结论
在本教程中，我们介绍了使用 Aspose.PDF for .NET 将 PDF 转换为带有字体提示的 PNG 图像的分步过程。按照上述说明，您现在应该能够将 PDF 的每一页转换为带有字体提示的 PNG 图像。当您希望在转换为 PNG 图像时保持小字体的可读性时，此功能很有用。