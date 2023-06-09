---
title: 搜索正则表达式
linktitle: 搜索正则表达式
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 文档中使用正则表达式搜索和检索文本。
type: docs
weight: 440
url: /zh/net/programming-with-text/search-regular-expression/
---

本教程解释了如何使用 Aspose.PDF for .NET 来搜索和检索与 PDF 文档中的正则表达式匹配的文本。提供的 C# 源代码逐步演示了该过程。

## 先决条件

在继续本教程之前，请确保您具有以下内容：

- C# 编程语言的基础知识。
- 安装了 Aspose.PDF for .NET 库。您可以从 Aspose 网站获取它或使用 NuGet 将其安装到您的项目中。

## 第 1 步：设置项目

首先在您首选的集成开发环境 (IDE) 中创建一个新的 C# 项目，并添加对 Aspose.PDF for .NET 库的引用。

## 第 2 步：导入必要的命名空间

在 C# 文件的开头添加以下 using 指令以导入所需的命名空间：

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## 第 3 步：加载 PDF 文档

设置 PDF 文档目录的路径并使用`Document`班级：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionAll.pdf");
```

确保更换`"YOUR DOCUMENT DIRECTORY"`使用文档目录的实际路径。

## 第 4 步：使用正则表达式搜索

创建一个`TextFragmentAbsorber`对象并设置正则表达式模式以查找与该模式匹配的所有短语：

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); //就像 1999-2000
```

代替`"\\d{4}-\\d{4}"`使用您想要的正则表达式模式。

## 第 5 步：设置文本搜索选项

创建一个`TextSearchOptions`对象并将其设置为`TextSearchOptions`的财产`TextFragmentAbsorber`启用正则表达式用法的对象：

```csharp
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
```

## 第 6 步：在所有页面上搜索

接受文档所有页面的吸收器：

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## 第 7 步：检索提取的文本片段

使用获取提取的文本片段`TextFragments`的财产`TextFragmentAbsorber`目的：

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## 第 8 步：循环遍历文本片段

遍历检索到的文本片段并访问它们的属性：

```csharp
foreach (TextFragment textFragment in textFragmentCollection)
{
	Console.WriteLine("Text: {0} ", textFragment.Text);
	Console.WriteLine("Position: {0} ", textFragment.Position);
	Console.WriteLine("XIndent: {0} ", textFragment.Position.XIndent);
	Console.WriteLine("YIndent: {0} ", textFragment.Position.YIndent);
	Console.WriteLine("Font - Name: {0}", textFragment.TextState.Font.FontName);
	Console.WriteLine("Font - IsAccessible: {0} ", textFragment.TextState.Font.IsAccessible);
	Console.WriteLine("Font - IsEmbedded: {0} ", textFragment.TextState.Font.IsEmbedded);
	Console.WriteLine("Font - IsSubset: {0} ", textFragment.TextState.Font.IsSubset);
	Console.WriteLine("Font Size: {0} ", textFragment.TextState.FontSize);
	Console.WriteLine("Foreground Color: {0} ", textFragment.TextState.ForegroundColor);
}
```

您可以修改循环内的代码以对每个文本片段执行进一步的操作。

### 使用 Aspose.PDF for .NET 搜索正则表达式的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//打开文档
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionAll.pdf");
//创建 TextAbsorber 对象以查找与正则表达式匹配的所有短语
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); //就像 1999-2000
//设置文本搜索选项以指定正则表达式用法
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
//接受所有页面的吸收器
pdfDocument.Pages.Accept(textFragmentAbsorber);
//获取提取的文本片段
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
//遍历片段
foreach (TextFragment textFragment in textFragmentCollection)
{
	Console.WriteLine("Text : {0} ", textFragment.Text);
	Console.WriteLine("Position : {0} ", textFragment.Position);
	Console.WriteLine("XIndent : {0} ", textFragment.Position.XIndent);
	Console.WriteLine("YIndent : {0} ", textFragment.Position.YIndent);
	Console.WriteLine("Font - Name : {0}", textFragment.TextState.Font.FontName);
	Console.WriteLine("Font - IsAccessible : {0} ", textFragment.TextState.Font.IsAccessible);
	Console.WriteLine("Font - IsEmbedded : {0} ", textFragment.TextState.Font.IsEmbedded);
	Console.WriteLine("Font - IsSubset : {0} ", textFragment.TextState.Font.IsSubset);
	Console.WriteLine("Font Size : {0} ", textFragment.TextState.FontSize);
	Console.WriteLine("Foreground Color : {0} ", textFragment.TextState.ForegroundColor);
}
```

## 结论

恭喜！您已经成功学习了如何使用 Aspose.PDF for .NET 在 PDF 文档中搜索和检索与正则表达式匹配的文本。本教程提供了从加载文档到访问提取的文本片段的分步指南。您现在可以将此代码合并到您自己的 C# 项目中，以在 PDF 文件中执行高级文本搜索。