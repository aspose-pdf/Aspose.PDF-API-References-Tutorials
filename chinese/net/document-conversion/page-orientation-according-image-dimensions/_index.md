---
title: 页面方向根据图像尺寸
linktitle: 页面方向根据图像尺寸
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 根据图像尺寸设置页面方向的分步指南。
type: docs
weight: 80
url: /zh/net/document-conversion/page-orientation-according-image-dimensions/
---

在本教程中，我们将引导您完成使用 Aspose.PDF for .NET 根据图像尺寸设置页面方向的过程。我们将遍历给定目录中的 JPG 图像列表，并根据每个图像的宽度自动调整页面方向。请按照以下步骤实现此目的。

## 先决条件
在开始之前，请确保满足以下先决条件：

- C# 编程语言的基础知识。
- .NET 的 Aspose.PDF 库安装在您的系统上。
- 开发环境，例如 Visual Studio。

## 第 1 步：浏览 JPG 图片
在此步骤中，我们将浏览给定目录中的所有 JPG 图像。请遵循以下代码：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//创建一个新的 PDF 文档
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

//检索特定目录中所有 JPG 文件的名称
string[] fileEntries = Directory.GetFiles(dataDir, "*.JPG");
```

务必更换`"YOUR DOCUMENTS DIRECTORY"`使用 JPG 图像所在的实际目录。

## 第 2 步：创建页面和图像
浏览 JPG 文件后，我们将为每个文件创建一个页面和一个图像。使用以下代码：

```csharp
int counter;
for (counter = 0; counter < fileEntries.Length - 1; counter++)
{
//创建页面对象
Aspose.Pdf.Page page = doc.Pages.Add();

//创建图像对象
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
image1.File = fileEntries[counter];
```

## 第 3 步：检查图像尺寸
现在让我们检查每个图像的尺寸以确定页面方向。使用以下代码：

```csharp
//创建一个 BitMap 对象以从图像文件中获取信息
Bitmap myimage = new Bitmap(fileEntries[counter]);

//检查图像的宽度是否大于页面的宽度
if (myimage.Width > page.PageInfo.Width)
//

  If the width of the image is greater than the width of the page, set the page orientation to landscape
page.PageInfo.IsLandscape = true;
else
//如果图像的宽度小于页面的宽度，将页面的方向设置为纵向
page.PageInfo.IsLandscape = false;
```

## 第 4 步：将图像添加到 PDF 文档
检查图像的尺寸后，我们将图像添加到 PDF 文档的段落集合中。使用以下代码：

```csharp
//将图像添加到PDF文档的段落集合
page.Paragraphs.Add(image1);
```

## 第 5 步：保存 PDF 文件
将所有图像添加到 PDF 文档后，我们现在可以保存生成的 PDF 文件。这是最后一步：

```csharp
//保存 PDF 文件
doc.Save(dataDir + "SetPageOrientation_out.pdf");
```

代替`"YOUR DOCUMENTS DIRECTORY"`使用要保存输出 PDF 文件的所需目录。

### 使用 Aspose.Words for .NET 的页面方向根据图像尺寸的示例源代码

```csharp

//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

//检索特定目录中所有 JPG 文件的名称
string[] fileEntries = Directory.GetFiles(dataDir, "*.JPG");

int counter;
for (counter = 0; counter < fileEntries.Length - 1; counter++)
{
	//创建页面对象
	Aspose.Pdf.Page page = doc.Pages.Add();

	//创建图像对象
	Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
	image1.File = fileEntries[counter];

	//创建一个 BitMap 对象以获取图像文件的信息
	Bitmap myimage = new Bitmap(fileEntries[counter]);
	//检查图像文件的宽度是否大于页面宽度
	if (myimage.Width > page.PageInfo.Width)
		//如果图像宽度大于页面宽度，则将页面方向设置为横向
		page.PageInfo.IsLandscape = true;
	else
		//如果图像宽度小于页面宽度，则将页面方向设置为纵向
		page.PageInfo.IsLandscape = false;
	//将图像添加到 PDF 文档的段落集合
	page.Paragraphs.Add(image1);
}
//保存 Pdf 文件
doc.Save(dataDir + "SetPageOrientation_out.pdf");
```

## 结论
在本教程中，我们介绍了使用 Aspose.PDF for .NET 根据图像尺寸设置页面方向的分步过程。按照上述说明，您现在应该能够为每个图像创建具有正确页面方向的 PDF 文档。当您有不同尺寸的图像并想将它们嵌入 PDF 文档时，此功能很有用。