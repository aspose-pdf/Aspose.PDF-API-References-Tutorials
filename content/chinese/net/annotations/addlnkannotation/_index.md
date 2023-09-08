---
title: 添加lnk注释
linktitle: 添加lnk注释
second_title: Aspose.PDF for .NET API 参考
description: 通过分步指南和完整源代码，了解如何使用 Aspose.PDF for .NET 在 C# 中向 PDF 文档添加墨迹注释功能。
type: docs
weight: 20
url: /zh/net/annotations/addlnkannotation/
---
Aspose.PDF for .NET 是一个功能强大的库，使开发人员能够执行各种 PDF 操作。其中一项操作就是向 PDF 文档添加墨迹注释。在本文中，我们将提供分步指南来解释使用 Aspose.PDF for .NET 添加墨迹注释的 C# 源代码。让我们开始吧！

## 了解 Aspose.PDF for .NET 的墨迹注释功能

在深入研究 C# 源代码之前，我们首先了解什么是 Ink Annotation 及其用途。

墨迹注释是一种在 PDF 文档上绘制自由格式墨迹注释的方法。它允许您使用手写笔或鼠标创建注释。当您需要绘制图表、草图或其他类型的注释时，此功能非常有用。

## 第 1 步：创建新文档

将墨迹注释添加到 PDF 文档的第一步是创建 Document 类的新实例。这是使用以下代码片段实现的：

```csharp
string dataDir = "YOUR DATA DIRECTORY";
Document doc = new Document();
Page pdfPage = doc.Pages.Add();
```

在这里，我们创建 Document 类的一个新实例并向其添加一个新页面。

## 第 2 步：创建墨迹注释

下一步是创建 InkAnnotation 类的实例。这是使用以下代码片段完成的：

```csharp
System.Drawing.Rectangle drect = new System.Drawing.Rectangle();
drect.Height = (int)pdfPage.Rect.Height;
drect.Width = (int)pdfPage.Rect.Width;
drect.X = 0;
drect.Y = 0;
Aspose.Pdf.Rectangle arect = Aspose.Pdf.Rectangle.FromRect(drect);
IList<Point[]> inkList = new List<Point[]>();
Aspose.Pdf.Point[] arrpt = new Aspose.Pdf.Point[3];
inkList.Add(arrpt);
arrpt[0] = new Aspose.Pdf.Point(100, 800);
arrpt[1] = new Aspose.Pdf.Point(200, 800);
arrpt[2] = new Aspose.Pdf.Point(200, 700);
InkAnnotation ia = new InkAnnotation(pdfPage, arect, inkList);
ia.Title = "XXX";
ia.Color = Aspose.Pdf.Color.LightBlue; // (GetColorFromString(笔划.InkColor));
ia.CapStyle = CapStyle.Rounded;
Border border = new Border(ia);
border.Width = 25;
ia.Opacity = 0.5;
pdfPage.Annotations.Add(ia);
```

在这里，我们首先使用 System.Drawing.Rectangle 类创建一个矩形，并使用 FromRect 方法将其转换为 Aspose.Pdf.Rectangle。然后，我们使用矩形、点列表以及添加注释的页面创建 InkAnnotation 类的实例。

然后，我们设置 InkAnnotation 的各种属性，例如标题、颜色、大头样式、边框和不透明度。最后，我们使用 Annotations.Add 方法将注释添加到页面。

## 第 3 步：保存文档

最后一步是保存添加了墨迹注释的 PDF 文档。这是使用以下代码片段实现的：

```csharp
dataDir = dataDir + "AddlnkAnnotation_out.pdf";
doc.Save(dataDir);
```

在这里，我们将输出文件名连接到数据目录，并使用 Save 方法保存文档。

### 使用 Aspose.PDF for .NET 添加墨迹注释的示例源代码

```csharp
//文档目录的路径。
string dataDir = "YOUR DATA DIRECTORY";


Document doc = new Document();
Page pdfPage = doc.Pages.Add();
System.Drawing.Rectangle drect = new System.Drawing.Rectangle();
drect.Height = (int)pdfPage.Rect.Height;
drect.Width = (int)pdfPage.Rect.Width;
drect.X = 0;
drect.Y = 0;
Aspose.Pdf.Rectangle arect = Aspose.Pdf.Rectangle.FromRect(drect);
IList<Point[]> inkList = new List<Point[]>();
Aspose.Pdf.Point[] arrpt = new Aspose.Pdf.Point[3];
inkList.Add(arrpt);
arrpt[0] = new Aspose.Pdf.Point(100, 800);
arrpt[1] = new Aspose.Pdf.Point(200, 800);
arrpt[2] = new Aspose.Pdf.Point(200, 700);
InkAnnotation ia = new InkAnnotation(pdfPage, arect, inkList);
ia.Title = "XXX";
ia.Color = Aspose.Pdf.Color.LightBlue; // (GetColorFromString(笔划.InkColor));
ia.CapStyle = CapStyle.Rounded;
Border border = new Border(ia);
border.Width = 25;
ia.Opacity = 0.5;
pdfPage.Annotations.Add(ia);

dataDir = dataDir + "AddlnkAnnotation_out.pdf";
//保存输出文件
doc.Save(dataDir);
```

## 结论

在本教程中，我们探讨了如何使用 Aspose.PDF for .NET 将墨迹注释添加到 PDF 文档。通过遵循提供的分步指南和 C# 源代码，开发人员可以轻松在 PDF 处理应用程序中实现墨迹注释功能。

### 常见问题解答

#### 问：什么是 PDF 文档中的墨迹注释？

答：PDF 文档中的墨迹注释允许用户使用手写笔或鼠标绘制自由格式的墨迹注释。它通常用于向 PDF 添加手绘草图、图表或其他手绘注释。

#### 问：我可以自定义墨迹注释的外观吗？

答：是的，Aspose.PDF for .NET 提供了各种属性来自定义墨迹注释的外观，例如颜色、不透明度、大头样式、边框宽度等。开发人员可以调整这些属性以满足他们的特定要求。

#### 问：是否可以将多个墨迹注释添加到单个 PDF 页面？

答：是的，您可以使用 Aspose.PDF for .NET 将多个墨迹注释添加到单个 PDF 页面。每个墨迹注释都可以有自己的一组点和自定义外观。

#### 问：我可以在现有 PDF 文档中添加墨迹注释吗？

答：是的，Aspose.PDF for .NET 允许您将墨迹注释添加到新创建的 PDF 文档和现有 PDF 文件中。您可以打开现有 PDF、添加墨迹注释并保存更新的文档。

#### 问：PDF 文档中墨迹注释有哪些常见用例？

答：墨迹注释适用于多种应用，包括向 PDF 表单添加签名或手写注释、注释建筑蓝图或工程图以及标记文档以供协作审阅。