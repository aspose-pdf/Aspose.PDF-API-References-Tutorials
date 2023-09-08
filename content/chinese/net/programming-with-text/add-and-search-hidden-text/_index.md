---
title: 添加并搜索 PDF 文件中的隐藏文本
linktitle: 添加并搜索 PDF 文件中的隐藏文本
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 在 PDF 文件中添加和搜索隐藏文本的分步指南。
type: docs
weight: 20
url: /zh/net/programming-with-text/add-and-search-hidden-text/
---
在本教程中，我们将引导您了解如何使用 Aspose.PDF for .NET 在 PDF 文件中添加和搜索隐藏文本。请按照以下步骤轻松执行此操作。

## 1. 前提条件

在开始之前，请确保您具备以下条件：

- 安装并配置 Visual Studio 或任何其他开发环境。
- C# 编程语言的基础知识。
- 安装了适用于.NET 的 Aspose.PDF 库。您可以从Aspose官方网站下载。

## 2. 创建带有隐藏文本的PDF文档

首先，使用以下代码创建一个包含隐藏文本的新 PDF 文档：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
//创建文档
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Page page = doc.Pages.Add();
TextFragment frag1 = new TextFragment("This is common text.");
TextFragment frag2 = new TextFragment("This is invisible text.");
//设置文本属性-不可见
frag2.TextState.Invisible = true;
page.Paragraphs.Add(frag1);
page.Paragraphs.Add(frag2);
doc.Save(dataDir + "39400_out.pdf");
doc.Dispose();
```

请务必提供 PDF 文档所需的路径和文件名。

## 3. 在文档中搜索文本

接下来，我们将搜索PDF文档中的隐藏文本。使用以下代码：

```csharp
doc = new Aspose.Pdf.Document(dataDir + "39400_out.pdf");
TextFragmentAbsorber absorb = new TextFragmentAbsorber();
absorb.Visit(doc.Pages[1]);
foreach(TextFragment fragment in absorber.TextFragments)
{
//用碎片做一些事情
Console.WriteLine("Text '{0}' at position {1}, invisibility: {2} ",
fragment.Text, fragment.Position.ToString(), fragment.TextState.Invisible);
}
doc.Dispose();
```

这将搜索 PDF 文档第二页中的隐藏文本并显示相关信息。

### 使用 Aspose.PDF for .NET 添加和搜索隐藏文本的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//创建带有隐藏文本的文档
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
Page page = doc.Pages.Add();
TextFragment frag1 = new TextFragment("This is common text.");
TextFragment frag2 = new TextFragment("This is invisible text.");
//设置文本属性-不可见
frag2.TextState.Invisible = true;
page.Paragraphs.Add(frag1);
page.Paragraphs.Add(frag2);
doc.Save(dataDir + "39400_out.pdf");
doc.Dispose();
//搜索文档中的文本
doc = new Aspose.Pdf.Document(dataDir + "39400_out.pdf");
TextFragmentAbsorber absorber = new TextFragmentAbsorber();
absorber.Visit(doc.Pages[1]);
foreach (TextFragment fragment in absorber.TextFragments)
{
	//用碎片做一些事情
	Console.WriteLine("Text '{0}' on pos {1} invisibility: {2} ",
	fragment.Text, fragment.Position.ToString(), fragment.TextState.Invisible);
}
doc.Dispose();
```

## 结论

恭喜！您已使用 Aspose.PDF for .NET 在 PDF 文档中成功添加并找到了隐藏文本。您现在可以将此方法应用到您自己的项目中，以操作和搜索 PDF 文件中的隐藏文本。

### 常见问题解答

#### 问：什么是 Aspose.PDF for .NET？

答：Aspose.PDF for .NET 是一个强大的库，使开发人员能够在 .NET 应用程序中创建、操作和转换 PDF 文档。

#### 问：隐藏文本可以用于水印吗？

答：当然！隐藏文本可以作为给 PDF 文档添加水印的有效方法，增加额外的安全层。

#### 问：是否可以显示 PDF 文档中的隐藏文本？

答：是的，搜索和显示 PDF 文档中隐藏文本的过程可以使用本教程中概述的技术来实现。

#### 问：Aspose.PDF for .NET 还提供哪些其他功能？

答：除了隐藏文本操作之外，Aspose.PDF for .NET 还提供了广泛的功能，包括 PDF 生成、转换、加密等。