---
title: 创建多层 PDF 的第一种方法
linktitle: 创建多层 PDF 的第一种方法
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 的第一种方法创建多层 PDF 文档。添加文本、图像等以增强您的 PDF。
type: docs
weight: 70
url: /zh/net/programming-with-document/createmultilayerpdffirstapproach/
---

在本教程中，我们将指导您使用 Aspose.PDF for .NET 使用第一种方法创建多层 PDF。这种方法允许您向 PDF 文档添加多个图层。请按照以下分步指南操作：

## 第 1 步：初始化 PDF 文档

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();
```

## 第 2 步：向文档添加新页面

```csharp
Aspose.Pdf.Page sec1 = pdf.Pages.Add();
```

## 第 3 步：向页面添加文本片段

```csharp
Aspose.Pdf.Text.TextFragment t1 = new Aspose.Pdf.Text.TextFragment("paragraph 3 segment");
sec1.Paragraphs.Add(t1);
```

## 第 4 步：自定义文本片段

```csharp
t1.Text = "paragraph 3 segment 1";
t1.TextState.ForegroundColor = Color.Red;
t1.TextState.FontSize = 12;
```

## 第 5 步：将图像添加到页面

```csharp
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
image1.File = dataDir + "test_image.png";
```

## 第六步：给页面添加浮动框

```csharp
Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(117, 21);
sec1.Paragraphs.Add(box1);

box1.Left = -4;
box1.Top = -4;
box1.Paragraphs.Add(image1);
```

## 步骤 7：保存生成的 PDF 文档

```csharp
pdf.Save(dataDir + "CreateMultiLayerPdf_out.pdf");
```

恭喜！您已经使用 Aspose.PDF for .NET 使用第一种方法成功创建了一个多层 PDF 文档。

### Create Multilayer PDF First Approach using Aspose.PDF for .NET 的示例源代码：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();
Aspose.Pdf.Page sec1 = pdf.Pages.Add();
Aspose.Pdf.Text.TextFragment t1 = new Aspose.Pdf.Text.TextFragment("paragraph 3 segment");
sec1.Paragraphs.Add(t1);

t1.Text = "paragraph 3 segment 1";
t1.TextState.ForegroundColor = Color.Red;
t1.TextState.FontSize = 12;

Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
image1.File = dataDir + "test_image.png";

Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(117, 21);
sec1.Paragraphs.Add(box1);

box1.Left = -4;
box1.Top = -4;
box1.Paragraphs.Add(image1);

pdf.Save(dataDir + "CreateMultiLayerPdf_out.pdf");
```

现在您可以使用 Aspose.PDF for .NET 使用第一种方法创建多层 PDF 文档。
