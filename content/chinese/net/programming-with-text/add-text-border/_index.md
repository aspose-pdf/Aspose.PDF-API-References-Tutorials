---
title: 在 PDF 文件中添加文本边框
linktitle: 在 PDF 文件中添加文本边框
second_title: Aspose.PDF for .NET API 参考
description: 通过本分步指南了解如何使用 Aspose.PDF for .NET 在 PDF 文件中添加文本边框。增强您的 PDF 文档。
type: docs
weight: 70
url: /zh/net/programming-with-text/add-text-border/
---
## 介绍

在当今的数字世界中，创建和操作 PDF 文档已成为一项必备技能。无论您是生成报告、发票还是任何其他类型的文档，控制文本的显示方式都会产生重大影响。您可能想要实现的一项增强功能是在 PDF 文件中的文本周围添加边框。在本指南中，我们将引导您完成使用 .NET 的 Aspose.PDF 库在 PDF 文件中添加文本边框的步骤。那么，让我们开始吧！

## 先决条件

在我们开始之前，您需要准备好一些东西。别担心，这很简单！

1. Visual Studio：确保您的机器上安装了 Visual Studio。这将是您编写和运行代码的开发环境。
2.  Aspose.PDF for .NET：您需要下载并安装 Aspose.PDF 库。您可以从[Aspose PDF for .NET 下载页面](https://releases.aspose.com/pdf/net/)。如果你想先试用，你也可以获得[点击此处免费试用](https://releases.aspose.com/).
3. C# 基础知识：对 C# 编程语言的基本了解将帮助您轻松地理解示例。
4. .NET Framework：确保您已在项目中安装并设置 .NET Framework。

一旦满足了这些先决条件，您就可以开始编码了！

## 导入包

现在我们已经设置好了一切，让我们导入必要的包以在我们的项目中使用 Aspose.PDF。您可以通过在 C# 文件顶部添加以下使用指令来执行此操作：

```csharp
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;

```

这些命名空间将允许您有效地处理 PDF 文档和文本片段。 

现在，让我们将添加文本边框的过程分解为详细的步骤。我们将逐一介绍每个步骤，以便您准确了解幕后发生的情况。

## 步骤 1：设置文档

首先，我们需要创建一个新的 PDF 文档。这就是我们所有魔法发生的地方。

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//创建新的文档对象
Document pdfDocument = new Document();
```

在此步骤中，我们指定要保存 PDF 文件的目录。然后我们创建一个新的实例`Document`类，代表我们的 PDF 文档。

## 第 2 步：添加新页面

接下来，我们需要在文档中添加一页。可以将其视为添加一块空白画布，用于放置文本。

```csharp
//获取特定页面
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

在这里，我们称`Add()`方法`Pages`收集我们的`pdfDocument`对象。这会将新页面添加到文档中，我们将对它的引用存储在`pdfPage`多变的。

## 步骤 3：创建文本片段

现在，让我们创建要在 PDF 中显示的文本。这是我们定义文本片段内容的地方。

```csharp
//创建文本片段
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
```

在此代码中，我们创建一个新的`TextFragment`对象，文本为“主文本”。我们还使用`Position`类。坐标 (100, 600) 指定文本在页面上的放置位置。

## 步骤 4：设置文本属性

接下来，我们将自定义文本片段，使其具有视觉吸引力。这包括设置字体大小、字体类型、背景颜色和前景色。

```csharp
//设置文本属性
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
```

这里，我们将字体大小设置为 12，使用“Times New Roman”作为字体，并应用浅灰色背景颜色和红色文本。这些属性有助于增强文本的可见性。

## 步骤 5：设置边框的描边颜色

现在，我们进入激动人心的部分——在文本周围添加边框！

```csharp
//设置 StrokingColor 属性以在文本矩形周围绘制边框（描边）
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
```

在此步骤中，我们指定要在文本周围绘制的边框的颜色。这里，我们选择了深红色。

## 步骤 6：启用文本矩形边框

为了真正绘制文本周围的边框，我们需要启用`DrawTextRectangleBorder`财产。

```csharp
//将 DrawTextRectangleBorder 属性值设置为 true
textFragment.TextState.DrawTextRectangleBorder = true;
```

通过将此属性设置为`true`，我们告诉 Aspose.PDF 根据指定的描边颜色在文本矩形周围绘制边框。

## 步骤 7：将文本片段附加到页面

现在我们已经准备好了文本片段并设置了所有属性，是时候将其添加到页面了。

```csharp
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
```

在这里，我们创建一个`TextBuilder`与我们关联的对象`pdfPage`.然后我们使用`AppendText`方法添加我们的`textFragment`到页面。 

## 步骤 8：保存文档

最后，我们需要将 PDF 文档保存到指定的目录。这是关键时刻！

```csharp
//保存文档
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

在此步骤中，我们称`Save`方法`pdfDocument`对象，提供我们想要保存文件的路径。运行代码后，您应该会在指定目录中找到新创建的带有文本边框的 PDF！

## 结论

就这样！您已成功使用 Aspose.PDF for .NET 向 PDF 文件添加了文本边框。这个简单但功能强大的功能可以显著提高 PDF 文档的可读性和美观性。无论您是创建报告、小册子还是任何其他类型的文档，了解如何操作文本格式都会派上用场。

## 常见问题解答

### 什么是 Aspose.PDF for .NET？
Aspose.PDF for .NET 是一个功能强大的库，允许开发人员使用 .NET 框架以编程方式创建、操作和处理 PDF 文档。

### 我可以免费试用 Aspose.PDF 吗？
是的！Aspose 提供[免费试用](https://releases.aspose.com/)他们的 PDF 库，让您可以在购买之前测试其功能。

### 如何购买 Aspose.PDF for .NET？
您可以直接从他们的[购买页面](https://purchase.aspose.com/buy).

### 是否支持 Aspose.PDF？
当然！您可以通过访问[Aspose 支持论坛](https://forum.aspose.com/c/pdf/10).

### 如果我需要临时执照怎么办？
Aspose 提供了[临时执照](https://purchase.aspose.com/temporary-license/)适合需要在有限时间内评估该库的开发人员的选项。