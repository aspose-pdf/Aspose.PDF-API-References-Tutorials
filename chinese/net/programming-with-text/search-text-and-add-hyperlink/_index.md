---
title: 搜索文本并添加超链接
linktitle: 搜索文本并添加超链接
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 中搜索文本、向找到的文本添加超链接以及保存修改后的文档。
type: docs
weight: 450
url: /zh/net/programming-with-text/search-text-and-add-hyperlink/
---

本教程介绍如何使用 Aspose.PDF for .NET 搜索 PDF 文档中的特定文本、添加找到的文本的超链接以及保存修改后的文档。提供的 C# 源代码逐步演示了该过程。

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
using Aspose.Pdf.Content;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Text;
```

## 第三步：设置文档目录路径

使用以下命令设置文档目录的路径`dataDir`多变的：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

代替`"YOUR DOCUMENT DIRECTORY"`与文档目录的实际路径。

## 第四步：创建一个TextFragmentAbsorber

创建一个`TextFragmentAbsorber`对象查找输入搜索短语的所有实例：

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber("\\d{4}-\\d{4}");
```

代替`"\\d{4}-\\d{4}"`与您想要的正则表达式模式。

## 第 5 步：启用正则表达式搜索

通过设置启用正则表达式搜索`TextSearchOptions`吸收体的特性：

```csharp
absorber.TextSearchOptions = new TextSearchOptions(true);
```

## 步骤6：打开并绑定PDF文档

创建一个`PdfContentEditor`对象并将其绑定到源 PDF 文件：

```csharp
PdfContentEditor editor = new PdfContentEditor();
editor.BindPdf(dataDir + "SearchRegularExpressionPage.pdf");
```

代替`"SearchRegularExpressionPage.pdf"`与您的 PDF 文件的实际名称。

## 第 7 步：接受页面的吸收器

接受文档所需页面的吸收器：

```csharp
editor.Document.Pages[1].Accept(absorber);
```

代替`1`与所需的页码。

## 步骤 8：将超链接添加到找到的文本

循环检索到的文本片段并向其添加超链接：

```csharp
foreach (TextFragment textFragment in absorber.TextFragments)
{
    textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Blue;
    //根据文本片段的位置创建一个矩形
    System.Drawing.Rectangle rect = new System.Drawing.Rectangle((int)textFragment.Rectangle.LLX,
        (int)Math.Round(textFragment.Rectangle.LLY), (int)Math.Round(textFragment.Rectangle.Width + 2),
        (int)Math.Round(textFragment.Rectangle.Height + 1));
    //将网络链接添加到矩形
    editor.CreateWebLink(rect, "http://www.aspose.com", 1, System.Drawing.Color.Blue);
}
```

代替`"http://www.aspose.com"`与所需的超链接 URL。

## 步骤9：保存并关闭修改后的文档

保存修改后的文档并关闭编辑器：

```csharp
dataDir = dataDir + "SearchTextAndAddHyperlink_out.pdf";
editor.Save(dataDir);
editor.Close();
Console.WriteLine("\nText replaced and hyperlink added successfully based on a regular expression.\nFile saved at " + dataDir);
```

确保更换`"SearchTextAndAddHyperlink_out.pdf"`与所需的输出文件名。

### 使用 Aspose.PDF for .NET 搜索文本和添加超链接的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//创建吸收器对象以查找输入搜索短语的所有实例
TextFragmentAbsorber absorber = new TextFragmentAbsorber("\\d{4}-\\d{4}");
//启用正则表达式搜索
absorber.TextSearchOptions = new TextSearchOptions(true);
//打开文档
PdfContentEditor editor = new PdfContentEditor();
//绑定源PDF文件
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
	editor.CreateWebLink(rect, "http://www.aspose.com", 1, 蓝色, actionName);
	editor.CreateLine(rect, "", (float)textFragment.Rectangle.LLX + 1, (float)textFragment.Rectangle.LLY - 1,
		(float)textFragment.Rectangle.URX, (float)textFragment.Rectangle.LLY - 1, 1, 1, blue, "S", dashArray, LEArray);
}
dataDir = dataDir + "SearchTextAndAddHyperlink_out.pdf";
editor.Save(dataDir);
editor.Close();
Console.WriteLine("\nText replaced and hyperlink added successfully based on a regular expression.\nFile saved at " + dataDir);
```

## 结论

恭喜！您已经成功学习了如何在 PDF 文档中搜索特定文本、向找到的文本添加超链接以及使用 Aspose.PDF for .NET 保存修改后的文档。本教程提供了从设置项目到执行所需操作的分步指南。现在，您可以将此代码合并到您自己的 C# 项目中，以操作文本并在 PDF 文件中添加超链接。