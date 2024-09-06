---
title: 在 PDF 文件中搜索正则表达式
linktitle: 在 PDF 文件中搜索正则表达式
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 文件中使用正则表达式搜索和检索文本。
type: docs
weight: 440
url: /zh/net/programming-with-text/search-regular-expression/
---
本教程讲解如何使用 Aspose.PDF for .NET 在 PDF 文件中搜索和检索与正则表达式匹配的文本。提供的 C# 源代码逐步演示了该过程。

## 先决条件

在继续本教程之前，请确保您已具备以下条件：

- C# 编程语言的基本知识。
- 已安装 Aspose.PDF for .NET 库。您可以从 Aspose 网站获取它，也可以使用 NuGet 将其安装在您的项目中。

## 步骤 1：设置项目

首先在您首选的集成开发环境 (IDE) 中创建一个新的 C# 项目，并添加对 Aspose.PDF for .NET 库的引用。

## 第 2 步：导入必要的命名空间

在 C# 文件的开头添加以下使用指令来导入所需的命名空间：

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## 步骤 3：加载 PDF 文档

设置 PDF 文档目录的路径，然后使用`Document`班级：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "SearchRegularExpressionAll.pdf");
```

确保更换`"YOUR DOCUMENT DIRECTORY"`使用您的文档目录的实际路径。

## 步骤 4：使用正则表达式搜索

创建一个`TextFragmentAbsorber`对象并设置正则表达式模式来查找与模式匹配的所有短语：

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); //比如 1999-2000 年
```

代替`"\\d{4}-\\d{4}"`使用您想要的正则表达式模式。

## 步骤 5：设置文本搜索选项

创建一个`TextSearchOptions`对象并将其设置为`TextSearchOptions`的财产`TextFragmentAbsorber`对象来启用正则表达式的使用：

```csharp
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
```

## 步骤 6：在所有页面上搜索

接受文档所有页面的吸收器：

```csharp
pdfDocument.Pages.Accept(textFragmentAbsorber);
```

## 步骤 7：检索提取的文本片段

使用获取提取的文本片段`TextFragments`的财产`TextFragmentAbsorber`目的：

```csharp
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
```

## 步骤 8：循环遍历文本片段

循环遍历检索到的文本片段并访问其属性：

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
//创建 TextAbsorber 对象来查找与正则表达式匹配的所有短语
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("\\d{4}-\\d{4}"); //比如 1999-2000 年
//设置文本搜索选项以指定正则表达式的使用
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textFragmentAbsorber.TextSearchOptions = textSearchOptions;
//接受所有页面的吸收器
pdfDocument.Pages.Accept(textFragmentAbsorber);
//获取提取的文本片段
TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;
//循环遍历片段
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

恭喜！您已成功学习了如何使用 Aspose.PDF for .NET 在 PDF 文档中搜索和检索与正则表达式匹配的文本。本教程提供了分步指南，从加载文档到访问提取的文本片段。您现在可以将此代码合并到自己的 C# 项目中，以在 PDF 文件中执行高级文本搜索。

### 常见问题解答

#### 问：《在 PDF 文件中搜索正则表达式》教程的目的是什么？

答：“在 PDF 文件中搜索正则表达式”教程旨在展示如何使用 .NET 的 Aspose.PDF 库在 PDF 文件中搜索和提取与指定正则表达式模式匹配的文本。该教程提供了全面的指导和示例 C# 代码来演示该过程。

#### 问：本教程如何帮助您在 PDF 文档中使用正则表达式搜索文本？

答：本教程提供了使用 Aspose.PDF 库根据正则表达式模式在 PDF 文档中进行文本搜索的分步方法。它详细介绍了如何设置项目、加载 PDF 文档、定义正则表达式模式以及检索匹配的文本片段。

#### 问：学习本教程的先决条件是什么？

答：在开始本教程之前，您应该对 C# 编程语言有基本的了解。此外，您还需要安装 Aspose.PDF for .NET 库。您可以从 Aspose 网站获取它，也可以使用 NuGet 将其集成到您的项目中。

#### 问：如何设置我的项目来遵循本教程？

答：首先，在您首选的集成开发环境 (IDE) 中创建一个新的 C# 项目，并添加对 Aspose.PDF for .NET 库的引用。这将允许您在项目中利用该库的功能。

#### 问：我可以使用正则表达式在 PDF 文档中搜索文本吗？

答：是的，本教程演示了如何使用正则表达式从 PDF 文档中搜索和提取文本。它涉及利用`TextFragmentAbsorber`类并指定正则表达式模式来查找与提供的模式匹配的短语。

#### 问：如何定义文本搜索的正则表达式模式？

答：要定义用于文本搜索的正则表达式模式，请创建一个`TextFragmentAbsorber`对象并使用设置其模式`Text`参数。替换默认模式`"\\d{4}-\\d{4}"`在教程的代码中使用您想要的正则表达式模式。

#### 问：如何启用正则表达式进行文本搜索？

答：通过创建`TextSearchOptions`对象并将其值设置为`true` 将此对象分配给`TextSearchOptions`的财产`TextFragmentAbsorber`实例。这可确保在文本搜索期间应用正则表达式模式。

#### 问：我可以检索与正则表达式模式匹配的文本片段吗？

答：当然可以。在 PDF 文档上应用正则表达式搜索后，您可以使用`TextFragments`的财产`TextFragmentAbsorber`对象。这些文本片段包含与指定的正则表达式模式匹配的文本段。

#### 问：从检索到的文本片段中我可以访问什么？

答：从检索到的文本片段中，您可以访问各种属性，例如匹配的文本内容、位置（X 和 Y 坐标）、字体信息（名称、大小、颜色）等。本教程循环中的示例代码演示了如何访问和显示这些属性。

#### 问：如何定制对提取的文本片段的操作？

答：获得提取的文本片段后，您可以自定义循环内的代码，以对每个文本片段执行其他操作。这可以包括保存提取的文本、分析模式或根据您的要求实施格式更改。