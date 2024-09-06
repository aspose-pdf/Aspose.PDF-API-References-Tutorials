---
title: 搜索文本并添加超链接
linktitle: 搜索文本并添加超链接
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 中搜索文本、向找到的文本添加超链接以及保存修改后的文档。
type: docs
weight: 450
url: /zh/net/programming-with-text/search-text-and-add-hyperlink/
---
本教程讲解如何使用 Aspose.PDF for .NET 在 PDF 文档中搜索特定文本、为找到的文本添加超链接以及保存修改后的文档。提供的 C# 源代码逐步演示了该过程。

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
using Aspose.Pdf.Content;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Text;
```

## 步骤3：设置文档目录的路径

使用以下方式设置文档目录的路径：`dataDir`多变的：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

代替`"YOUR DOCUMENT DIRECTORY"`使用您的文档目录的实际路径。

## 步骤 4：创建 TextFragmentAbsorber

创建一个`TextFragmentAbsorber`对象来查找输入搜索短语的所有实例：

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("\\d{4}-\\d{4}");
```

代替`"\\d{4}-\\d{4}"`使用您想要的正则表达式模式。

## 步骤 5：启用正则表达式搜索

通过设置启用正则表达式搜索`TextSearchOptions`吸收体的特性：

```csharp
absorber.TextSearchOptions = new TextSearchOptions(true);
```

## 步骤6：打开并装订PDF文档

创建一个`PdfContentEditor`对象并将其绑定到源 PDF 文件：

```csharp
PdfContentEditor editor = new PdfContentEditor();
editor.BindPdf(dataDir + "SearchRegularExpressionPage.pdf");
```

代替`"SearchRegularExpressionPage.pdf"`使用您的 PDF 文件的实际名称。

## 步骤 7：接受页面的吸收器

接受所需文档页面的吸收器：

```csharp
editor.Document.Pages[1].Accept(absorber);
```

代替`1`并输入所需的页码。

## 步骤 8：为找到的文本添加超链接

循环遍历检索到的文本片段并向其添加超链接：

```csharp
foreach (TextFragment textFragment in absorber.TextFragments)
{
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
    //根据文本片段的位置创建一个矩形
    System.Drawing.Rectangle rect = new System.Drawing.Rectangle((int)textFragment.Rectangle.LLX,
        (int)Math.Round(textFragment.Rectangle.LLY), (int)Math.Round(textFragment.Rectangle.Width + 2),
        (int)Math.Round(textFragment.Rectangle.Height + 1));
    //在矩形中添加网页链接
    editor.CreateWebLink(rect, "http://www.aspose.com", 1, System.Drawing.Color.Blue);
}
```

代替`"http://www.aspose.com"`使用所需的超链接 URL。

## 步骤 9：保存并关闭修改后的文档

保存修改后的文档并关闭编辑器：

```csharp
dataDir = dataDir + "SearchTextAndAddHyperlink_out.pdf";
editor.Save(dataDir);
editor.Close();
Console.WriteLine("\nText replaced and hyperlink added successfully based on a regular expression.\nFile saved at " + dataDir);
```

确保更换`"SearchTextAndAddHyperlink_out.pdf"`使用所需的输出文件名。

### 使用 Aspose.PDF for .NET 搜索文本并添加超链接的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//创建吸收器对象来查找输入搜索短语的所有实例
TextFragmentAbsorber absorber = new TextFragmentAbsorber("\\d{4}-\\d{4}");
//启用正则表达式搜索
absorber.TextSearchOptions = new TextSearchOptions(true);
//打开文档
PdfContentEditor editor = new PdfContentEditor();
//绑定源 PDF 文件
editor.BindPdf(dataDir + "SearchRegularExpressionPage.pdf");
//接受页面的吸收器
editor.Document.Pages[1].Accept(absorber);
int[] dashArray = { };
String[] LEArray = { };
System.Drawing.Color blue = System.Drawing.Color.Blue;
//循环遍历片段
foreach (TextFragment textFragment in absorber.TextFragments)
{
	textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
	System.Drawing.Rectangle rect = new System.Drawing.Rectangle((int)textFragment.Rectangle.LLX,
		(int)Math.Round(textFragment.Rectangle.LLY), (int)Math.Round(textFragment.Rectangle.Width + 2),
		(int)Math.Round(textFragment.Rectangle.Height + 1));
	Enum[] actionName = new Enum[2] { Aspose.Pdf.Annotations.PredefinedAction.Document_AttachFile, Aspose.Pdf.Annotations.PredefinedAction.Document_ExtractPages };
	editor.CreateWebLink(rect, "http://Www.aspose.com", 1, 蓝色, 动作名称);
	editor.CreateLine(rect, "", (float)textFragment.Rectangle.LLX + 1, (float)textFragment.Rectangle.LLY - 1,
		(float)textFragment.Rectangle.URX, (float)textFragment.Rectangle.LLY - 1, 1, 1, blue, "S", dashArray, LEArray);
}
dataDir = dataDir + "SearchTextAndAddHyperlink_out.pdf";
editor.Save(dataDir);
editor.Close();
Console.WriteLine("\nText replaced and hyperlink added successfully based on a regular expression.\nFile saved at " + dataDir);
```

## 结论

恭喜！您已成功学习了如何使用 Aspose.PDF for .NET 在 PDF 文档中搜索特定文本、向找到的文本添加超链接以及保存修改后的文档。本教程提供了分步指南，从设置项目到执行所需的操作。您现在可以将此代码合并到自己的 C# 项目中，以操作文本并在 PDF 文件中添加超链接。

### 常见问题解答

#### 问：“搜索文本并添加超链接”教程的目的是什么？

答：“搜索文本并添加超链接”教程旨在演示如何使用 .NET 的 Aspose.PDF 库在 PDF 文档中搜索特定文本、为找到的文本添加超链接，然后保存修改后的文档。该教程提供了全面的指南和 C# 代码示例来说明分步过程。

#### 问：本教程如何帮助您在 PDF 文档中添加指向特定文本的超链接？

答：本教程将指导您使用 Aspose.PDF 库查找 PDF 文档中的特定文本、将超链接应用于已识别的文本以及保存修改后的 PDF。它涵盖了设置项目、加载文档、启用正则表达式搜索以及向找到的文本添加超链接等基本步骤。

#### 问：学习本教程需要哪些先决条件？

答：在开始之前，您应该对 C# 编程语言有基本的了解。此外，您还需要安装 Aspose.PDF for .NET 库，该库可从 Aspose 网站获取，也可以在您的项目中使用 NuGet 安装。

#### 问：如何设置我的项目来遵循本教程？

答：首先在您首选的集成开发环境 (IDE) 中创建一个新的 C# 项目。然后，添加对 Aspose.PDF for .NET 库的引用，这将使您能够在项目中利用该库的功能。

#### 问：我可以使用本教程向特定文本添加超链接吗？

答：是的，本教程专门介绍如何向 PDF 文档中的特定文本添加超链接。它演示了如何使用正则表达式查找和提取所需文本、创建与文本片段关联的超链接以及保存修改后的 PDF。

#### 问：如何定义我想要搜索并添加超链接的文本？

答：要指定要搜索并添加超链接的文本，请创建一个`TextFragmentAbsorber`对象并使用设置其模式`Text`参数。替换默认模式`"\\d{4}-\\d{4}"`在教程的代码中使用您想要的正则表达式模式。

#### 问：如何启用文本的正则表达式搜索？

答：通过创建`TextSearchOptions`对象并将其值设置为`true` 将此对象分配给`TextSearchOptions`的财产`TextFragmentAbsorber`实例。这可确保在文本搜索期间应用正则表达式模式。

#### 问：如何为找到的文本添加超链接？

答：使用`TextFragmentAbsorber`，本教程提供了一个循环来迭代这些片段。对于每个文本片段，本教程演示了如何将文本颜色设置为蓝色，并使用`CreateWebLink`方法。

#### 问：保存修改后的带有超链接的 PDF 的步骤是什么？

答：将超链接添加到所需的文本片段后，使用`PdfContentEditor`类来保存修改后的文档。本教程的示例代码展示了如何保存已编辑的 PDF、关闭编辑器并显示成功消息。