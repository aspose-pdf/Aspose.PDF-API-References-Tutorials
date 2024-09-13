---
title: 添加目录时自定义页码
linktitle: 添加目录时自定义页码
second_title: Aspose.PDF for .NET API 参考
description: 在本综合教程中学习如何使用 Aspose.PDF for .NET 向您的 PDF 文档添加目录并自定义页码。
type: docs
weight: 100
url: /zh/net/programming-with-document/customizepagenumbeswhileaddingtoc/
---
## 介绍

在文档管理领域，PDF 占据主导地位。它们是跨各种平台共享和保存文档的首选格式。但是，当您想要使用目录 (TOC) 等功能增强 PDF 文档时会发生什么？这就是 Aspose.PDF for .NET 发挥作用的地方！这个强大的库允许开发人员轻松操作 PDF 文件，使他们能够毫不费力地添加、修改和自定义内容。在本教程中，我们将深入研究如何使用 Aspose.PDF for .NET 自定义页码，同时将目录添加到 PDF 文档中。所以，戴上你的编码帽，让我们开始吧！

## 先决条件

在我们进入代码之前，你需要做好以下几件事：

1. Visual Studio：确保您的机器上安装了 Visual Studio。这将是我们的开发环境。
2. Aspose.PDF for .NET：您需要下载并安装 Aspose.PDF 库。您可以找到它[这里](https://releases.aspose.com/pdf/net/).
3. C# 基础知识：熟悉 C# 编程将帮助您更好地理解代码片段。
4. 示例 PDF 文件：准备好一个示例 PDF 文件以供我们使用。您可以创建一个简单的 PDF 文件或下载现有的 PDF 文件。

## 导入包

首先，我们需要导入必要的包。打开您的 Visual Studio 项目并添加对 Aspose.PDF 库的引用。您可以使用 NuGet 包管理器执行此操作：

1. 在解决方案资源管理器中右键单击您的项目。
2. 选择“管理 NuGet 包”。
3. 搜索“Aspose.PDF”并安装。

```csharp
using Aspose.Pdf.Text;
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

一旦安装了库，您就可以开始编码！

## 步骤 1：设置文档目录

首先，我们需要设置文档目录。这是我们存储输入和输出 PDF 文件的地方。 

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "42824.pdf";
string outFile = dataDir + "42824_out.pdf";
```

在此代码片段中，替换`YOUR DOCUMENT DIRECTORY`替换为 PDF 文件所在的实际路径。这将帮助我们加载现有 PDF 并保存修改后的版本。

## 步骤 2：加载现有 PDF 文件

现在我们已经设置了文档目录，让我们加载现有的 PDF 文件。 

```csharp
Document doc = new Document(inFile);
```

在这里，我们创建一个新的`Document`通过传递输入文件路径来获取 PDF 对象。这使我们能够以编程方式操作 PDF 内容。

## 步骤 3：为目录插入新页面

接下来，我们需要在 PDF 中创建一个新页面，用于存放目录。

```csharp
Aspose.Pdf.Page tocPage = doc.Pages.Insert(1);
```

此行在文档开头插入一个新页面。目录将显示在此页面上。

## 步骤 4：创建目录信息

现在，让我们创建一个对象来表示目录信息。

```csharp
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
tocInfo.PageNumbersPrefix = "P";
tocPage.TocInfo = tocInfo;
```

在此步骤中，我们创建一个`TocInfo`对象并将其标题设置为“目录”。我们还自定义了字体大小和样式。`PageNumbersPrefix`设置为“P”，它将作为目录中页码的前缀。

## 步骤 5：将标题添加到目录

现在到了最有趣的部分！我们将循环遍历文档的页面并将标题添加到目录中。

```csharp
for (int i = 1; i < doc.Pages.Count; i++)
{
    Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
    TextSegment segment2 = new TextSegment();
    heading2.TocPage = tocPage;
    heading2.Segments.Add(segment2);
    heading2.DestinationPage = doc.Pages[i + 1];
    heading2.Top = doc.Pages[i + 1].Rect.Height;
    segment2.Text = "Page " + i.ToString();
    tocPage.Paragraphs.Add(heading2);
}
```

在这个循环中，我们创建一个新的`Heading`为每个页面添加一个对象。我们为每个标题设置目标页面，并指定要显示的文本，即“第 X 页”，其中 X 是页码。最后，我们将标题添加到目录页面。

## 步骤 6：保存更新后的文档

添加所有必要的标题后，就可以保存更新后的文档了。

```csharp
doc.Save(outFile);
```

此行保存了修改后的 PDF 以及包含目录的内容。现在您可以打开输出文件并查看自定义的目录！

## 结论

就这样！您已成功自定义页码，同时使用 Aspose.PDF for .NET 向您的 PDF 文档添加目录。这个功能强大的库可让您轻松操作 PDF 文件，只需几行代码，您就可以显著增强文档。无论您是创建报告、电子书还是任何其他类型的 PDF，拥有目录都可以极大地改善读者的导航。那么，您还在等什么？立即深入了解 Aspose.PDF 并开始创建精彩的 PDF！

## 常见问题解答

### 什么是 Aspose.PDF for .NET？
Aspose.PDF for .NET 是一个库，允许开发人员以编程方式创建、操作和转换 PDF 文档。

### 我可以免费使用 Aspose.PDF 吗？
是的，Aspose 提供免费试用版，你可以使用它来探索该库的功能。你可以下载它[这里](https://releases.aspose.com/).

### 如何获得 Aspose.PDF 的支持？
您可以通过访问 Aspose 论坛获得支持[这里](https://forum.aspose.com/c/pdf/10).

### 有临时执照吗？
是的，您可以申请 Aspose.PDF 的临时许可证[这里](https://purchase.aspose.com/temporary-license/).

### 我可以在哪里购买 Aspose.PDF for .NET？
您可以购买 Aspose.PDF for .NET[这里](https://purchase.aspose.com/buy).