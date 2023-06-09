---
title: 设置图像大小
linktitle: 设置图像大小
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 设置 PDF 文档中图像大小的分步指南。
type: docs
weight: 270
url: /zh/net/programming-with-images/set-image-size/
---

在本教程中，我们将带您了解如何使用 Aspose.PDF for .NET 设置 PDF 文档中图像的大小。按照以下步骤轻松执行此操作。

## 先决条件

在开始之前，请确保您具备以下条件：

- 安装和配置 Visual Studio 或任何其他开发环境。
- C# 编程语言的基本知识。
- 安装了 .NET 的 Aspose.PDF 库。可以从Aspose官网下载。

## 第 1 步：创建 PDF 文档

首先，使用以下代码创建一个新的 PDF 文档：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
//实例化一个文档对象
Document doc = new Document();

//将页面添加到 PDF 文件的页面集合
Aspose.Pdf.Page page = doc.Pages.Add();
```

## 第 2 步：添加图片

接下来，我们将向 PDF 文档的页面添加图像。使用以下代码：

```csharp
//创建图像实例
Aspose.Pdf.Image img = new Aspose.Pdf.Image();

//以磅为单位设置图像的宽度和高度
img. FixWidth = 100;
img. FixHeight = 100;

//将图像类型设置为未知（Unknown）
img.FileType = Aspose.Pdf.ImageFileType.Unknown;

//图像源文件的路径
img.File = dataDir + "aspose-logo.jpg";

//将图像添加到页面的段落集合
page.Paragraphs.Add(img);
```

请务必提供图像源文件的正确路径。

## 第三步：设置页面属性

最后，我们将设置页面的属性，包括它的宽度和高度。使用以下代码：

```csharp
//设置页面属性
page.PageInfo.Width = 800;
page.PageInfo.Height = 800;
```

### 使用 Aspose.PDF for .NET 设置图像大小的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//实例化文档对象
Document doc = new Document();
//将页面添加到 PDF 文件的页面集合
Aspose.Pdf.Page page = doc.Pages.Add();
//创建图像实例
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
//以磅为单位设置图像宽度和高度
img.FixWidth = 100;
img.FixHeight = 100;
//将图像类型设置为 SVG
img.FileType = Aspose.Pdf.ImageFileType.Unknown;
//源文件路径
img.File = dataDir + "aspose-logo.jpg";
page.Paragraphs.Add(img);
//设置页面属性
page.PageInfo.Width = 800;
page.PageInfo.Height = 800;
dataDir = dataDir + "SetImageSize_out.pdf";
//保存生成的 PDF 文件
doc.Save(dataDir);
Console.WriteLine("\nImage size added successfully.\nFile saved at " + dataDir);
```

## 结论

恭喜！您已经使用 Aspose.PDF for .NET 成功设置了 PDF 文档中图像的大小。您现在可以将此方法应用于您自己的项目，以调整 PDF 文件中图像的大小。