---
title: 添加链接注释
linktitle: 添加链接注释
second_title: Aspose.PDF for .NET API 参考
description: 通过分步指南和完整源代码，了解如何使用 Aspose.PDF for .NET 在 C# 中向 PDF 文档添加墨迹注释功能。
type: docs
weight: 20
url: /zh/net/annotations/addlnkannotation/
---
Aspose.PDF for .NET 是一个功能强大的库，使开发人员能够执行各种 PDF 操作。其中一项操作是向 PDF 文档添加 Ink Annotation。在本文中，我们将提供一个分步指南来解释使用 Aspose.PDF for .NET 添加 Ink Annotation 的 C# 源代码。让我们开始吧！

## 了解 Aspose.PDF for .NET 的墨迹注释功能

在深入研究 C# 源代码之前，让我们先了解什么是 Ink Annotation 及其用途。

墨迹注释是一种在 PDF 文档上绘制自由形式墨迹注释的方法。它允许您使用手写笔或鼠标创建注释。此功能在您需要绘制图表、草图或其他类型的注释的情况下很有用。

## 第 1 步：创建新文档

将 Ink Annotation 添加到 PDF 文档的第一步是创建 Document 类的新实例。这是使用以下代码片段实现的：

```csharp
string dataDir = "YOUR DATA DIRECTORY";
Document doc = new Document();
Page pdfPage = doc.Pages.Add();
```

在这里，我们创建了 Document 类的一个新实例并向其添加了一个新页面。

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
ia.Color = Aspose.Pdf.Color.LightBlue; // (GetColorFromString(stroke.InkColor));
ia.CapStyle = CapStyle.Rounded;
Border border = new Border(ia);
border.Width = 25;
ia.Opacity = 0.5;
pdfPage.Annotations.Add(ia);
```

在这里，我们首先使用 System.Drawing.Rectangle 类创建一个矩形，然后使用 FromRect 方法将其转换为 Aspose.Pdf.Rectangle。然后，我们使用矩形、点列表和添加注释的页面创建 InkAnnotation 类的实例。

然后我们设置 InkAnnotation 的各种属性，例如标题、颜色、大写样式、边框和不透明度。最后，我们使用 Annotations.Add 方法将注释添加到页面。

## 第 3 步：保存文档

最后一步是保存添加了 Ink Annotation 的 PDF 文档。这是使用以下代码片段实现的：

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
ia.Color = Aspose.Pdf.Color.LightBlue; // (GetColorFromString(stroke.InkColor));
ia.CapStyle = CapStyle.Rounded;
Border border = new Border(ia);
border.Width = 25;
ia.Opacity = 0.5;
pdfPage.Annotations.Add(ia);

dataDir = dataDir + "AddlnkAnnotation_out.pdf";
//保存输出文件
doc.Save(dataDir);
```