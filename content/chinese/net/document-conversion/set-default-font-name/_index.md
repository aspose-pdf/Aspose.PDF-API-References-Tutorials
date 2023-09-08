---
title: 设置默认字体名称
linktitle: 设置默认字体名称
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 在 PDF 文件中设置默认字体名称的分步指南。
type: docs
weight: 270
url: /zh/net/document-conversion/set-default-font-name/
---
在本教程中，我们将向您展示如何使用 Aspose.PDF for .NET 在 PDF 文件中设置默认字体名称。有时，当您从 PDF 文件中提取图像时，可能会遇到缺少字体的问题。通过指定默认字体名称，您可以确保提取的文本能够正确显示。按照以下步骤设置 PDF 文件中的默认字体名称。

## 先决条件
在开始之前，请确保满足以下先决条件：

- C# 编程语言的基础知识。
- 您的系统上安装了适用于 .NET 的 Aspose.PDF 库。
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

一定要更换`"YOUR DOCUMENTS DIRECTORY"`与您的 PDF 文件所在的实际目录。

## 第2步：设置默认字体名称
接下来，我们将使用以下命令设置默认字体名称`DefaultFontName`的选项`RenderingOptions`目的。使用以下代码：

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

一定要更换`"Arial"`与所需的字体名称。

## 第三步：图像提取
接下来，我们将从PDF文档的指定页面中提取图像。使用以下代码：

```csharp
pngDevice.Process(pdfDocument.Pages[1], imageStream);
```

请务必在中指定正确的页码`pdfDocument.Pages[1]`.

### 使用 Aspose.PDF for .NET 设置默认字体名称的示例源代码

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
在本教程中，我们学习了如何使用 Aspose.PDF for .NET 在 PDF 文件中设置默认字体名称。通过指定默认字体名称，您可以确保提取的文本能够正确显示。使用此方法可以解决从 PDF 文件中提取图像时丢失字体的问题。

### 常见问题解答

#### 问：什么是 Aspose.PDF for .NET？

答：Aspose.PDF for .NET 是一个功能强大的库，使开发人员能够在 C# 应用程序中处理 PDF 文档。它提供各种功能，包括设置 PDF 文件中的默认字体名称。

#### 问：为什么需要在 PDF 文件中设置默认字体名称？

答：从 PDF 文档中提取文本时，设置默认字体名称非常有用。如果 PDF 包含提取机上不可用的字体的文本，则指定默认字体名称可确保正确的文本显示。

#### 问：如何使用 Aspose.PDF for .NET 加载 PDF 文档并设置默认字体名称？

 A：要加载PDF文档并设置默认字体名称，您可以使用`Document`类来加载 PDF 文件和`RenderingOptions.DefaultFontName`属性来指定所需的默认字体名称。

#### 问：我可以选择任何字体作为默认字体名称吗？

答：是的，您可以选择提取机上可用的任何字体作为默认字体名称。使用与原始 PDF 中缺失字体紧密匹配的字体，以确保准确的文本呈现。

#### 问：设置默认字体名称是否会永久更改 PDF 文件？

答：不，使用 Aspose.PDF for .NET 设置默认字体名称是在文本提取过程中进行的临时更改。它不会修改原始 PDF 文件。