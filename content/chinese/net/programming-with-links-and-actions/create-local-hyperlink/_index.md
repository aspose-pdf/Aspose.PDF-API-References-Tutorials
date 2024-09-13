---
title: 在 PDF 文件中创建本地超链接
linktitle: 在 PDF 文件中创建本地超链接
second_title: Aspose.PDF for .NET API 参考
description: 通过我们的分步指南学习如何使用 Aspose.PDF for .NET 轻松在 PDF 文件中创建本地超链接。
type: docs
weight: 40
url: /zh/net/programming-with-links-and-actions/create-local-hyperlink/
---
## 介绍

在本指南中，我们将引导您完成使用 Aspose.PDF for .NET 在 PDF 文件中创建本地超链接的过程。我们将清晰地分解每个步骤，确保即使您是 PDF 操作领域的新手，也能轻松跟上。

## 先决条件

在深入研究代码之前，让我们先确保您已准备好所需的一切：

1.  Visual Studio：您需要使用它来开发 .NET 应用程序。从[网站](https://visualstudio.microsoft.com/).
2. Aspose.PDF for .NET：您可以通过以下方式下载此库[下载链接在这里](https://releases.aspose.com/pdf/net/).它带有一套丰富的 PDF 操作功能。
3. C# 基础知识：对 C# 编程有一点熟悉会有所帮助，但不用担心；我们将逐行介绍代码。
4.  .NET Framework：确保您的机器上安装了 .NET Framework。您可以在 Aspose.PDF 上查看要求[文档](https://reference.aspose.com/pdf/net/).

设置这些先决条件后，您就可以学习如何在 PDF 文档中创建本地超链接了！

## 导入包

现在您已做好一切准备，是时候在 C# 项目中导入必要的包了。Aspose.PDF 库包含我们需要的所有类。操作方法如下：

### 打开你的项目

打开您现有的 .NET 项目或在 Visual Studio 中创建一个新项目。如果您是新开始，请从启动屏幕中选择“创建新项目”。

### 添加对 Aspose.PDF 的引用

在解决方案资源管理器中，右键单击项目文件夹中的“依赖项”。选择“管理 NuGet 包”，然后搜索`Aspose.PDF`。安装最新版本。这将带来创建和处理 PDF 所需的所有工具。

### 导入命名空间

在.cs文件的顶部，添加Aspose.PDF库的使用指令，如下所示：

```csharp
using System;
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

这样，您就可以访问图书馆的功能。

让我们将创建本地超链接的过程分解为简单的步骤。每个步骤都会得到全面解释，以帮助您了解其背后的逻辑。

## 步骤 1：设置文档实例

在此步骤中，您将创建 Document 类的新实例，它代表您将使用的 PDF 文件。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY"; //设置文档目录
Document doc = new Document(); //创建 Document 实例
```
这`dataDir`变量是新创建的 PDF 的存放位置。您需要替换`"YOUR DOCUMENT DIRECTORY"`与您系统上的实际路径一致。`Document`该类创建一个新的 PDF 文档，我们可以在其中添加页面和链接。

## 步骤 2：向文档添加页面

接下来，您将向 PDF 文档添加一页。 

```csharp
Page page = doc.Pages.Add(); //将页面添加到页面集合
```
这`Pages.Add()`方法会向文档添加一个新页面。所有内容都将存放在此页面中。

## 步骤 3：创建文本片段

现在，让我们创建一段可作为可点击链接的文本。

```csharp
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("link page number test to page 7");
```
这`TextFragment`表示 PDF 中的一段文本。在这里，我们创建一个链接，告诉用户它将带他们到第 7 页。

## 步骤 4：创建本地超链接

奇迹就在这里发生！您需要创建一个本地超链接，告诉文本片段指向哪里。

```csharp
Aspose.Pdf.LocalHyperlink link = new Aspose.Pdf.LocalHyperlink(); //创建本地超链接
link.TargetPageNumber = 7; //设置链接实例的目标页面
text.Hyperlink = link; //设置 TextFragment 超链接
```
这`LocalHyperlink`类允许我们指向同一文档中的其他页面。通过设置`TargetPageNumber`到 7，您告诉超链接在单击时跳转到该特定页面。

## 步骤 5：将文本片段添加到页面

设置超链接后，就可以将文本片段添加到我们创建的页面了。

```csharp
page.Paragraphs.Add(text); //将文本添加到页面的段落集合
```
此行将可点击的文本添加到页面的段落集合中。

## 步骤 6：创建另一个文本片段（可选）

让我们添加另一个超链接以导航回第 1 页。

```csharp
text = new TextFragment("link page number test to page 1"); //创建新的 TextFragment
text.IsInNewPage = true; //将其添加到新页面
```
创建新`TextFragment`对于第二个链接，我们设置`IsInNewPage`为 true，表明该文本将出现在新页面上。

## 步骤 7：设置第二个本地超链接

与之前一样，您将为第 1 页创建另一个本地超链接。

```csharp
link = new LocalHyperlink(); //创建另一个本地超链接实例
link.TargetPageNumber = 1; //设置第二个超链接的目标页面
text.Hyperlink = link; //设置第二个 TextFragment 的链接
```
此超链接目标为第 1 页，允许用户在到达第二页时跳转回。

## 步骤 8：将第二个文本片段添加到新页面

现在，让我们将此文本添加到其页面中。

```csharp
page.Paragraphs.Add(text); //将文本添加到页面对象的段落集合中
```
与步骤 5 类似，此行将新的超链接文本添加到新创建的页面。

## 步骤 9：保存文档

最后，是时候保存你的辛勤工作成果了！ 

```csharp
dataDir = dataDir + "CreateLocalHyperlink_out.pdf"; //指定输出文件名
doc.Save(dataDir); //保存更新的文档
Console.WriteLine("\nLocal hyperlink created successfully.\nFile saved at " + dataDir);
```
这会将目录路径与文件名组合在一起。`Save()`方法保存您的文档，并且确认消息会让您知道一切顺利！

## 结论

使用 Aspose.PDF for .NET 在 PDF 文件中创建本地超链接不仅仅是一个很酷的技巧；它是一项实用的功能，可以增强导航和用户体验。现在，您已经掌握了将读者直接引导到他们需要的信息的知识。回想一下我们最初的比喻——不再有迷失的灵魂在无尽的页面中徘徊。

## 常见问题解答

### 什么是 Aspose.PDF for .NET？
Aspose.PDF for .NET 是一个库，允许开发人员使用 .NET 框架以编程方式创建、操作和转换 PDF 文档。

### 我可以创建指向外部网页的超链接吗？
是的，除了 PDF 内的本地超链接之外，Aspose.PDF 还支持创建到外部 URL 的超链接。

### Aspose.PDF 有免费试用版吗？
当然可以！你可以从[地点](https://releases.aspose.com/).

### Aspose 支持哪些编程语言？
Aspose 提供各种编程语言的库，包括 Java、C++，以及 Python 等等。

### 如何获得 Aspose 产品的支持？
您可以通过以下方式寻求支持[Aspose 论坛](https://forum.aspose.com/c/pdf/10).