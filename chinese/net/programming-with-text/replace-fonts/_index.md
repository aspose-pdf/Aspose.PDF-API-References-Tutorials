---
title: 替换字体
linktitle: 替换字体
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 替换 PDF 文档中的字体。
type: docs
weight: 340
url: /zh/net/programming-with-text/replace-fonts/
---

在本教程中，我们将解释如何使用 .NET 的 Aspose.PDF 库替换 PDF 文档中的特定字体。我们将逐步完成加载 PDF 文档、搜索文本片段、识别要替换的字体、替换字体以及使用提供的 C# 源代码保存修改后的 PDF 的过程。

## 先决条件

在开始之前，请确保您具有以下内容：

- 安装了 Aspose.PDF for .NET 库。
- 对 C# 编程有基本的了解。

## 第 1 步：设置文档目录

首先，您需要将路径设置为您拥有输入 PDF 文件的目录。代替`"YOUR DOCUMENT DIRECTORY"`在里面`dataDir`带有 PDF 文件路径的变量。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：加载 PDF 文档

接下来，我们使用`Document` Aspose.PDF 库中的类。

```csharp
Document pdfDocument = new Document(dataDir + "ReplaceTextPage.pdf");
```

## 第 3 步：搜索和替换字体

我们创造一个`TextFragmentAbsorber`对象并设置编辑选项以删除未使用的字体。然后，我们接受 PDF 文档所有页面的吸收器来搜索文本片段。

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
pdfDocument.Pages.Accept(absorber);
```

## 第 4 步：替换字体

我们遍历吸收器识别的所有文本片段。如果文本片段的字体名称与要替换的所需字体匹配，我们将其替换为新字体。

```csharp
foreach (TextFragment textFragment in absorber.TextFragments)
{
    if (textFragment.TextState.Font.FontName == "Arial,Bold")
    {
        textFragment.TextState.Font = FontRepository.FindFont("Arial");
    }
}
```

## 第 5 步：保存修改后的 PDF

最后，我们将修改后的PDF文档保存到指定的输出文件中。

```csharp
dataDir = dataDir + "ReplaceFonts_out.pdf";
pdfDocument.Save(dataDir);
Console.WriteLine("\nFonts replaced successfully in the PDF document.\nFile saved at " + dataDir);
```

### 使用 Aspose.PDF for .NET 替换字体的示例源代码 
```csharp
try
{
	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	//加载源 PDF 文件
	Document pdfDocument = new Document(dataDir + "ReplaceTextPage.pdf");
	//搜索文本片段并将编辑选项设置为删除未使用的字体
	TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
	//接受所有页面的吸收器
	pdfDocument.Pages.Accept(absorber);
	//遍历所有的TextFragments
	foreach (TextFragment textFragment in absorber.TextFragments)
	{
		//如果字体名称为 ArialMT，则将字体名称替换为 Arial
		if (textFragment.TextState.Font.FontName == "Arial,Bold")
		{
			textFragment.TextState.Font = FontRepository.FindFont("Arial");
		}
	}
	dataDir = dataDir + "ReplaceFonts_out.pdf";
	//保存更新的文档
	pdfDocument.Save(dataDir);
	Console.WriteLine("\nFonts replaced successfully in pdf document.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get 30 day temporary license from http://www.aspose.com/purchase/default.aspx.");
}
```

## 结论

在本教程中，您学习了如何使用 .NET 的 Aspose.PDF 库替换 PDF 文档中的特定字体。按照分步指南并执行提供的 C# 代码，您可以加载 PDF 文档、搜索文本片段、识别和替换特定字体以及保存修改后的 PDF。