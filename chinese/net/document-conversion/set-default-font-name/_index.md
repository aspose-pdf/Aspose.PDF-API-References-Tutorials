---
title: 设置默认字体名称
linktitle: 设置默认字体名称
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 在 PDF 文件中设置默认字体名称的分步指南。
type: docs
weight: 270
url: /zh/net/document-conversion/set-default-font-name/
---

在本教程中，我们将向您展示如何使用 Aspose.PDF for .NET 在 PDF 文件中设置默认字体名称。有时，当您从 PDF 文件中提取图像时，您可能会遇到丢失字体的问题。通过指定默认字体名称，您可以确保正确显示提取的文本。按照以下步骤设置 PDF 文件中的默认字体名称。

## 先决条件
在开始之前，请确保满足以下先决条件：

- C# 编程语言的基础知识。
- .NET 的 Aspose.PDF 库安装在您的系统上。
- 开发环境，例如 Visual Studio。

## 第 1 步：加载 PDF 文档
第一步是将 PDF 文档加载到`Document`目的。使用以下代码：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

using (Document pdfDocument = new Document(dataDir + "input.pdf"))
{
     //要添加的代码
}
```

务必更换`"YOUR DOCUMENTS DIRECTORY"`使用您的 PDF 文件所在的实际目录。

## 第 2 步：设置默认字体名称
接下来，我们将使用`DefaultFontName`的选项`RenderingOptions`目的。使用以下代码：

```csharp
using (Document pdfDocument = new Document(dataDir + "input.pdf"))
{
     using (FileStream imageStream = new FileStream(dataDir + "SetDefaultFontName.png", FileMode.Create))
     {
         Resolution resolution = new Resolution(300);
         PngDevice pngDevice = new PngDevice(resolution);
         RenderingOptions ro = new RenderingOptions();
         ro.DefaultFontName = "Arial";
         pngDevice.RenderingOptions = ro;
        
         //要添加的代码
     }
}
```

务必更换`"Arial"`使用所需的字体名称。

## 第三步：图像提取
接下来，我们将从PDF文档的指定页面中提取图像。使用以下代码：

```csharp
pngDevice.Process(pdfDocument.Pages[1], imageStream);
```

请务必在中指定正确的页码`pdfDocument.Pages[1]`.

### 使用 Aspose.Words for .NET 设置默认字体名称的示例源代码

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

using (Document pdfDocument = new Document(dataDir + "input.pdf"))
{
	using (FileStream imageStream = new FileStream(dataDir + "SetDefaultFontName.png", FileMode.Create))
	{
		Resolution resolution = new Resolution(300);
		PngDevice pngDevice = new PngDevice(resolution);
		RenderingOptions ro = new RenderingOptions();
		ro.DefaultFontName = "Arial";
		pngDevice.RenderingOptions = ro;
		pngDevice.Process(pdfDocument.Pages[1], imageStream);
	}
}
```

## 结论
在本教程中，我们学习了如何使用 Aspose.PDF for .NET 在 PDF 文件中设置默认字体名称。通过指定默认字体名称，您可以确保正确显示提取的文本。使用此方法可以解决从 PDF 文件中提取图像时丢失字体的问题。