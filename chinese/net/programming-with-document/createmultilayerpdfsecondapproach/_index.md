---
title: 创建多层 PDF 第二种方法
linktitle: 创建多层 PDF 第二种方法
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 创建多层 PDF。带有源代码的分步指南，用于创建带有文本和图像的动态 PDF。
type: docs
weight: 80
url: /zh/net/programming-with-document/createmultilayerpdfsecondapproach/
---

在本教程中，我们将探索如何使用 Aspose.PDF for .NET 中的第二种方法创建多层 PDF。我们将提供带有详细解释的分步指南，并包括完整的源代码。按照本教程，您将能够在 .NET 应用程序中使用 Aspose.PDF 库生成具有多层的 PDF 文档。

现在，让我们开始使用分步指南。

## 第 1 步：设置环境

首先，打开 Visual Studio 并创建一个新的 C# 项目。确保您在项目中引用了 Aspose.PDF 库。设置好环境后，就可以进行下一步了。

## 第 2 步：初始化变量

在这一步中，我们将初始化必要的变量。我们需要设置文档目录的路径并为 PDF 层定义颜色变量。这是代码片段：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

int alpha = 10;
int green = 0;
int red = 100;
int blue = 0;
Color alphaColor = Color.FromArgb(alpha, red, green, blue);
```

## 第 3 步：创建 PDF 文档

接下来，我们将创建一个 Aspose.Pdf.Document 类的新实例，它表示一个 PDF 文档。这是代码片段：

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

## 第 4 步：向文档添加页面

在这一步中，我们将向 PDF 文档添加一个新页面。这是代码片段：

```csharp
Aspose.Pdf.Page page = doc.Pages.Add();
```

## 第 5 步：向页面添加文本

现在，我们将向页面添加一个文本片段。文本将显示为红色的第 3 段。这是代码片段：

```csharp
Aspose.Pdf.Text.TextFragment t1 = new Aspose.Pdf.Text.TextFragment("paragraph 3 segment");
t1.TextState.ForegroundColor = Color.Red;
t1.IsInLineParagraph = true;
t1.TextState.FontSize = 12;

Aspose.Pdf.FloatingBox TextFloatingBox1 = new Aspose.Pdf.FloatingBox(117, 21);
TextFloatingBox1.ZIndex = 1;
TextFloatingBox1.Left = -4;
TextFloatingBox1.Top = -4;
page.Paragraphs.Add(TextFloatingBox1);
TextFloatingBox1.Paragraphs.Add(t1);
```

## 第 6 步：将图像添加到页面

在此步骤中，我们将向页面添加图像。图像将定位为具有特定大小的浮动框。这是代码片段：

```csharp
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
image1.File = dataDir + "test_image.png";

Aspose.Pdf.FloatingBox ImageFloatingBox = new Aspose.Pdf.FloatingBox(117, 21);
page.Paragraphs.Add(ImageFloatingBox);
ImageFloatingBox.Left = -4;
ImageFloatingBox.Top = -4;
ImageFloatingBox.ZIndex = 2;
ImageFloatingBox.Paragraphs.Add(image1);
```

## 第 7 步：保存 PDF

在此步骤中，我们会将 PDF 保存到文件中。

```
doc.Save(dataDir + @"Multilayer-2ndApproach_out.pdf");
```

### 使用 Aspose.PDF for .NET 创建多层 PDF 第二种方法的示例源代码。

```csharp

            
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

int alpha = 10;
int green = 0;
int red = 100;
int blue = 0;
Color alphaColor = Color.FromArgb(alpha, red, green, blue);
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

Aspose.Pdf.Page page = doc.Pages.Add();
Aspose.Pdf.Text.TextFragment t1 = new Aspose.Pdf.Text.TextFragment("paragraph 3 segment");
t1.TextState.ForegroundColor = Color.Red;
t1.IsInLineParagraph = true;
t1.TextState.FontSize = 12;
Aspose.Pdf.FloatingBox TextFloatingBox1 = new Aspose.Pdf.FloatingBox(117, 21);
TextFloatingBox1.ZIndex = 1;
TextFloatingBox1.Left = -4;
TextFloatingBox1.Top = -4;
page.Paragraphs.Add(TextFloatingBox1);
TextFloatingBox1.Paragraphs.Add(t1);
Aspose.Pdf.Image image1 = new Aspose.Pdf.Image();
image1.File = dataDir + "test_image.png";
Aspose.Pdf.FloatingBox ImageFloatingBox = new Aspose.Pdf.FloatingBox(117, 21);
page.Paragraphs.Add(ImageFloatingBox);

ImageFloatingBox.Left = -4;
ImageFloatingBox.Top = -4;
ImageFloatingBox.ZIndex = 2;
ImageFloatingBox.Paragraphs.Add(image1);

doc.Save(dataDir + @"Multilayer-2ndApproach_out.pdf");
            
        
```

## 结论

在本文中，我们学习了如何使用 Aspose.PDF for .NET 的第二种方法创建多层 PDF。我们为您提供了创建多层 PDF 所需的分步说明和完整源代码。