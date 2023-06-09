---
title: 页脚中的图像
linktitle: 页脚中的图像
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 文档的页脚部分添加图像。
type: docs
weight: 130
url: /zh/net/programming-with-stamps-and-watermarks/image-in-footer/
---
在本教程中，我们将逐步指导您如何使用 Aspose.PDF for .NET 在 PDF 文档的页脚部分添加图像。我们将使用提供的 C# 源代码打开现有的 PDF 文档，创建图像缓冲区，设置其属性，并将其添加到 PDF 文档的所有页面。

## 第 1 步：设置环境

在开始之前，请确保您具备以下条件：

- 已安装的 .NET 开发环境。
- 在您的项目中下载并引用了用于 .NET 的 Aspose.PDF 库。

## 第 2 步：加载现有的 PDF 文档

第一步是将现有的 PDF 文档加载到您的项目中。就是这样：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//打开现有的 PDF 文档
Document pdfDocument = new Document(dataDir + "ImageInFooter.pdf");
```

请务必将“您的文档目录”替换为您的 PDF 文档所在目录的实际路径。

## 第 3 步：在页脚部分创建和添加图像

现在 PDF 文档已加载，我们可以创建图像戳并将其添加到文档的所有页面。就是这样：

```csharp
//创建帧缓冲区
ImageStamp imageStamp = new ImageStamp(dataDir + "aspose-logo.jpg");

//设置图像缓冲区属性
imageStamp.BottomMargin = 10;
imageStamp.HorizontalAlignment = HorizontalAlignment.Center;
imageStamp.VerticalAlignment = VerticalAlignment.Bottom;

//将图像缓冲区添加到所有页面
foreach(Page page in pdfDocument.Pages)
{
     page.AddStamp(imageStamp);
}
```

上面的代码从“aspose-logo.jpg”文件创建一个图像缓冲区并设置其属性，例如底部边距、水平和垂直对齐方式。然后将图像缓冲区添加到 PDF 文档的所有页面。

## 第 4 步：保存修改后的 PDF 文档

将图像添加到页脚部分后，我们可以保存修改后的 PDF 文档。就是这样：

```csharp
//保存修改后的 PDF 文档
pdfDocument.Save(dataDir + "ImageInFooter_out.pdf");
```

上述代码将编辑好的PDF文档保存到指定目录。

### 使用 Aspose.PDF for .NET 的 Image In Footer 示例源代码 
```csharp

//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//打开文档
Document pdfDocument = new Document(dataDir+ "ImageInFooter.pdf");

//创建页脚
ImageStamp imageStamp = new ImageStamp(dataDir+ "aspose-logo.jpg");

//设置图章的属性
imageStamp.BottomMargin = 10;
imageStamp.HorizontalAlignment = HorizontalAlignment.Center;
imageStamp.VerticalAlignment = VerticalAlignment.Bottom;

//在所有页面上添加页脚
foreach (Page page in pdfDocument.Pages)
{
	page.AddStamp(imageStamp);
}
dataDir = dataDir + "ImageInFooter_out.pdf";

//保存更新的 PDF 文件
pdfDocument.Save(dataDir);
Console.WriteLine("\nImage in footer added successfully.\nFile saved at " + dataDir);
```

## 结论

恭喜！您已经学习了如何使用 Aspose.PDF for .NET 在 PDF 文档的页脚部分添加图像。您现在可以通过添加图像来自定义 PDF 文档的页脚。
