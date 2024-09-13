---
title: 获取文档窗口
linktitle: 获取文档窗口
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 的 GetDocumentWindow 功能来检索有关 PDF 文档窗口属性的信息。
type: docs
weight: 170
url: /zh/net/programming-with-document/getdocumentwindow/
---
# 介绍

您是否正在使用 PDF 并希望更好地控制它们打开时的外观？无论是隐藏菜单栏还是调整窗口大小以适合第一页，Aspose.Pdf for .NET 都为您提供了自定义 PDF 在查看器中打开时的行为所需的所有工具。在本教程中，我们将详细介绍如何在 Aspose.Pdf for .NET 中检索和操作文档窗口设置。


# 先决条件

在深入学习本教程之前，请确保您已满足以下先决条件：

- 在您的开发环境中安装 Aspose.PDF for .NET。
  - [下载 Aspose.PDF for .NET](https://releases.aspose.com/pdf/net/)
-  Aspose.PDF 的有效许可证，或者您可以获取[免费试用](https://releases.aspose.com/)或者[临时执照](https://purchase.aspose.com/temporary-license/).
- 对 .NET 和 C# 有基本的了解。
- Visual Studio 或其他合适的 IDE。

# 导入包

在开始编写任何代码之前，您需要导入必要的包。打开您的项目，然后在 C# 文件的顶部添加以下命名空间：

```csharp
using System.IO;
using System;
using Aspose.Pdf;
```

这将使您能够访问使用 Aspose.PDF for .NET 处理 PDF 文档所需的所有类和方法。

现在让我们分解一下检索不同文档窗口设置的过程。在本示例中，我们将使用名为`GetDocumentWindow.pdf`.

## 步骤 1：设置文档目录路径

首先，我们需要定义 PDF 文件的路径。拥有正确的文件路径至关重要，以避免执行过程中出现任何错误。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

在这里，替换`"YOUR DOCUMENT DIRECTORY"`替换为 PDF 文件所在的实际目录。这是您加载 PDF 文档的工作目录。

## 第 2 步：打开 PDF 文档

现在文件路径已设置，下一步是使用 Aspose.PDF 打开 PDF 文档。这会将文档加载到内存中，以便您检索其属性。

```csharp
Document pdfDocument = new Document(dataDir + "GetDocumentWindow.pdf");
```

通过这行简单的代码，您已成功将 PDF 文件加载到`pdfDocument`对象，现在您可以访问其所有属性。

## 步骤 3：检索窗口居中状态

接下来，让我们检查文档窗口在打开时是否应居中。默认值为`false`.

```csharp
Console.WriteLine("CenterWindow : {0}", pdfDocument.CenterWindow);
```

如果输出是`true`，文档窗口将在屏幕中央打开。否则，它将在默认位置打开。

## 步骤 4：检查文本方向

PDF 外观的另一个重要方面是文本方向，它决定了文本是从左到右 (L2R) 还是从右到左 (R2L) 阅读。您可以使用以下代码检索此信息：

```csharp
Console.WriteLine("Direction : {0}", pdfDocument.Direction);
```

输出将是`L2R`对于从左到右的文本和`R2L`适用于从右到左的文本。此设置对于阿拉伯语或希伯来语等语言的文档特别有用。

## 步骤 5：在窗口中显示文档标题

下一个属性允许您控制文档标题或文件名是否显示在窗口的标题栏上。默认情况下，此属性设置为`false`，表示将显示文件名。

```csharp
Console.WriteLine("DisplayDocTitle : {0}", pdfDocument.DisplayDocTitle);
```

如果您希望显示文档的标题而不是文件名，则必须启用此设置。

## 步骤 6：调整窗口大小以适合第一页

有时，您可能希望文档窗口在打开时自动调整大小以适合 PDF 的第一页。以下是检查该功能是否已启用的方法：

```csharp
Console.WriteLine("FitWindow : {0}", pdfDocument.FitWindow);
```

默认情况下，设置为`false`，这意味着无论第一页的大小如何，窗口大小都将保持原样。

## 步骤 7：隐藏菜单栏

为了获得更专注的阅读体验，您可能希望隐藏查看器应用程序的菜单栏。您可以使用以下行检索此设置：

```csharp
Console.WriteLine("HideMenuBar : {0}", pdfDocument.HideMenubar);
```

这将返回`true`如果菜单栏被隐藏，并且`false`否则。

## 步骤 8：隐藏工具栏

同样，您可能还想隐藏 PDF 查看器中的工具栏，以获得更简洁的用户界面。此设置可以按如下方式检索：

```csharp
Console.WriteLine("HideToolBar : {0}", pdfDocument.HideToolBar);
```

如果启用此设置，则打开 PDF 时工具栏将被隐藏。

## 步骤 9：隐藏滚动条和 UI 元素

如果您希望仅显示页面内容而不显示任何其他 UI 元素（如滚动条），则此设置可以控制该行为：

```csharp
Console.WriteLine("HideWindowUI : {0}", pdfDocument.HideWindowUI);
```

当设置为`true`，PDF 查看器将隐藏滚动条和其他用户界面元素，只留下文档内容。

## 步骤 10：设置非全屏页面模式

您可以使用`NonFullScreenPageMode`属性。此设置有助于定义用户在非全屏模式下应如何与文档交互。

```csharp
Console.WriteLine("NonFullScreenPageMode : {0}", pdfDocument.NonFullScreenPageMode);
```

输出可以设置为不同的模式，如缩略图、轮廓或附件面板。

## 步骤 11：定义页面布局

此设置允许您控制文档页面的布局方式。例如，您可以选择单页视图或连续列视图：

```csharp
Console.WriteLine("PageLayout : {0}", pdfDocument.PageLayout);
```

这使得用户可以灵活地阅读或查看文档内容。

## 步骤 12：指定页面模式

最后，`PageMode`属性定义文档打开时的显示方式。选项包括显示缩略图、进入全屏模式或显示附件面板。

```csharp
Console.WriteLine("PageMode : {0}", pdfDocument.PageMode);
```

根据您的需要，您可以将其设置为适合您的 PDF 用途的任何模式。

## 结论

如您所见，Aspose.PDF for .NET 提供了全面的工具来控制 PDF 文档在各种 PDF 查看器中的显示方式。无论您是想隐藏工具栏、将窗口居中还是控制文本方向，Aspose.PDF 都能提供灵活性来增强用户的查看体验。

# 常见问题解答

### 我可以自定义 PDF 的初始缩放级别吗？
是的，Aspose.PDF 允许您设置文档打开时的缩放级别。

### 如何锁定 PDF 的窗口大小？
您可以设置`FitWindow`属性来防止窗口调整大小。

### Aspose.PDF 是否支持不同的阅读模式？
是的，它支持全屏、缩略图和附件等不同模式。

### 是否可以隐藏 PDF 查看器中的滚动条？
当然，你可以通过设置`HideWindowUI`财产`true`.

### 我可以将文档窗口打开后置于中央吗？
是的，您可以通过设置来控制`CenterWindow`财产。