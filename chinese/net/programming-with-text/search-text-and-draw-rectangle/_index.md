---
title: 搜索文本并绘制矩形
linktitle: 搜索文本并绘制矩形
second_title: Aspose.PDF for .NET API 参考
description: 了解如何在 PDF 中搜索文本、在找到的文本周围绘制矩形以及使用 Aspose.PDF for .NET 保存修改后的文档。
type: docs
weight: 460
url: /zh/net/programming-with-text/search-text-and-draw-rectangle/
---

本教程介绍如何使用 Aspose.PDF for .NET 搜索 PDF 文档中的特定文本，在找到的文本周围绘制矩形，然后保存修改后的文档。提供的 C# 源代码逐步演示了该过程。

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
using Aspose.Pdf.Content;
using Aspose.Pdf.Facades;
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
Document document = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

代替`"SearchAndGetTextFromAll.pdf"`与您的 PDF 文件的实际名称。

## 第5步：创建一个TextFragmentAbsorber

创建一个`TextFragmentAbsorber`对象查找输入搜索短语的所有实例：

```csharp
TextFragmentAbsorber textAbsorber = new TextFragmentAbsorber(@"[\S]+");
```

代替`@"[\S]+"`与您想要的正则表达式模式。

## 第 6 步：启用正则表达式搜索

通过设置启用正则表达式搜索`TextSearchOptions`吸收体的特性：

```csharp
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textAbsorber.TextSearchOptions = textSearchOptions;
```

## 第7步：在所有页面上搜索

接受文档所有页面的吸收器：

```csharp
document.Pages.Accept(textAbsorber);
```

## 第 8 步：在找到的文本周围画一个矩形

创建一个`PdfContentEditor`对象并循环检索到的文本片段，在每个文本片段周围绘制一个矩形：

```csharp
var editor = new PdfContentEditor(document);
foreach (TextFragment textFragment in textAbsorber.TextFragments)
{
    foreach (TextSegment textSegment in textFragment.Segments)
    {
        DrawBox(editor, textFragment.Page.Number, textSegment, System.Drawing.Color.Red);
    }
}
```

## 步骤9：保存修改后的文档

保存修改后的文档：

```csharp
dataDir = dataDir + "SearchTextAndDrawRectangle_out.pdf";
document.Save(dataDir);
```

确保更换`"SearchTextAndDrawRectangle_out.pdf"`与所需的输出文件名。

### 使用 Aspose.PDF for .NET 搜索文本和绘制矩形的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//打开文档
Document document = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
//创建 TextAbsorber 对象以查找与正则表达式匹配的所有短语
TextFragmentAbsorber textAbsorber = new TextFragmentAbsorber(@"[\S]+");
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textAbsorber.TextSearchOptions = textSearchOptions;
document.Pages.Accept(textAbsorber); 
var editor = new PdfContentEditor(document); 
foreach (TextFragment textFragment in textAbsorber.TextFragments)
{
	foreach (TextSegment textSegment in textFragment.Segments)
	{
			DrawBox(editor, textFragment.Page.Number, textSegment, System.Drawing.Color.Red);
	}
}
dataDir = dataDir + "SearchTextAndDrawRectangle_out.pdf";
document.Save(dataDir);
Console.WriteLine("\nRectangle drawn successfully on searched text.\nFile saved at " + dataDir);
```

## 结论

恭喜！您已经成功学习了如何在 PDF 文档中搜索特定文本、在找到的文本周围绘制矩形以及使用 Aspose.PDF for .NET 保存修改后的文档。本教程提供了从设置项目到执行所需操作的分步指南。现在，您可以将此代码合并到您自己的 C# 项目中，以操作 PDF 文件中的文本和绘制矩形。