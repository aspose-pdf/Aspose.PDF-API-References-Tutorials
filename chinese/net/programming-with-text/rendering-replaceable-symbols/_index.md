---
title: 渲染可替换符号
linktitle: 渲染可替换符号
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 文档中呈现可替换符号。
type: docs
weight: 310
url: /zh/net/programming-with-text/rendering-replaceable-symbols/
---

在本教程中，我们将解释如何使用 .NET 的 Aspose.PDF 库在 PDF 文档中呈现可替换符号。我们将逐步完成创建 PDF、添加带有换行符标记的文本片段、设置文本属性、定位文本以及使用提供的 C# 源代码保存 PDF 的过程。

## 先决条件

在开始之前，请确保您具备以下条件：

- 安装了 Aspose.PDF for .NET 库。
- 对 C# 编程有基本了解。

## 第 1 步：设置文档目录

首先，您需要设置要保存生成的 PDF 文件的目录路径。代替`"YOUR DOCUMENT DIRECTORY"`在里面`dataDir`变量包含您所需目录的路径。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：创建 PDF 文档和页面

接下来，我们创建一个新的 PDF 文档并使用以下命令向其中添加页面`Document`类和`Page`来自 Aspose.PDF 库的类。

```csharp
Aspose.Pdf.Document pdfApplicationDoc = new Aspose.Pdf.Document();
Aspose.Pdf.Page applicationFirstPage = (Aspose.Pdf.Page)pdfApplicationDoc.Pages.Add();
```

## 第 3 步：添加带有换行标记的文本片段

我们创建一个`TextFragment`对象并设置其文本以包含换行符（`Environment.NewLine`) 来表示多行文本。

```csharp
Aspose.Pdf.Text.TextFragment textFragment = new Aspose.Pdf.Text.TextFragment("Applicant Name: " + Environment.NewLine + " Joe Smoe");
```

## 步骤 4：设置文本片段属性

如果需要，我们可以为文本片段设置各种属性，例如字体大小、字体、背景颜色和前景色。

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
```

## 第5步：创建文本段落和位置

我们创建一个`TextParagraph`对象，将文本片段附加到段落中，并设置段落在页面上的位置。

```csharp
TextParagraph par = new TextParagraph();
par.AppendLine(textFragment);
par.Position = new Aspose.Pdf.Text.Position(100, 600);
```

## 第 6 步：将文本段落添加到页面

我们创建一个`TextBuilder`对象与页面并将文本段落附加到文本生成器。

```csharp
TextBuilder textBuilder = new TextBuilder(applicationFirstPage);
textBuilder.AppendParagraph(par);
```

## 第7步：保存PDF文档

最后，我们将PDF文档保存到指定的输出文件中。

```csharp
dataDir = dataDir + "RenderingReplaceableSymbols_out.pdf";
pdfApplicationDoc.Save(dataDir);
Console.WriteLine("\nReplaceable symbols rendered successfully during PDF creation.\nFile saved at " + dataDir);
```

### 使用 Aspose.PDF for .NET 渲染可替换符号的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Document pdfApplicationDoc = new Aspose.Pdf.Document();
Aspose.Pdf.Page applicationFirstPage = (Aspose.Pdf.Page)pdfApplicationDoc.Pages.Add();
//使用包含所需换行标记的文本初始化新的 TextFragment
Aspose.Pdf.Text.TextFragment textFragment = new Aspose.Pdf.Text.TextFragment("Applicant Name: " + Environment.NewLine + " Joe Smoe");
//如有必要，设置文本片段属性
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
//创建 TextParagraph 对象
TextParagraph par = new TextParagraph();
//添加新的 TextFragment 到段落
par.AppendLine(textFragment);
//设置段落位置
par.Position = new Aspose.Pdf.Text.Position(100, 600);
//创建 TextBuilder 对象
TextBuilder textBuilder = new TextBuilder(applicationFirstPage);
//使用 TextBuilder 添加 TextParagraph
textBuilder.AppendParagraph(par);
dataDir = dataDir + "RenderingReplaceableSymbols_out.pdf";
pdfApplicationDoc.Save(dataDir);
Console.WriteLine("\nReplaceable symbols render successfully duing pdf creation.\nFile saved at " + dataDir);
```

## 结论

在本教程中，您学习了如何使用 .NET 的 Aspose.PDF 库在 PDF 文档中呈现可替换符号。通过遵循分步指南并执行提供的 C# 代码，您可以创建 PDF、添加带有换行符标记的文本、设置文本属性、在页面上放置文本以及保存 PDF。