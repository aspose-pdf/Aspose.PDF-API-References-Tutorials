---
title: 全部替换文本
linktitle: 全部替换文本
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 替换 PDF 文档中的所有文本。
type: docs
weight: 350
url: /zh/net/programming-with-text/replace-text-all/
---

在本教程中，我们将解释如何使用 .NET 的 Aspose.PDF 库替换 PDF 文档中的所有文本。我们将提供分步指南以及必要的 C# 源代码。

## 先决条件

在开始之前，请确保您具备以下条件：

- 安装了 Aspose.PDF for .NET 库。
- 对 C# 编程有基本了解。

## 第 1 步：设置文档目录

将路径设置为输入 PDF 文件所在的目录。代替`"YOUR DOCUMENT DIRECTORY"`在里面`dataDir`变量包含 PDF 文件的路径。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：加载 PDF 文档

使用加载 PDF 文档`Document`来自 Aspose.PDF 库的类。

```csharp
Document pdfDocument = new Document(dataDir + "ReplaceTextAll.pdf");
```

## 第 3 步：搜索并替换文本

创建一个`TextFragmentAbsorber`对象查找输入搜索短语的所有实例。接受 PDF 文档所有页面的吸收器以提取文本片段。

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## 第 4 步：替换文本

循环遍历提取的文本片段并根据需要替换文本。更新文本和其他属性，例如字体、字体大小、前景色和背景色。

```csharp
foreach (TextFragment textFragment in textFragmentAbsorber.TextFragments)
{
    textFragment.Text = "TEXT";
    textFragment.TextState.Font = FontRepository.FindFont("Verdana");
    textFragment.TextState.FontSize = 22;
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
    textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
}
```

## 第5步：保存修改后的PDF

将修改后的PDF文档保存到指定的输出文件。

```csharp
dataDir = dataDir + "ReplaceTextAll_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nText replaced successfully.\nFile saved at " + dataDir);
```

### 使用 Aspose.PDF for .NET 替换全部文本的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//打开文档
Document pdfDocument = new Document(dataDir + "ReplaceTextAll.pdf");
//创建 TextAbsorber 对象以查找输入搜索短语的所有实例
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
//接受所有页面的吸收器
pdfDocument.Pages.Accept(textFragmentAbsorber);
//获取提取的文本片段
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
//循环遍历片段
foreach (TextFragment textFragment in textFragmentCollection)
{
	//更新文本和其他属性
	textFragment.Text = "TEXT";
	textFragment.TextState.Font = FontRepository.FindFont("Verdana");
	textFragment.TextState.FontSize = 22;
	textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Blue);
	textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
}
dataDir = dataDir + "ReplaceTextAll_out.pdf";
//保存生成的 PDF 文档。
pdfDocument.Save(dataDir);
Console.WriteLine("\nText replaced  successfully.\nFile saved at " + dataDir);
```

## 结论

在本教程中，您学习了如何使用 .NET 的 Aspose.PDF 库替换 PDF 文档中的所有文本。通过遵循分步指南并执行提供的 C# 代码，您可以加载 PDF 文档、搜索所需文本、替换它并保存修改后的 PDF。