---
title: 从 HTML 转换后删除超链接
linktitle: 从 HTML 转换后删除超链接
second_title: Aspose.PDF for .NET API 参考
description: 在本分步指南中了解如何使用 Aspose.PDF for .NET 将 HTML 文档转换为 PDF 后从 HTML 文档中删除超链接。
type: docs
weight: 250
url: /zh/net/document-conversion/remove-hyperlinks-after-converting-from-html/
---
## 介绍

在数字时代，将 HTML 文档转换为 PDF 是一项常见任务。但是，有时您可能出于各种原因（例如增强可读性或防止不必要的导航）想要从转换后的 PDF 中删除超链接。在本教程中，我们将探讨如何使用 Aspose.PDF for .NET 实现此目的。 

## 先决条件

在深入研究代码之前，请确保您满足以下先决条件：

1. Visual Studio：确保您的机器上安装了 Visual Studio。这将是您的开发环境。
2.  Aspose.PDF for .NET：您需要有 Aspose.PDF 库。您可以从以下位置下载[这里](https://releases.aspose.com/pdf/net/).
3. C# 基础知识：熟悉 C# 编程将帮助您更好地理解代码。

## 导入包

首先，您需要在 C# 项目中导入必要的包。具体操作如下：

1. 打开您的 Visual Studio 项目。
2. 在解决方案资源管理器中右键单击您的项目并选择“管理 NuGet 包”。
3. 搜索`Aspose.PDF`并安装它。

```csharp
using Aspose.Pdf.Annotations;
using Aspose.Pdf.Text;
using System.IO;
```

现在您已完成所有设置，让我们分解一下将 HTML 文件转换为 PDF 后从中删除超链接的过程。

## 步骤 1：设置文档目录

首先，您需要指定文档目录的路径。这是 HTML 文件所在的位置，也是输出 PDF 的保存位置。

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

代替`"YOUR DOCUMENT DIRECTORY"`使用存储 HTML 文件的实际路径。

## 步骤 2：加载 HTML 文档

接下来，您将使用`Document`来自 Aspose.PDF 的类。该类可让您轻松处理 PDF 文档。

```csharp
Document doc = new Document(dataDir + "SampleHtmlFile.html", new HtmlLoadOptions());
```

在这里，我们正在加载名为`SampleHtmlFile.html`确保此文件存在于您指定的目录中。

## 步骤 3：将文档保存到内存流

在开始处理注释之前，我们需要将文档保存到内存流中。此步骤至关重要，因为它为文档的进一步操作做好了准备。

```csharp
doc.Save(new MemoryStream());
```

此行将文档保存在内存中，使我们能够使用它而不必将其写入磁盘。

## 步骤 4：迭代注释

现在，我们将遍历文档中的注释。注释是链接、注释和突出显示等元素。我们对链接注释特别感兴趣。

```csharp
foreach (Annotation a in doc.Pages[1].Annotations)
{
    if (a.AnnotationType == AnnotationType.Link)
    {
        //处理链接注释
    }
}
```

在这个循环中，我们检查注释类型是否为链接。如果是，我们继续下一步。

## 步骤 5：删除超链接操作

对于每个链接注释，我们需要检查它是否具有超链接操作。如果有，我们将通过将其 URI 设置为空字符串来删除超链接。

```csharp
LinkAnnotation la = (LinkAnnotation)a;
if (la.Action is GoToURIAction)
{
    GoToURIAction gta = (GoToURIAction)la.Action;
    gta.URI = "";
```

此代码片段确保超链接操作被有效删除。

## 步骤 6：吸收文本片段

接下来，我们将吸收与链接注释相关的文本片段。这使我们能够操纵文本的外观。

```csharp
TextFragmentAbsorber tfa = new TextFragmentAbsorber();
tfa.TextSearchOptions = new TextSearchOptions(a.Rect);
doc.Pages[a.PageIndex].Accept(tfa);
```

在这里，我们创建一个`TextFragmentAbsorber`并将其搜索选项设置为注释的矩形。这有助于我们找到链接的文本。

## 步骤 7：修改文本外观

一旦我们有了文本片段，我们就可以修改它们的外观。在本例中，我们将删除下划线并将文本颜色更改为黑色。

```csharp
foreach (TextFragment tf in tfa.TextFragments)
{
    tf.TextState.Underline = false;
    tf.TextState.ForegroundColor = Color.Black;
}
```

此步骤通过删除超链接样式来增强文本的可读性。

## 步骤 8：删除注释

修改文本后，我们可以安全地从文档中删除链接注释。

```csharp
doc.Pages[a.PageIndex].Annotations.Delete(a);
}
```

此行将从 PDF 中删除超链接，确保它不再存在于最终输出中。

## 步骤 9：保存修改后的文档

最后，我们需要将修改后的文档保存为新的 PDF 文件。这是我们流程的最后一步。

```csharp
doc.Save(dataDir + "RemoveHyperlinksFromText_out.pdf");
```

此行将保存文档并删除超链接，并创建一个名为`RemoveHyperlinksFromText_out.pdf`.

## 结论

就这样！使用 Aspose.PDF for .NET 将 HTML 文档转换为 PDF 后，您已成功从 HTML 文档中删除超链接。此过程不仅增强了 PDF 的可读性，还使您能够控制所呈现的内容。 

## 常见问题解答

### 我可以从任何 PDF 文档中删除超链接吗？
是的，您可以使用 Aspose.PDF for .NET 从任何 PDF 文档中删除超链接。

### Aspose.PDF 可以免费使用吗？
 Aspose.PDF 提供免费试用，但要使用完整功能，您需要购买许可证。检查[购买页面](https://purchase.aspose.com/buy).

### 如果在使用 Aspose.PDF 时遇到问题怎么办？
您可以在[支持论坛](https://forum.aspose.com/c/pdf/10).

### 我可以使用 Aspose 将所有文件格式转换为 PDF 吗？
是的，Aspose 支持各种文件格式转换为 PDF。

### 我可以在哪里下载 Aspose.PDF for .NET？
您可以从[下载链接](https://releases.aspose.com/pdf/net/).