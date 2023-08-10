---
title: 搜索文本段页面
linktitle: 搜索文本段页面
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 文档页面上搜索文本段并检索其属性。
type: docs
weight: 470
url: /zh/net/programming-with-text/search-text-segments-page/
---

本教程介绍如何使用 Aspose.PDF for .NET 搜索 PDF 文档页面上的特定文本段并检索其属性。提供的 C# 源代码逐步演示了该过程。

## 先决条件

在继续学习本教程之前，请确保您具备以下条件：

- C# 编程语言的基础知识。
- 安装了 Aspose.PDF for .NET 库。您可以从 Aspose 网站获取它或使用 NuGet 将其安装到您的项目中。

## 第 1 步：设置项目

首先在您首选的集成开发环境 (IDE) 中创建一个新的 C# 项目，并添加对 Aspose.PDF for .NET 库的引用。

## 第2步：导入必要的命名空间

在 C# 文件的开头添加以下 using 指令以导入所需的命名空间：

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## 第三步：设置文档目录路径

使用以下命令设置文档目录的路径`dataDir`多变的：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

代替`"YOUR DOCUMENT DIRECTORY"`与文档目录的实际路径。

## 第 4 步：加载 PDF 文档

使用加载 PDF 文档`Document`班级：

```csharp
Document pdfDocument = new Document(dataDir + "SearchTextSegmentsPage.pdf");
```

代替`"SearchTextSegmentsPage.pdf"`与您的 PDF 文件的实际名称。

## 第5步：创建一个TextFragmentAbsorber

创建一个`TextFragmentAbsorber`对象查找输入搜索短语的所有实例：

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
```

代替`"text"`与您想要的搜索短语。

## 第 6 步：接受特定页面的吸收器

接受文档所需页面的吸收器：

```csharp
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
```

代替`2`与所需的页码（从 1 开始的索引）。

## 步骤 7：检索提取的文本片段

使用以下命令获取提取的文本片段`TextFragments`的财产`TextFragmentAbsorber`目的：

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## 第 8 步：循环文本段

循环检索到的文本段并访问它们的属性：

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
		Console.WriteLine("Text: {0} ", textSegment.Text);
		Console.WriteLine("Position: {0} ", textSegment.Position);
		Console.WriteLine("XIndent: {0} ", textSegment.Position.XIndent);
		Console.WriteLine("YIndent: {0} ", textSegment.Position.YIndent);
		Console.WriteLine("Font - Name: {0}", textSegment.TextState.Font.FontName);
		Console.WriteLine("Font - IsAccessible: {0} ", textSegment.TextState.Font.IsAccessible);
		Console.WriteLine("Font - IsEmbedded: {0} ", textSegment.TextState.Font.IsEmbedded);
		Console.WriteLine("Font - IsSubset: {0} ", textSegment.TextState.Font.IsSubset);
		Console.WriteLine("Font Size: {0} ", textSegment.TextState.FontSize);
		Console.WriteLine("Foreground Color: {0} ", textSegment.TextState.ForegroundColor);
	}
}
```

如果需要，修改循环内的代码以对每个文本段执行进一步的操作。

### 使用 Aspose.PDF for .NET 搜索文本段页面的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//打开文档
Document pdfDocument = new Document(dataDir + "SearchTextSegmentsPage.pdf");
//创建 TextAbsorber 对象以查找输入搜索短语的所有实例
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("text");
//接受所有页面的吸收器
pdfDocument.Pages[2].Accept(textFragmentAbsorber);
//获取提取的文本片段
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
//循环遍历片段
foreach (TextFragment textFragment in textFragmentCollection)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
		Console.WriteLine("Text : {0} ", textSegment.Text);
		Console.WriteLine("Position : {0} ", textSegment.Position);
		Console.WriteLine("XIndent : {0} ",
		textSegment.Position.XIndent);
		Console.WriteLine("YIndent : {0} ",
		textSegment.Position.YIndent);
		Console.WriteLine("Font - Name : {0}",
		textSegment.TextState.Font.FontName);
		Console.WriteLine("Font - IsAccessible : {0} ",
		textSegment.TextState.Font.IsAccessible);
		Console.WriteLine("Font - IsEmbedded : {0} ",
		textSegment.TextState.Font.IsEmbedded);
		Console.WriteLine("Font - IsSubset : {0} ",
		textSegment.TextState.Font.IsSubset);
		Console.WriteLine("Font Size : {0} ",
		textSegment.TextState.FontSize);
		Console.WriteLine("Foreground Color : {0} ",
		textSegment.TextState.ForegroundColor);
	}
}
```

## 结论

恭喜！您已成功学习如何使用 Aspose.PDF for .NET 在 PDF 文档页面上搜索特定文本段。本教程提供了从加载文档到访问提取的文本段的分步指南。您现在可以将此代码合并到您自己的 C# 项目中，以在 PDF 文件中执行高级文本段搜索。