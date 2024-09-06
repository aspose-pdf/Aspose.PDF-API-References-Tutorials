---
title: 获取文档窗口
linktitle: 获取文档窗口
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 的 GetDocumentWindow 功能来检索有关 PDF 文档窗口属性的信息。
type: docs
weight: 170
url: /zh/net/programming-with-document/getdocumentwindow/
---
Aspose.PDF for .NET 是一个功能强大的 PDF 操作库，允许开发人员在其 .NET 应用程序中创建、编辑和转换 PDF 文件。此库提供的功能之一是能够检索有关文档窗口属性的信息。本教程将指导您完成使用`GetDocumentWindow`Aspose.PDF for .NET 的功能用于检索有关 PDF 文档窗口属性的信息。

## 步骤 1：安装 Aspose.PDF for .NET

要在 .NET 应用程序中使用 Aspose.PDF for .NET，您必须首先安装该库。您可以从[Aspose.PDF for .NET 下载页面](https://releases.aspose.com/pdf/net).

下载库后，将 ZIP 文件的内容解压到计算机上的文件夹中。然后，您需要在 .NET 项目中添加对 Aspose.PDF for .NET DLL 的引用。

## 第 2 步：加载 PDF 文档

一旦安装了 Aspose.PDF for .NET 并在 .NET 项目中添加了对 DLL 的引用，您就可以开始使用`GetDocumentWindow`用于检索有关 PDF 文档窗口属性的信息的功能。

使用此功能的第一步是加载要检索信息的 PDF 文档。为此，您可以使用以下代码：

```csharp
// PDF 文档的路径
string dataDir = "YOUR DOCUMENT DIRECTORY";

//打开 PDF 文档
Document pdfDocument = new Document(dataDir + "GetDocumentWindow.pdf");
```

在上面的代码中，替换`"YOUR DOCUMENT DIRECTORY"`以及 PDF 文档所在目录的路径。此代码会将 PDF 文档加载到`Document`对象，然后您可以使用它来检索有关文档窗口属性的信息。

## 步骤 3：检索文档的窗口属性

要检索有关 PDF 文档窗口属性的信息，您可以使用以下代码：

```csharp
//检索文档的窗口属性
Console.WriteLine("CenterWindow : {0}", pdfDocument.CenterWindow);
Console.WriteLine("Direction : {0}", pdfDocument.Direction);
Console.WriteLine("DisplayDocTitle : {0}", pdfDocument.DisplayDocTitle);
Console.WriteLine("FitWindow : {0}", pdfDocument.FitWindow);
Console.WriteLine("HideMenuBar : {0}", pdfDocument.HideMenubar);
Console.WriteLine("HideToolBar : {0}", pdfDocument.HideToolBar);
Console.WriteLine("HideWindowUI : {0}", pdfDocument.HideWindowUI);
Console.WriteLine("NonFullScreenPageMode : {0}", pdfDocument.NonFullScreenPageMode);
Console.WriteLine("PageLayout : {0}", pdfDocument.PageLayout);
Console.WriteLine("pageMode : {0}", pdfDocument.PageMode);
```

在上面的代码中，每一行都会检索 PDF 文档的不同窗口属性并将其输出到控制台。您可以自定义此代码以仅检索您感兴趣的属性。

### 使用 Aspose.PDF for .NET 获取 PDF 文件文档窗口的示例源代码 

以下是使用以下函数检索 PDF 文档窗口属性的完整源代码：`GetDocumentWindow` Aspose.PDF for .NET的功能：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//打开文档
Document pdfDocument = new Document(dataDir + "GetDocumentWindow.pdf");

//获取不同的文档属性
//文档窗口的位置 - 默认值：false
Console.WriteLine("CenterWindow : {0}", pdfDocument.CenterWindow);

//主要阅读顺序；决定页面的位置
//并排显示时 - 默认：L2R
Console.WriteLine("Direction : {0}", pdfDocument.Direction);

//窗口的标题栏是否应显示文档标题
//如果为 false，则标题栏显示 PDF 文件名 - 默认值：false
Console.WriteLine("DisplayDocTitle : {0}", pdfDocument.DisplayDocTitle);

//是否调整文档窗口的大小以适应
//第一个显示的页面 - 默认值：false
Console.WriteLine("FitWindow : {0}", pdfDocument.FitWindow);

//是否隐藏查看器应用程序的菜单栏 - 默认值：false
Console.WriteLine("HideMenuBar : {0}", pdfDocument.HideMenubar);

//是否隐藏查看器应用程序的工具栏 - 默认值：false
Console.WriteLine("HideToolBar : {0}", pdfDocument.HideToolBar);

//是否隐藏滚动条等 UI 元素
//仅显示页面内容 - 默认值：false
Console.WriteLine("HideWindowUI : {0}", pdfDocument.HideWindowUI);

//文档的页面模式。如何在退出全屏模式时显示文档。
Console.WriteLine("NonFullScreenPageMode : {0}", pdfDocument.NonFullScreenPageMode);

//页面布局即单页，单列
Console.WriteLine("PageLayout : {0}", pdfDocument.PageLayout);

//文档打开时应如何显示
//即显示缩略图、全屏、显示附件面板
Console.WriteLine("pageMode : {0}", pdfDocument.PageMode);
```

## 结论

在本教程中，我们学习了如何使用 Aspose.PDF for .NET 检索有关 PDF 文档窗口属性的信息。通过加载 PDF 文档并访问其窗口属性，您可以收集有关在查看器应用程序中打开时应如何显示文档的信息。Aspose.PDF for .NET 提供了一组强大的功能，可用于以编程方式处理 PDF 文件，使其成为 .NET 应用程序中 PDF 操作的宝贵工具。

### 常见问题解答

#### 问：检索 PDF 文档的窗口属性的目的是什么？

答：检索 PDF 文档的窗口属性可让您收集有关在查看器应用程序中打开时应如何显示 PDF 文档的信息。这些属性控制各个方面，例如窗口位置、显示模式和 UI 元素的可见性。

#### 问：如何在我的.NET 项目中安装 Aspose.PDF for .NET？

答：要安装 Aspose.PDF for .NET，您需要从[Aspose.PDF for .NET 下载页面](https://releases.aspose.com/pdf/net)。下载后，解压ZIP文件的内容并在您的.NET项目中添加对Aspose.PDF for .NET DLL的引用。

#### 问：我可以自定义代码以仅检索特定的窗口属性吗？

答：是的，您可以通过注释掉不需要的行来自定义代码以检索特定的窗口属性。代码中的每一行都对应一个特定的窗口属性，因此您可以根据需要包含或排除属性。

#### 问：使用 Aspose.PDF for .NET 可以检索哪些类型的窗口属性？

答：使用 Aspose.PDF for .NET，您可以检索 PDF 文档的各种窗口属性，包括居中窗口、设置页面布局、控制工具栏和菜单栏的显示等。