---
title: 页眉页脚中使用浮动框的页码
linktitle: 页眉页脚中使用浮动框的页码
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 文档的页眉和页脚中添加页码。
type: docs
weight: 150
url: /zh/net/programming-with-stamps-and-watermarks/page-number-in-header-footer-using-floating-box/
---
在本教程中，我们将逐步指导您如何使用 FloatingBox 和 Aspose.PDF for .NET 在 PDF 文档的页眉和页脚中添加页码。我们将使用提供的 C# 源代码创建 PDF 文档，添加页面，创建 FloatingBox，设置其位置并添加页码，然后保存修改后的 PDF 文档。

## 第一步：搭建环境

在开始之前，请确保您具备以下条件：

- 已安装的 .NET 开发环境。
- 下载用于 .NET 的 Aspose.PDF 库并在您的项目中引用。

## 第 2 步：创建 PDF 文档并添加页面

第一步是创建 PDF 文档的实例并向其中添加页面。就是这样：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//实例化 PDF 文档
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();

//向 PDF 文档添加页面
Aspose.Pdf.Page page = pdf.Pages.Add();
```

请务必将“您的文档目录”替换为您要保存 PDF 文档的目录的实际路径。

## 第三步：创建FloatingBox并添加页码

现在页面已添加到 PDF 文档中，我们可以创建一个 FloatingBox，设置其位置，并向其添加页码。就是这样：

```csharp
//创建一个宽度为 140、高度为 80 的 FloatingBox
Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(140, 80);

//设置段落的左侧位置
box1. Left = 2;

//设置段落顶部位置
box1. Top = 10;

//将页码添加到 FloatingBox
box1.Paragraphs.Add(new Aspose.Pdf.Text.TextFragment("Page: ($p/ $P )"));

//将FloatingBox添加到页面中
page.Paragraphs.Add(box1);
```

上面的代码创建了一个宽度为 140、高度为 80 的 FloatingBox。接下来，我们通过指定 left 和 top 值来设置其位置。最后，我们使用包含语法“($p/ $P )”的 TextFragment 将页码添加到 FloatingBox，该语法将替换为当前页码和总页数。

## 第四步：保存修改后的PDF文档

使用 FloatingBox 将页码添加到页眉或页脚后，我们就可以保存修改后的 PDF 文档。就是这样：

```csharp
//保存修改后的PDF文档
pdf.Save(dataDir + "PageNumberinHeaderFooterUsingFloatingBox_out.pdf");
```

上述代码将编辑后的PDF文档保存到指定目录。

### 使用 Aspose.PDF for .NET 使用浮动框在页眉页脚中页码的示例源代码 
```csharp

//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//实例化文档实例
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();

//将页面添加到 pdf 文档中
Aspose.Pdf.Page page = pdf.Pages.Add();

//初始化 FloatingBox 类的新实例
Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(140, 80);

//指示段落左侧位置的浮点值
box1.Left = 2;

//指示段落顶部位置的浮点值
box1.Top = 10;

//将宏添加到 FloatingBox 的段落集合中
box1.Paragraphs.Add(new Aspose.Pdf.Text.TextFragment("Page: ($p/ $P )"));

//给页面添加一个floatingBox
page.Paragraphs.Add(box1);

//保存文档
pdf.Save(dataDir + "PageNumberinHeaderFooterUsingFloatingBox_out.pdf");

```

## 结论

恭喜！您已经学习了如何使用 FloatingBox 和 Aspose.PDF for .NET 在 PDF 文档的页眉和页脚中添加页码。现在，您可以通过添加页码等动态信息来自定义页眉和页脚。

### 常见问题解答

#### 问：什么是 FloatingBox，如何使用它在 PDF 文档的页眉或页脚中添加页码？

答：FloatingBox 是 Aspose.PDF 中的多功能布局元素，可以容纳各种内容，包括文本和图像。在本教程中，它用于创建页码容器，允许您动态地将当前页码和总页数插入页眉或页脚中。

#### Q：提供的C#源码是如何实现使用FloatingBox添加页码的？

答：该代码片段演示了如何创建 PDF 文档、添加页面、创建 FloatingBox、设置其在页面内的位置以及使用 TextFragment 插入页码。 TextFragment 中的语法“($p/ $P )”被替换为当前页码和总页数。

#### 问：我可以自定义使用 FloatingBox 添加的页码的外观和格式吗？

答：是的，您可以通过修改 FloatingBox 内 TextFragment 的属性来自定义页码的外观。您可以更改字体大小、颜色、样式、对齐方式和其他格式选项。

#### 问：是否可以使用类似的方法向页眉或页脚添加不同的动态元素（例如日期和时间）？

答：当然，您可以通过修改 FloatingBox 中的 TextFragment 内容来添加不同的动态元素，例如日期、时间、文档元数据或自定义文本。您可以使用“($p/ $P )”等宏来表示页码，或使用“($date)”来表示当前日期。

#### 问：如何指定 FloatingBox 在页眉或页脚部分中的位置？
答：提供的代码使用以下命令设置 FloatingBox 的位置`Left`和`Top`特性。您可以调整这些值以根据需要在页眉或页脚部分中定位 FloatingBox。

#### 问：页眉或页脚中的页码可以使用不同的字体或样式吗？

答：是的，您可以通过修改 FloatingBox 中的 TextFragment 属性来自定义页码文本的字体、样式和其他格式属性。

#### 问：如果 FloatingBox 中的内容超出其尺寸会发生什么？

答：如果 FloatingBox 内的内容超出其尺寸，则可能会被截断或出现布局问题。确保 FloatingBox 的尺寸适合容纳内容，并根据需要考虑调整页面布局。

#### 问：是否可以在同一页面的页眉或页脚添加多个不同内容的FloatingBox？

答：是的，您可以通过创建单独的 FloatingBox 实例并将它们添加到页面的 Paragraphs 集合中，将多个具有不同内容的 FloatingBox 添加到同一页面的页眉或页脚。

#### 问：我可以使用 FloatingBox 方法将内容添加到 PDF 文档的其他部分，例如正文或页边距吗？

答：虽然 FloatingBox 通常用于页眉和页脚，但您也可以使用它们将内容添加到 PDF 文档的其他部分，例如正文或页边距，方法是将它们相应地定位在页面内。