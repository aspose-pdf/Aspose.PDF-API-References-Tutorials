---
title: 设置 PDF 文件中的图像大小
linktitle: 设置 PDF 文件中的图像大小
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 设置 PDF 文件中图像大小的分步指南。
type: docs
weight: 270
url: /zh/net/programming-with-images/set-image-size/
---
在本教程中，我们将引导您了解如何使用 Aspose.PDF for .NET 设置 PDF 文件中图像的大小。请按照以下步骤轻松执行此操作。

## 先决条件

在开始之前，请确保您具备以下条件：

- 安装并配置 Visual Studio 或任何其他开发环境。
- C# 编程语言的基础知识。
- 安装了适用于.NET 的 Aspose.PDF 库。您可以从Aspose官方网站下载。

## 第 1 步：创建 PDF 文档

首先，使用以下代码创建一个新的 PDF 文档：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
//实例化一个文档对象
Document doc = new Document();

//将页面添加到 PDF 文件的页面集合中
Aspose.Pdf.Page page = doc.Pages.Add();
```

## 第2步：添加图片

接下来，我们将向 PDF 文档的页面添加图像。使用以下代码：

```csharp
//创建图像实例
Aspose.Pdf.Image img = new Aspose.Pdf.Image();

//设置图像的宽度和高度（以磅为单位）
img. FixWidth = 100;
img. FixHeight = 100;

//将图像类型设置为未知（Unknown）
img.FileType = Aspose.Pdf.ImageFileType.Unknown;

//图像源文件的路径
img.File = dataDir + "aspose-logo.jpg";

//将图像添加到页面的段落集合中
page.Paragraphs.Add(img);
```

请务必提供图像源文件的正确路径。

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
//实例化文档对象
Document doc = new Document();
//将页面添加到 PDF 文件的页面集合
Aspose.Pdf.Page page = doc.Pages.Add();
//创建图像实例
Aspose.Pdf.Image img = new Aspose.Pdf.Image();
//设置图像宽度和高度（以磅为单位）
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

恭喜！您已使用 Aspose.PDF for .NET 成功设置 PDF 文档中图像的大小。您现在可以将此方法应用到您自己的项目中，以调整 PDF 文件中图像的大小。

### 在 PDF 文件中设置图像尺寸的常见问题解答

#### 问：使用 Aspose.PDF for .NET 设置 PDF 文档中图像的大小的目的是什么？

答：设置PDF文档中图像尺寸的目的是为了控制图像添加到PDF时的尺寸。这允许您调整 PDF 文件中图像的外观和布局。

#### 问：在 PDF 文档中如何设置图像尺寸？

答：该过程涉及创建一个`Aspose.Pdf.Image`实例，使用指定其宽度和高度`FixWidth`和`FixHeight`属性，然后将图像添加到 PDF 文档。此外，您可以设置页面本身的尺寸以容纳图像。

#### 问：我可以将图像的大小设置为页面尺寸的特定百分比吗？

答：提供的代码设置图像的绝对宽度和高度（以磅为单位）。如果您想根据页面尺寸的百分比设置图像的尺寸，则需要相应地计算尺寸并相应地调整代码。

#### 问： 其意义何在？`FileType` property when adding an image to the PDF document?

答： 的`FileType`属性指定添加到 PDF 文档中的图像的类型。在提供的代码中，值`Unknown`表示图像类型未知，Aspose.PDF 将尝试根据文件扩展名确定图像类型。

#### 问：我可以使用此方法将多个图像添加到单个页面吗？

答：是的，您可以通过创建多个图像将多个图像添加到单个页面`Aspose.Pdf.Image`实例并将它们添加到页面的段落集合中。确保根据需要调整图像的位置和布局。

#### 问：如何控制页面上添加的图像的位置和对齐方式？

答：可以通过使用以下属性调整图像的坐标和布局来控制添加的图像的放置和对齐：`img.Left`, `img.Top`和段落格式属性。

#### 问：使用设置页面属性的目的是什么？`page.PageInfo.Width` and `page.PageInfo.Height`?

答：设置页面属性允许您定义页面本身的尺寸。这可确保页面尺寸适应添加的图像以及页面上可能有的任何其他内容。

#### 问：我可以为同一个 PDF 文档中的不同图像设置不同的尺寸吗？

答：是的，您可以通过创建单独的图像来为不同的图像设置不同的尺寸`Aspose.Pdf.Image`实例并调整`FixWidth`, `FixHeight`，以及每个图像的放置属性。

#### 问：如何将此方法集成到我自己的项目中以设置 PDF 文件中的图像尺寸？

答：要将此方法集成到您的项目中，请按照概述的步骤操作并根据需要修改代码。您可以使用此方法根据应用程序的要求将特定尺寸的图像添加到 PDF 文档中。