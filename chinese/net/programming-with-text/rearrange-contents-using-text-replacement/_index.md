---
title: 使用文本替换重新排列内容
linktitle: 使用文本替换重新排列内容
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 的文本替换来重新排列 PDF 文档中的内容。
type: docs
weight: 270
url: /zh/net/programming-with-text/rearrange-contents-using-text-replacement/
---

在本教程中，我们将解释如何使用 .NET 的 Aspose.PDF 库使用文本替换来重新排列 PDF 文档中的内容。我们将逐步完成加载 PDF、搜索特定文本片段、替换文本以及使用提供的 C# 源代码保存修改后的 PDF 的过程。

## 要求

在开始之前，请确保您具有以下内容：

- 安装了 Aspose.PDF for .NET 库。
- 对 C# 编程有基本的了解。

## 第 1 步：设置文档目录

首先，您需要设置 PDF 文件所在目录的路径。代替`"YOUR DOCUMENT DIRECTORY"`在里面`dataDir`带有 PDF 文件路径的变量。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：加载源 PDF

接下来，我们使用`Document` Aspose.PDF 库中的类。

```csharp
Document doc = new Document(dataDir + "ExtractTextPage.pdf");
```

## 第 3 步：搜索和替换文本片段

我们创造一个`TextFragmentAbsorber`带有正则表达式的对象来搜索特定的文本片段。然后，我们遍历文本片段，自定义它们的字体、大小、颜色，并替换文本。

```csharp
TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("[TextFragmentAbsorber,companyname,Textbox,50]");
doc.Pages.Accept(textFragmentAbsorber);

foreach(TextFragment textFragment in textFragmentAbsorber.TextFragments)
{
     textFragment.TextState.Font = FontRepository.FindFont("Arial");
     textFragment.TextState.FontSize = 12;
     textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Navy;
     textFragment.Text = "This is a Larger String for the Testing of this issue";
}
```

## 第 4 步：保存修改后的 PDF

最后，我们将修改后的PDF文档保存到指定的输出文件中。

```csharp
dataDir = dataDir + "RearrangeContentsUsingTextReplacement_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nContents rearranged successfully using text replacement.\nFile saved at " + dataDir);
```

### 使用 Aspose.PDF for .NET 使用文本替换重新排列内容的示例源代码 
```csharp
try
{
	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	//加载源 PDF 文件
	Document doc = new Document(dataDir + "ExtractTextPage.pdf");
	//使用正则表达式创建 TextFragment Absorber 对象
	TextFragmentAbsorber textFragmentAbsorber = new TextFragmentAbsorber("[TextFragmentAbsorber,companyname,Textbox,50]");
	doc.Pages.Accept(textFragmentAbsorber);
	//替换每个 TextFragment
	foreach (TextFragment textFragment in textFragmentAbsorber.TextFragments)
	{
		//设置被替换文本片段的字体
		textFragment.TextState.Font = FontRepository.FindFont("Arial");
		//设置字体大小
		textFragment.TextState.FontSize = 12;
		textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Navy;
		//用比占位符更大的字符串替换文本
		textFragment.Text = "This is a Larger String for the Testing of this issue";
	}
	dataDir = dataDir + "RearrangeContentsUsingTextReplacement_out.pdf";
	//保存生成的 PDF
	doc.Save(dataDir);
	Console.WriteLine("\nContents rearranged successfully using text replacement.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get 30 day temporary license from http://www.aspose.com/purchase/default.aspx.");
}
```

## 结论

在本教程中，您学习了如何使用适用于 .NET 的 Aspose.PDF 库使用文本替换来重新排列 PDF 文档中的内容。按照分步指南并执行提供的 C# 代码，您可以搜索特定文本片段、自定义其外观并替换 PDF 文档中的文本。