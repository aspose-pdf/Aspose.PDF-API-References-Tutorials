---
title: 添加图层
linktitle: 添加图层
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 向 PDF 文件添加图层。包含用于创建和保存分层 PDF 的代码教程的分步指南。
type: docs
weight: 20
url: /zh/net/programming-with-document/addlayers/
---

要向 PDF 文件添加图层，我们将使用 Aspose.PDF for .NET。该库允许我们在 .NET 应用程序中有效地处理 PDF 文件。按照下面的分步说明使用 Aspose.PDF for .NET 添加图层。

## 步骤 1：创建一个新的 PDF 文档

首先创建一个新的实例`Document`Aspose.PDF for .NET 提供的类。这将用作我们将在其中添加图层的 PDF 文档。

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
```

## 第 2 步：向文档添加页面

接下来，使用`Add`的方法`Pages`收集在`Document`班级。

```csharp
Page page = doc.Pages.Add();
```

## 第 3 步：创建图层并将其添加到页面

创建实例`Layer`您要添加到 PDF 文件的每个图层的类。为每一层指定唯一标识符和名称。

```csharp
Layer layer = new Layer("oc1", "Red Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(1, 0, 0));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 700));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 700));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers = new List<Layer>();
page.Layers.Add(layer);

layer = new Layer("oc2", "Green Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(0, 1, 0));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 750));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 750));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers.Add(layer);

layer = new Layer("oc3", "Blue Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(0, 0, 1));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 800));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 800));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers.Add(layer);
```

在本教程中，我们在页面中添加了三个具有不同颜色和名称的图层。

## 第 4 步：保存 PDF 文件

使用保存修改后的 PDF 文件`Save`的方法`Document`班级。

```csharp
dataDir = dataDir + "AddLayers_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nLayers added successfully to PDF file.\nFile saved at " + dataDir);
```

此代码会将修改后的 PDF 文件保存到指定目录。

### 使用 Aspose.PDF for .NET 向 PDF 页面添加图层的示例源代码

```csharp            
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
Page page = doc.Pages.Add();
Layer layer = new Layer("oc1", "Red Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(1, 0, 0));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 700));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 700));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers = new  List<Layer>();
page.Layers.Add(layer);
layer = new Layer("oc2", "Green Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(0, 1, 0));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 750));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 750));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers.Add(layer);
layer = new Layer("oc3", "Blue Line");
layer.Contents.Add(new Aspose.Pdf.Operators.SetRGBColorStroke(0, 0, 1));
layer.Contents.Add(new Aspose.Pdf.Operators.MoveTo(500, 800));
layer.Contents.Add(new Aspose.Pdf.Operators.LineTo(400, 800));
layer.Contents.Add(new Aspose.Pdf.Operators.Stroke());
page.Layers.Add(layer);
dataDir = dataDir + "AddLayers_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nLayers added successfully to PDF file.\nFile saved at " + dataDir);

```

## 结论

在本文中，我们提供了使用 Aspose.PDF for .NET 向 PDF 文件添加图层的分步指南。按照说明并利用提供的代码教程，您可以轻松地将图层合并到 PDF 文档中。层允许您组织和控制内容的可见性，为您的用户提供更具交互性和可定制性的体验。