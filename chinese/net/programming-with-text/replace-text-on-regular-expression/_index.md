---
title: 替换正则表达式上的文本
linktitle: 替换 Texton 正则表达式
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 根据正则表达式替换 PDF 文档中的文本。
type: docs
weight: 360
url: /zh/net/programming-with-text/replace-text-on-regular-expression/
---

在本教程中，我们将解释如何使用 .NET 的 Aspose.PDF 库根据 PDF 文档中的正则表达式替换文本。我们将提供分步指南以及必要的 C# 源代码。

## 先决条件

在开始之前，请确保您具备以下条件：

- 安装了 Aspose.PDF for .NET 库。
- 基本了解 C# 编程。

## 第 1 步：设置文档目录

将路径设置为您拥有输入 PDF 文件的目录。代替`"YOUR DOCUMENT DIRECTORY"`在里面`dataDir`带有 PDF 文件路径的变量。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：加载 PDF 文档

使用`Document` Aspose.PDF 库中的类。

```csharp
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionPage.pdf");
```

## 第 3 步：使用正则表达式搜索和替换文本

创建一个`TextFragmentAbsorber`对象并指定正则表达式模式以查找与该模式匹配的所有短语。设置文本搜索选项以启用正则表达式使用。

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); //就像 1999-2000
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
pdfDocument.Pages[1].Accept(textFragmentAbsorber);
```

## 第 4 步：替换文本

遍历提取的文本片段并根据需要替换文本。更新文本和其他属性，例如字体、字体大小、前景色和背景色。

```csharp
foreach (TextFragment textFragment in textFragmentAbsorber.TextFragments)
{
    textFragment.Text = "New Phrase";
    textFragment.TextState.Font = FontRepository.FindFont("Verdana");
    textFragment.TextState.FontSize = 22;
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
    textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
}
```

## 第 5 步：保存修改后的 PDF

将修改后的 PDF 文档保存到指定的输出文件。

```csharp
dataDir = dataDir + "ReplaceTextonRegularExpression_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nText replaced successfully based on a regular expression.\nFile saved at " + dataDir);
```

### 使用 Aspose.PDF for .NET 替换 Texton 正则表达式的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//打开文档
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionPage.pdf");
//创建 TextAbsorber 对象以查找与正则表达式匹配的所有短语
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); //就像 1999-2000
//设置文本搜索选项以指定正则表达式用法
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
//接受单个页面的吸收器
pdfDocument.Pages[1].Accept(textFragmentAbsorber);
//获取提取的文本片段
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
//遍历片段
foreach (TextFragment textFragment in textFragmentCollection)
{
	//更新文本和其他属性
	textFragment.Text = "New Phrase";
	//设置为对象的实例。
	textFragment.TextState.Font = FontRepository.FindFont("Verdana");
	textFragment.TextState.FontSize = 22;
	textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
	textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
}
dataDir = dataDir + "ReplaceTextonRegularExpression_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nText replaced successfully based on a regular expression.\nFile saved at " + dataDir);
```

## 结论

在本教程中，您学习了如何使用 .NET 的 Aspose.PDF 库根据 PDF 文档中的正则表达式替换文本。按照分步指南并执行提供的 C# 代码，您可以加载 PDF 文档、使用正则表达式搜索文本、替换文本并保存修改后的 PDF。