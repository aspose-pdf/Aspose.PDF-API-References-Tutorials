---
title: 在 PDF 文件中设置图像大小
linktitle: 在 PDF 文件中设置图像大小
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 设置 PDF 文件中图像大小的分步指南。
type: docs
weight: 270
url: /zh/net/programming-with-images/set-image-size/
---
在本教程中，我们将引导您了解如何使用 Aspose.PDF for .NET 设置 PDF 文件中图像的大小。按照以下步骤轻松执行此操作。

## 先决条件

开始之前，请确保您已准备好以下物品：

- 已安装并配置 Visual Studio 或任何其他开发环境。
- C# 编程语言的基本知识。
- 已安装适用于 .NET 的 Aspose.PDF 库。您可以从 Aspose 官方网站下载。

## 步骤 1：创建 PDF 文档

首先，使用以下代码创建一个新的 PDF 文档：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
//实例化 Document 对象
Document doc = new Document();

//将页面添加到 PDF 文件的页面集合中
Aspose.Pdf.Page page = doc.Pages.Add();
```

## 第 2 步：添加图片

接下来，我们将向 PDF 文档的页面添加图像。使用以下代码：

```csharp
//创建图像实例
Aspose.Pdf.Image img = new Aspose.Pdf.Image();

//以点为单位设置图像的宽度和高度
img. FixWidth = 100;
img. FixHeight = 100;

//将图像类型设置为未知（Unknown）
img.FileType = Aspose.Pdf.ImageFileType.Unknown;

//图片源文件的路径
img.File = dataDir + "aspose-logo.jpg";

//将图像添加到页面的段落集合中
page.Paragraphs.Add(img);
```

确保提供图像源文件的正确路径。

## 步骤 3：设置页面属性

最后，我们将设置页面的属性，包括其宽度和高度。使用以下代码：

```csharp
//设置页面属性
page.PageInfo.Width = 800;
page.PageInfo.Height = 800;
```

### 使用 Aspose.PDF for .NET 设置图像大小的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//实例化 Document 对象
Document doc = new Document();
//将页面添加到 PDF 文件的页面集合
Aspose.Pdf.Page page = doc.Pages.Add();
//创建图像实例
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
//以点为单位设置图像宽度和高度
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

恭喜！您已成功使用 Aspose.PDF for .NET 设置 PDF 文档中图像的大小。现在，您可以将此方法应用到您自己的项目中，以调整 PDF 文件中图像的大小。

### PDF 文件中设置图像大小的常见问题

#### 问：使用 Aspose.PDF for .NET 设置 PDF 文档中图像的大小有什么目的？

答：设置 PDF 文档中图片的大小的目的是控制图片添加到 PDF 时的尺寸。这允许您调整 PDF 文件中图片的外观和布局。

#### 问：在 PDF 文档中如何设置图像大小？

答：该过程涉及创建一个`Aspose.Pdf.Image`实例，使用指定其宽度和高度`FixWidth`和`FixHeight`属性，然后将图像添加到 PDF 文档。此外，您还可以设置页面本身的尺寸以容纳图像。

#### 问：我可以将图像的大小设置为页面尺寸的特定百分比吗？

答：提供的代码以点为单位设置图像的绝对宽度和高度。如果您想根据页面尺寸的百分比设置图像的大小，则需要相应地计算尺寸并相应地调整代码。

#### 问：`FileType` property when adding an image to the PDF document?

答：`FileType`属性指定添加到 PDF 文档的图像类型。在提供的代码中，值`Unknown`表示图像类型未知，Aspose.PDF 将尝试根据文件扩展名确定图像类型。

#### 问：我可以使用此方法将多张图片添加到单个页面吗？

答：是的，您可以通过创建多个图片将多张图片添加到一个页面。`Aspose.Pdf.Image`实例并将其添加到页面的段落集合中。确保根据需要调整图像的位置和布局。

#### 问：如何控制页面上添加的图像的位置和对齐方式？

答：可以通过调整图像的坐标和布局来控制添加图像的位置和对齐方式，具体方法是使用以下属性：`img.Left`, `img.Top`以及段落格式属性。

#### 问：使用设置页面属性的目的是什么`page.PageInfo.Width` and `page.PageInfo.Height`?

答：设置页面属性允许您定义页面本身的尺寸。这可确保页面尺寸能够容纳添加的图像以及页面上可能存在的任何其他内容。

#### 问：我可以为同一个 PDF 文档中的不同图像设置不同的大小吗？

答：是的，您可以通过创建单独的图片来设置不同尺寸。`Aspose.Pdf.Image`实例和调整`FixWidth`, `FixHeight`以及每幅图像的放置属性。

#### 问：我如何将此方法集成到我自己的项目中来设置 PDF 文件中的图像大小？

答：要将此方法集成到您的项目中，请按照概述的步骤操作并根据需要修改代码。您可以根据应用程序的要求使用此方法将特定大小的图像添加到 PDF 文档中。