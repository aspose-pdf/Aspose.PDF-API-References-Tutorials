---
title: 在 PDF 文件中的文本中添加工具提示
linktitle: 在 PDF 文件中的文本中添加工具提示
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 向 PDF 文件中的文本添加工具提示。轻松使用信息丰富的悬停文本增强您的 PDF。
type: docs
weight: 90
url: /zh/net/programming-with-text/add-tooltip-to-text/
---
## 介绍

在创建引人入胜且具有交互性的 PDF 时，工具提示非常有用。您知道那些将鼠标悬停在某个内容上时会为您提供额外信息的小弹出框吗？它们可以提供上下文、描述，甚至是一些建议，而不会使您的文档杂乱无章。在本教程中，我们将介绍如何使用 Aspose.PDF for .NET 库向 PDF 文件中的文本添加工具提示。无论您是经验丰富的开发人员，还是刚刚涉足 PDF 世界，您都来对地方了！让我们开始吧！

## 先决条件

在我们进入编码部分之前，让我们确保您拥有顺利进行所需的一切。

### 已安装 Visual Studio
在您的机器上安装 Visual Studio 至关重要，因为它将成为 .NET 应用程序的主要开发环境。

### Aspose.PDF for .NET 库
您还需要有 Aspose.PDF 库。您可以[点击下载](https://releases.aspose.com/pdf/net/)确保将其包含在您的项目参考中。

### C# 基础知识
拥有 C# 背景会很有帮助，因为我们将使用该语言进行编码。但不要担心——我会指导您完成每一步！

### 要处理的 PDF 文档
您可以从空白 PDF 文档开始，就像我们在此示例中所做的那样，或者如果愿意，可以使用现有的文档。

现在，让我们继续编码部分！

## 导入包 

我们的编码冒险的第一步是导入必要的包。打开 Visual Studio 项目，然后在 C# 文件的顶部添加以下内容`using`指令：

```csharp
using Aspose.Pdf.Forms;
using Aspose.Pdf.Text;
```

这些包使您能够访问创建和操作 PDF 文档所需的所有类和功能。

## 步骤 1：设置文档目录

首先，我们需要设置保存文档的路径。这就像在文件系统中找到一个舒适的位置，将您所有的创作都存放在那里。

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outputFile = dataDir + "Tooltip_out.pdf";
```

确保更换`YOUR DOCUMENT DIRECTORY`与您的机器上的实际路径。

## 步骤 2：创建示例 PDF 文档

接下来，是时候创建一个包含一些文本的简单 PDF 了。这就是我们开始创作过程的地方！

```csharp
//创建带有文本的示例文档
Document doc = new Document();
doc.Pages.Add().Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a tooltip"));
doc.Pages[1].Paragraphs.Add(new TextFragment("Move the mouse cursor here to display a very long tooltip"));
doc.Save(outputFile);
```

这一步我们创建一个文档，添加两个文本片段，并将其保存到我们之前指定的路径。

## 步骤 3：打开文档进行处理

现在我们已经创建了文档，让我们打开它以便可以处理那些工具提示！

```csharp
//打开带有文本的文档
Document document = new Document(outputFile);
```

这里我们只需加载刚刚创建的文档。

## 步骤 4：创建文本吸收器以查找文本片段

我们需要找到想要添加工具提示的文本片段。这就像使用放大镜突出显示大地图的特定部分一样！ 

```csharp
//创建 TextAbsorber 对象来查找与正则表达式匹配的所有短语
TextFragmentAbsorber absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a tooltip");
document.Pages.Accept(absorber);
```

## 步骤 5：提取文本片段

接下来，我们提取从上一步中找到的文本片段。

```csharp
//获取提取的文本片段
TextFragmentCollection textFragments = absorber.TextFragments;
```

此代码片段使我们能够保留对我们感兴趣的文本片段的引用。

## 步骤 6：循环遍历片段并添加工具提示

现在到了最有趣的部分！我们将循环遍历每个文本片段并为每个文本片段添加一个工具提示。想象一下将小礼物（工具提示）包裹在特定物品（文本片段）周围。

```csharp
//循环遍历片段
foreach (TextFragment fragment in textFragments)
{
	//在文本片段位置创建隐形按钮
	ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
	//AlternateName 值将由查看器应用程序显示为工具提示
	field.AlternateName = "Tooltip for text.";
	//向文档添加按钮字段
	document.Form.Add(field);
}
```

在每次迭代中，我们创建一个与文本片段的位置相对应的按钮字段并将工具提示文本分配给它。

## 步骤 7：重复上述步骤，以制作长工具提示

就像我们添加了一个简单的工具提示一样，我们可以对较长的文本执行相同的操作。让我们发挥我们的创造力吧！

```csharp
//接下来将是一个非常长的工具提示的示例
absorber = new TextFragmentAbsorber("Move the mouse cursor here to display a very long tooltip");
document.Pages.Accept(absorber);
textFragments = absorber.TextFragments;
foreach (TextFragment fragment in textFragments)
{
	ButtonField field = new ButtonField(fragment.Page, fragment.Rectangle);
	//设置非常长的文本
	field.AlternateName = "Lorem ipsum dolor sit amet, consectetur adipiscing elit," +
							" sed do eiusmod tempor incididunt ut labore et dolore magna" +
							" aliqua. Ut enim ad minim veniam, quis nostrud exercitation" +
							" ullamco laboris nisi ut aliquip ex ea commodo consequat." +
							" Duis aute irure dolor in reprehenderit in voluptate velit" +
							" esse cillum dolore eu fugiat nulla pariatur. Excepteur sint" +
							" occaecat cupidatat non proident, sunt in culpa qui officia" +
							" deserunt mollit anim id est laborum.";
	document.Form.Add(field);
}
```

在这里，我们做着与以前相同的工作，但使用了更为扩展的工具提示。

## 步骤 8：保存文档

最后一步是使用所有这些闪亮的新工具提示保存您的文档。 

```csharp
//保存文档
document.Save(outputFile);
```

就这样，您就大功告成了！您已将工具提示添加到 PDF，使其更加用户友好且更具交互性。

## 结论

以上就是如何使用 Aspose.PDF for .NET 向 PDF 文件中的文本添加工具提示的简单易懂的指南。此技术可以显著增强用户体验，使您的文档更具信息量，而不会让读者一次阅读过多的文本。 

只需将鼠标悬停在单词或短语上，读者即可获得相关信息，这些信息既有价值又不会杂乱。所以，撸起袖子试试吧！不知不觉中，您就可以创建各种引人注目的引人入胜的文档。

## 常见问题解答

### 什么是 Aspose.PDF for .NET？
Aspose.PDF for .NET 是一个库，使开发人员能够在 .NET 应用程序中创建、操作和转换 PDF 文档。

### 我可以免费使用 Aspose.PDF 吗？
是的，Aspose 提供免费试用，让您探索其功能！您可以找到它[这里](https://releases.aspose.com/).

### Aspose.PDF 是否有任何可用的许可选项？
是的，您可以购买许可证或获取临时许可证。查看选项[这里](https://purchase.aspose.com/).

### 我可以使用 Aspose.PDF 添加工具提示以外的交互元素吗？
当然！Aspose.PDF 允许添加各种交互元素，如超链接、按钮和表单。

### 在哪里可以找到有关 Aspose.PDF 的更多文档？
您可以查看文档[这里](https://reference.aspose.com/pdf/net/)以获得更深入的指导。