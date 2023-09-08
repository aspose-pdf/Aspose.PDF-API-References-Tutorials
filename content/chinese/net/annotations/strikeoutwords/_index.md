---
title: 删除单词
linktitle: 删除单词
second_title: Aspose.PDF for .NET API 参考
description: 本文提供了使用 Aspose.PDF for .NET 的删除单词功能的分步指南，包括分步指南和说明
type: docs
weight: 150
url: /zh/net/annotations/strikeoutwords/
---
Aspose.PDF for .NET 是一个 PDF 文档操作和处理库，它提供了创建、修改和转换 PDF 文件的各种功能。 Aspose.PDF 提供的有用功能之一是能够使用 C# 源代码删除 PDF 文档中的单词或短语。在本文中，我们将提供有关如何使用 Aspose.PDF for .NET 删除单词的分步指南。

## 第 1 步：加载 PDF 文档
第一步是加载要修改的 PDF 文档。在本教程中，我们将从“您的文档目录”文件夹中加载名为“input.pdf”的 PDF 文档。 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document document = new Document(dataDir + "input.pdf");
```

## 第二步：搜索文本片段
要删除 PDF 文档中的特定单词或短语，您首先需要搜索它们。 Aspose.PDF提供了一个TextFragmentAbsorber类，可用于搜索PDF文档中的特定文本片段。

```csharp
Aspose.Pdf.Text.TextFragmentAbsorber textFragmentAbsorber = new Aspose.Pdf.Text.TextFragmentAbsorber("Estoque");
```

在上面的代码中，我们正在 PDF 文档中搜索文本片段“Estoque”。您可以修改此选项以搜索您想要删除的任何其他单词或短语。

## 第三步：删除文本片段
找到文本片段后，下一步就是将它们删除。 Aspose.PDF提供了一个StrikeOutAnnotation类，可用于为文本片段创建删除线注释。 

```csharp
Aspose.Pdf.Rectangle rect = new Aspose.Pdf.Rectangle((float)textFragment.Position.XIndent, (float)textFragment.Position.YIndent, (float)textFragment.Position.XIndent + (float)textFragment.Rectangle.Width, (float)textFragment.Position.YIndent + (float)textFragment.Rectangle.Height);

StrikeOutAnnotation strikeOut = new StrikeOutAnnotation(textFragment.Page, rect);
strikeOut.Opacity = .80f;
strikeOut.Border = new Border(strikeOut);
strikeOut.Color = Aspose.Pdf.Color.Red;
textFragment.Page.Annotations.Add(strikeOut);
```

在上面的代码中，我们为找到的每个文本片段创建删除线注释。我们还设置删除线注释的不透明度、边框和颜色。

## 第四步：保存修改后的PDF文档
删除文本片段后，保存修改后的文档。

```csharp
dataDir = dataDir + "StrikeOutWords_out.pdf";
document.Save(dataDir);
```

### 使用 Aspose.PDF for .NET 删除单词的示例源代码


```csharp

//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//打开文档
Document document = new Document(dataDir + "input.pdf");

//创建 TextFragment Absorber 实例来搜索特定文本片段
Aspose.Pdf.Text.TextFragmentAbsorber textFragmentAbsorber = new Aspose.Pdf.Text.TextFragmentAbsorber("Estoque");
//遍历 PDF 文档的页面
for (int i = 1; i <= document.Pages.Count; i++)
{
	//获取PDF文档的第一页
	Page page = document.Pages[1];
	page.Accept(textFragmentAbsorber);
}

//创建吸收文本的集合
Aspose.Pdf.Text.TextFragmentCollection textFragmentCollection = textFragmentAbsorber.TextFragments;

//迭代上面的集合
for (int j = 1; j <= textFragmentCollection.Count; j++)
{
	Aspose.Pdf.Text.TextFragment textFragment = textFragmentCollection[j];

	//获取 TextFragment 对象的矩形尺寸
	Aspose.Pdf.Rectangle rect = new Aspose.Pdf.Rectangle(
				(float)textFragment.Position.XIndent,
				(float)textFragment.Position.YIndent,
				(float)textFragment.Position.XIndent +
				(float)textFragment.Rectangle.Width,
				(float)textFragment.Position.YIndent +
				(float)textFragment.Rectangle.Height);

	//实例化删除线注释实例
	StrikeOutAnnotation strikeOut = new StrikeOutAnnotation(textFragment.Page, rect);
	//设置注释的不透明度
	strikeOut.Opacity = .80f;
	//设置注释实例的边框
	strikeOut.Border = new Border(strikeOut);
	//设置注释颜色
	strikeOut.Color = Aspose.Pdf.Color.Red;
	//将注释添加到 TextFragment 的注释集合中
	textFragment.Page.Annotations.Add(strikeOut);
}
dataDir = dataDir + "StrikeOutWords_out.pdf";
document.Save(dataDir);
```

## 结论

在本教程中，我们学习了如何使用 Aspose.PDF for .NET 删除 PDF 文档中的特定单词。通过遵循分步指南并使用提供的 C# 源代码，您可以轻松加载 PDF 文档、搜索特定文本片段并创建删除线注释以直观地标记和删除这些单词。 Aspose.PDF for .NET 提供了一种简单有效的方法来以编程方式操作 PDF 文档，使其成为开发人员在 .NET 应用程序中处理 PDF 文件的宝贵工具。

### 常见问题解答

#### 问：什么是 Aspose.PDF for .NET？

答：Aspose.PDF for .NET 是一个功能强大的库，允许开发人员在 .NET 应用程序中以编程方式创建、编辑和操作 PDF 文档。它提供了广泛的处理 PDF 文件的功能，包括文本提取、注释处理、表单填写等等。

#### 问：我可以使用 Aspose.PDF for .NET 删除 PDF 文档中的特定单词吗？

答：是的，Aspose.PDF for .NET 提供了在 PDF 文档中搜索特定文本片段的功能，然后创建删除线注释以直观地标记和删除这些单词。

#### 问：如何在 PDF 文档中指定要删除的文本？

答：要指定要删除的文本，可以使用`TextFragmentAbsorber`Aspose.PDF for .NET 提供的类。它允许您根据所需的条件在 PDF 文档中搜索特定的文本片段。

#### 问：我可以自定义删除线注释的外观吗？

答：是的，您可以自定义删除线注释的各种属性，例如不透明度、边框样式和颜色。这使您可以根据您的具体要求定制删除线注释的外观。