---
title: 删除 PDF 文件中未使用的字体
linktitle: 删除 PDF 文件中未使用的字体
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 删除 PDF 文件中未使用的字体。
type: docs
weight: 300
url: /zh/net/programming-with-text/remove-unused-fonts/
---
在本教程中，我们将解释如何使用 .NET 的 Aspose.PDF 库删除 PDF 文件中未使用的字体。我们将逐步完成加载 PDF、识别和删除未使用的字体以及使用提供的 C# 源代码保存更新的 PDF 的过程。

## 要求

在开始之前，请确保您具备以下条件：

- 安装了 Aspose.PDF for .NET 库。
- 对 C# 编程有基本了解。

## 第 1 步：设置文档目录

首先，您需要设置 PDF 文件所在目录的路径。代替`"YOUR DOCUMENT DIRECTORY"`在里面`dataDir`变量包含 PDF 文件的路径。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：加载源 PDF

接下来，我们使用以下命令加载源 PDF 文档`Document`来自 Aspose.PDF 库的类。

```csharp
Document doc = new Document(dataDir + "ReplaceTextPage.pdf");
```

## 第 3 步：识别并删除未使用的字体

我们创建一个`TextFragmentAbsorber`对象与`TextEditOptions`参数设置为`TextEditOptions.FontReplace.RemoveUnusedFonts`。此选项允许我们识别并删除 PDF 文档中未使用的字体。然后我们迭代所有的`TextFragments`并将字体设置为所需的字体。

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
doc.Pages.Accept(absorb);

foreach(TextFragment textFragment in absorber.TextFragments)
{
     textFragment.TextState.Font = FontRepository.FindFont("Arial, Bold");
}
```

## 第 4 步：保存更新后的 PDF

最后，我们将更新后的 PDF 文档保存到指定的输出文件中。

```csharp
dataDir = dataDir + "RemoveUnusedFonts_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nUnused fonts removed successfully from the PDF document.\nFile saved at " + dataDir);
```

### 使用 Aspose.PDF for .NET 删除未使用的字体的示例源代码 
```csharp
try
{
	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	//加载源 PDF 文件
	Document doc = new Document(dataDir + "ReplaceTextPage.pdf");
	TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
	doc.Pages.Accept(absorber);
	//遍历所有 TextFragment
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

在本教程中，您学习了如何使用 .NET 的 Aspose.PDF 库从 PDF 文档中删除未使用的字体。通过遵循分步指南并执行提供的 C# 代码，您可以加载 PDF、识别和删除未使用的字体以及保存更新的 PDF。

### 常见问题解答

#### 问：“删除 PDF 文件中未使用的字体”教程的目的是什么？

答：“删除 PDF 文件中未使用的字体”教程介绍了如何使用 .NET 的 Aspose.PDF 库从 PDF 文档中删除未使用的字体。本教程将指导您完成加载 PDF、识别和删除未使用的字体以及保存更新的 PDF 的过程。

#### 问：为什么我要从 PDF 文档中删除未使用的字体？

答：从 PDF 文档中删除未使用的字体有助于减小文件大小并优化文档以获得更好的性能。这在处理包含文档内容中实际未使用的嵌入字体的 PDF 时特别有用。

#### 问：如何设置文档目录？

A：设置文档目录：

1. 代替`"YOUR DOCUMENT DIRECTORY"`在里面`dataDir`变量包含 PDF 文件所在目录的路径。

#### 问：如何使用 Aspose.PDF 库从 PDF 文档中删除未使用的字体？

答：本教程将逐步指导您完成整个过程：

1. 使用以下命令打开 PDF 文档`Document`班级。
2. 创建一个`TextFragmentAbsorber`对象与`TextEditOptions`设置`FontReplace.RemoveUnusedFonts`.
3. 接受吸收器以识别并删除 PDF 中未使用的字体。
4. 遍历所有`TextFragments`并将字体设置为所需的字体。
5. 保存更新的 PDF 文档。

#### 问：这样做的目的是什么`TextEditOptions.FontReplace.RemoveUnusedFonts` parameter?

答： 的`TextEditOptions.FontReplace.RemoveUnusedFonts`参数指示`TextFragmentAbsorber`识别并删除 PDF 文档中未使用的字体。

#### 问：我可以用我选择的字体替换未使用的字体吗？

答：是的，您可以修改代码，将未使用的字体替换为您选择的字体。在提供的示例代码中，使用字体“Arial, Bold”作为替换。

#### 问：如何`TextFragmentAbsorber` work to remove unused fonts?

答： 的`TextFragmentAbsorber`配置为`TextEditOptions.FontReplace.RemoveUnusedFonts`参数，用于标识 PDF 文本片段中未使用的字体。吸收后，可以迭代`TextFragments`并将其字体设置为所需的替换字体。

#### 问：执行所提供的代码的预期结果是什么？

答：通过遵循教程并运行提供的 C# 代码，您将从输入 PDF 文档中删除未使用的字体，并将更新的版本保存为输出 PDF 文件。

#### 问：我可以修改代码以仅从特定页面或区域删除字体吗？

答：提供的代码重点是从整个 PDF 文档中删除未使用的字体。如果您想要针对特定页面或区域进行字体删除，则需要修改方法并使用更复杂的逻辑来识别这些区域中未使用的字体。