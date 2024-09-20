---
title: 搜索文本并绘制矩形
linktitle: 搜索文本并绘制矩形
second_title: Aspose.PDF for .NET API 参考
description: 学习使用 Aspose.PDF for .NET 在 PDF 中搜索文本并用矩形突出显示！简单的分步教程可增强 PDF 操作技能。
type: docs
weight: 460
url: /zh/net/programming-with-text/search-text-and-draw-rectangle/
---
## 介绍

您是否希望提高 PDF 操作技能？您是否想学习如何在 PDF 文件中搜索特定文本并用矩形突出显示它？您已经找到了完美的指南！今天，我将引导您了解如何使用 Aspose.PDF for .NET 在 PDF 文档中搜索文本并在其周围绘制矩形。本文将提供一个循序渐进的教程，该教程设计时考虑到了清晰度和实用性，确保您可以遵循并将这些技术应用于您的项目。 

## 先决条件

在深入学习本教程之前，让我们先准备好所需的一切以确保工作流程顺畅：

1. 对 .NET 的基本了解：您应该熟悉 C# 编程和 .NET 框架才能有效地学习本教程。
   
2. 已安装 Visual Studio：您需要一个集成开发环境 (IDE) 来编写和测试代码。Visual Studio Community 是一个不错的选择，而且是免费的。
   
3. Aspose.PDF for .NET：您需要在项目中安装 Aspose.PDF 库。您可以下载它[这里](https://releases.aspose.com/pdf/net/)或者考虑[临时执照](https://purchase.aspose.com/temporary-license/)以获得扩展功能。
   
4. 示例 PDF 文档：对于本教程，您将需要一个名为的示例 PDF 文件`SearchAndGetTextFromAll.pdf`存储在您的项目目录中。 

## 导入包

首先，您需要将必要的包导入到 .NET 项目中。请按以下步骤操作：

### 打开 Visual Studio

启动 Visual Studio 并创建一个新的控制台应用程序或使用您想要实现 PDF 功能的现有控制台应用程序。

### 将 Aspose.PDF 添加到您的项目中

1. 在解决方案资源管理器中右键单击您的项目。
2. 选择“管理 NuGet 包”。
3. 搜索`Aspose.PDF`并安装最新版本。

通过这样做，您为即将执行的所有令人惊叹的 PDF 操作奠定了基础。

## 导入命名空间

在程序文件的顶部，您需要从 Aspose 库导入相关的命名空间：

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
using Aspose.Pdf.Facades;
```

这使得您可以更轻松地访问 Aspose.PDF 库中的类和方法来完成您的任务。


现在您已完成所有设置，让我们将在 PDF 中搜索文本并在其周围绘制矩形的过程分解为易于管理的步骤。

## 步骤 1：设置文档路径

首先，设置 PDF 文件的路径。确保替换`YOUR DOCUMENT DIRECTORY`实际路径`SearchAndGetTextFromAll.pdf`被存储。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：打开 PDF 文档

接下来，创建一个实例`Document`加载 PDF 的类：

```csharp
Document document = new Document(dataDir + "SearchAndGetTextFromAll.pdf");
```

这行代码打开您指定的 PDF 文件，允许您进一步操作它。

## 步骤 3：创建文本吸收器

现在，您需要一种方法来搜索该文档中的文本。为此，我们使用`TextFragmentAbsorber`：

```csharp
TextFragmentAbsorber textAbsorber = new TextFragmentAbsorber(@"[\S]+");
```

正则表达式`@"[\S]+"`旨在匹配 PDF 中的任何非空白字符串。 

## 步骤 4：配置文本搜索选项

接下来，您应该设置文本搜索选项：

```csharp
TextSearchOptions textSearchOptions = new TextSearchOptions(true);
textAbsorber.TextSearchOptions = textSearchOptions;
```

在这里，`true`参数表示搜索将区分大小写。您可以将其设置为`false`如果您想要不区分大小写的搜索。

## 步骤 5：接受文档中的文本吸收器

与你的`TextFragmentAbsorber`并且搜索选项已经准备好，现在是时候从文档中吸收文本了：

```csharp
document.Pages.Accept(textAbsorber);
```

此方法检查 PDF 中的每一页以查找符合指定模式的文本片段。

## 步骤 6：创建 PdfContentEditor

要在文档上绘制形状，您需要`PdfContentEditor`：

```csharp
var editor = new PdfContentEditor(document);
```

该编辑器允许您轻松操作和编辑 PDF 内容。

## 步骤 7：循环查找找到的文本片段

现在，您需要循环遍历找到的文本片段以在它们周围绘制矩形：

```csharp
foreach (TextFragment textFragment in textAbsorber.TextFragments)
{
    foreach (TextSegment textSegment in textFragment.Segments)
    {
        DrawBox(editor, textFragment.Page.Number, textSegment, System.Drawing.Color.Red);
    }
}
```

此循环遍历每个文本片段及其段，调用`DrawBox`矩形的绘制方法。

## 步骤 8：定义 DrawBox 方法

您需要定义`DrawBox`方法，它将处理矩形绘制逻辑。以下是一个简单的实现：

```csharp
private static void DrawBox(PdfContentEditor editor, int pageNumber, TextSegment textSegment, System.Drawing.Color color)
{
    //根据文本段计算矩形尺寸
    float x = textSegment.Rectangle.LLX;
    float y = textSegment.Rectangle.LLY;
    float width = textSegment.Rectangle.Width;
    float height = textSegment.Rectangle.Height;

    //使用计算值绘制矩形
    editor.DrawRectangle(pageNumber, x, y, width, height, color, 1);
}
```

该方法根据线段的边界矩形确定矩形的位置和大小，并使用编辑器来绘制它。

## 步骤 9：保存修改后的文档

在找到的文本周围绘制矩形后，您可以保存修改后的文档：

```csharp
dataDir = dataDir + "SearchTextAndDrawRectangle_out.pdf";
document.Save(dataDir);
```

确保新文件以不同的名称保存，以避免覆盖原始文档。

## 步骤 10：确认信息

最后，向控制台打印一条确认消息，让你知道操作成功：

```csharp
Console.WriteLine("\nRectangle drawn successfully on searched text.\nFile saved at " + dataDir);
```

就这样！您已成功创建脚本来搜索 PDF 中的文本并用矩形突出显示它。

## 结论

恭喜！您刚刚解锁了一项强大的技能，该技能可以大大增强您使用 Aspose.PDF for .NET 处理 PDF 的能力。只需几个简单的步骤，您就可以搜索文档中的任何文本并以视觉方式突出显示它，从而使您的 PDF 文档更具交互性和可管理性。不要犹豫，尝试不同的正则表达式模式和颜色选项，真正让这个工具成为您自己的！

## 常见问题解答

### 什么是 Aspose.PDF for .NET？
Aspose.PDF for .NET 是一个库，它提供了一种以编程方式创建、操作和转换 PDF 文档的全面方法。

### 我可以免费使用 Aspose.PDF 吗？
是的，Aspose 提供免费试用，你可以使用它来测试该库的功能。查看[这里](https://releases.aspose.com/).

### 我需要使用哪种编程语言来使用 Aspose.PDF for .NET？
Aspose.PDF for .NET 设计用于 C# 和其他 .NET 语言。

### 如何获得 Aspose.PDF 的帮助？
您可以访问 Aspose 支持论坛，获取有关您可能遇到的任何问题或疑问的帮助。 查找支持[这里](https://forum.aspose.com/c/pdf/10).

### 我在哪里可以下载 Aspose.PDF for .NET？
您可以从 Aspose 网站下载该库，[这里](https://releases.aspose.com/pdf/net/).