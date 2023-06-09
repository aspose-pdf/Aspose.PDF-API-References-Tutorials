---
title: 创建本地超链接
linktitle: 创建本地超链接
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 在 PDF 文件中轻松创建本地超链接。
type: docs
weight: 40
url: /zh/net/programming-with-links-and-actions/create-local-hyperlink/
---

在 PDF 文件中创建本地超链接可让您创建可点击的链接，将用户带到同一 PDF 文档中的其他页面。使用 Aspose.PDF for .NET，您可以按照以下源代码轻松创建此类链接：

## 第 1 步：导入所需的库

在开始之前，您需要为您的 C# 项目导入必要的库。这是必要的导入指令：

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.InteractiveFeatures;
```

## 第 2 步：设置文档文件夹的路径

在此步骤中，您需要指定要保存生成的 PDF 文件的文件夹路径。代替`"YOUR DOCUMENT DIRECTORY"`在以下代码中使用文档文件夹的实际路径：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 3 步：创建一个 Document 实例

我们将创建一个实例`Document`类来表示我们的 PDF 文档。下面是相应的代码：

```csharp
Document doc = new Document();
```

## 第 4 步：添加带有超链接的页面和文本

在此步骤中，我们将向 PDF 文档添加一个页面并添加一些包含本地超链接的文本。我们将为每个链接定义目标页面。下面是相应的代码：

```csharp
Page page = doc.Pages.Add();

TextFragment text = new TextFragment("Link to page 7");
LocalHyperlink link = new LocalHyperlink();
link.TargetPageNumber = 7;
text. Hyperlink = link;
page.Paragraphs.Add(text);

text = new TextFragment("Link to page 1");
text. IsInNewPage = true;
link = new LocalHyperlink();
link.TargetPageNumber = 1;
text. Hyperlink = link;
page.Paragraphs.Add(text);
```

## 第 5 步：保存更新后的文档

现在让我们使用`Save`的方法`doc`目的。下面是相应的代码：

```csharp
dataDir = dataDir + "CreateLocalHyperlink_out.pdf";
doc.Save(dataDir);
```

### 使用 Aspose.PDF for .NET 创建本地超链接的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//创建文档实例
Document doc = new Document();
//将页面添加到 PDF 文件的页面集合
Page page = doc.Pages.Add();
//创建文本片段实例
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("link page number test to page 7");
//创建本地超链接实例
Aspose.Pdf.LocalHyperlink link = new Aspose.Pdf.LocalHyperlink();
//设置链接实例的目标页面
link.TargetPageNumber = 7;
//设置 TextFragment 超链接
text.Hyperlink = link;
//将文本添加到页面的段落集合
page.Paragraphs.Add(text);
//创建新的 TextFragment 实例
text = new TextFragment("link page number test to page 1");
//应在新页面上添加 TextFragment
text.IsInNewPage = true;
//创建另一个本地超链接实例
link = new LocalHyperlink();
//为第二个超链接设置目标页面
link.TargetPageNumber = 1;
//为第二个 TextFragment 设置链接
text.Hyperlink = link;
//将文本添加到页面对象的段落集合
page.Paragraphs.Add(text);    
dataDir = dataDir + "CreateLocalHyperlink_out.pdf";
//保存更新的文档
doc.Save(dataDir);
Console.WriteLine("\nLocal hyperlink created successfully.\nFile saved at " + dataDir);            
```

## 结论

恭喜！现在您有了使用 Aspose.PDF for .NET 在 PDF 中创建本地超链接的分步指南。您可以使用此代码创建可点击的链接，将用户带到同一文档中的其他页面。

请务必查看官方 Aspose.PDF 文档以获取有关高级超链接功能的更多信息。