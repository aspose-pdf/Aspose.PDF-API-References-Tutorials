---
title: 删除未使用的字体
linktitle: 删除未使用的字体
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 从 PDF 文档中删除未使用的字体。
type: docs
weight: 300
url: /zh/net/programming-with-text/remove-unused-fonts/
---

在本教程中，我们将解释如何使用 .NET 的 Aspose.PDF 库从 PDF 文档中删除未使用的字体。我们将逐步完成加载 PDF、识别和删除未使用的字体以及使用提供的 C# 源代码保存更新的 PDF 的过程。

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
Document doc = new Document(dataDir + "ReplaceTextPage.pdf");
```

## 第 3 步：识别并删除未使用的字体

我们创造一个`TextFragmentAbsorber`对象与`TextEditOptions`参数设置为`TextEditOptions.FontReplace.RemoveUnusedFonts`.此选项允许我们识别和删除 PDF 文档中未使用的字体。然后我们遍历所有`TextFragments`并将字体设置为所需的字体。

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
doc.Pages.Accept(absorb);

foreach(TextFragment textFragment in absorber.TextFragments)
{
     textFragment.TextState.Font = FontRepository.FindFont("Arial, Bold");
}
```

## 第 4 步：保存更新的 PDF

最后，我们将更新后的 PDF 文档保存到指定的输出文件中。

```csharp
dataDir = dataDir + "RemoveUnusedFonts_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nUnused fonts removed successfully from the PDF document.\nFile saved at " + dataDir);
```

### 使用 Aspose.PDF for .NET 删除未使用字体的示例源代码 
```csharp
try
{
	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	//加载源 PDF 文件
	Document doc = new Document(dataDir + "ReplaceTextPage.pdf");
	TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
	doc.Pages.Accept(absorber);
	//遍历所有的 TextFragments
	foreach (TextFragment textFragment in absorber.TextFragments)
	{
		textFragment.TextState.Font = FontRepository.FindFont("Arial, Bold");
	}
	dataDir = dataDir + "RemoveUnusedFonts_out.pdf";
	//保存更新的文档
	doc.Save(dataDir);
	Console.WriteLine("\nUnused fonts removed successfully from pdf document.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get 30 day temporary license from http://www.aspose.com/purchase/default.aspx.");
}
```

## 结论

在本教程中，您学习了如何使用 .NET 的 Aspose.PDF 库从 PDF 文档中删除未使用的字体。按照分步指南并执行提供的 C# 代码，您可以加载 PDF，识别和删除未使用的字体，并保存更新后的 PDF。