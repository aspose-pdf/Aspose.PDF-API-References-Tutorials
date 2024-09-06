---
title: 使用浮动框在页眉页脚中显示页码
linktitle: 使用浮动框在页眉页脚中显示页码
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 文档的页眉和页脚中添加页码。
type: docs
weight: 150
url: /zh/net/programming-with-stamps-and-watermarks/page-number-in-header-footer-using-floating-box/
---
在本教程中，我们将逐步指导您如何使用 Aspose.PDF for .NET 的 FloatingBox 在 PDF 文档的页眉和页脚中添加页码。我们将使用提供的 C# 源代码创建 PDF 文档、添加页面、创建 FloatingBox、设置其位置并向其添加页码，然后保存修改后的 PDF 文档。

## 步骤 1：设置环境

开始之前，请确保您已准备好以下物品：

- 已安装的 .NET 开发环境。
- 已下载并引用适用于 .NET 的 Aspose.PDF 库到您的项目中。

## 步骤 2：创建 PDF 文档并添加页面

第一步是创建 PDF 文档的实例并向其中添加页面。操作方法如下：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//实例化 PDF 文档
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();

//向 PDF 文档添加页面
Aspose.Pdf.Page page = pdf.Pages.Add();
```

请务必将“YOUR DOCUMENTS DIRECTORY”替换为您想要保存 PDF 文档的目录的实际路径。

## 步骤 3：创建 FloatingBox 并添加页码

现在页面已添加到 PDF 文档中，我们可以创建一个 FloatingBox、设置其位置并向其添加页码。操作方法如下：

```csharp
//创建一个宽度为 140、高度为 80 的 FloatingBox
Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(140, 80);

//设置段落的左侧位置
box1. Left = 2;

//设置段落的顶部位置
box1. Top = 10;

//将页码添加到 FloatingBox
box1.Paragraphs.Add(new Aspose.Pdf.Text.TextFragment("Page: ($p/ $P )"));

//将 FloatingBox 添加到页面
page.Paragraphs.Add(box1);
```

上述代码创建了一个宽度为 140、高度为 80 的 FloatingBox。接下来，我们通过指定左侧和顶部的值来设置其位置。最后，我们使用包含语法“($p/ $P )”的 TextFragment 将页码添加到 FloatingBox，该语法将被替换为当前页码和总页数。

## 步骤 4：保存修改后的 PDF 文档

使用 FloatingBox 将页码添加到页眉或页脚后，我们就可以保存修改后的 PDF 文档。操作方法如下：

```csharp
//保存修改后的PDF文档
pdf.Save(dataDir + "PageNumberinHeaderFooterUsingFloatingBox_out.pdf");
```

上述代码将编辑后的PDF文档保存到指定目录。

### 使用 Aspose.PDF for .NET 的浮动框在页眉页脚中添加页码的示例源代码 
```csharp

//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//实例化 Document 实例
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();

//在 PDF 文档中添加页面
Aspose.Pdf.Page page = pdf.Pages.Add();

//初始化 FloatingBox 类的新实例
Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(140, 80);

//表示段落左侧位置的浮点值
box1.Left = 2;

//表示段落顶部位置的浮点值
box1.Top = 10;

//将宏添加到 FloatingBox 的段落集合中
box1.Paragraphs.Add(new Aspose.Pdf.Text.TextFragment("Page: ($p/ $P )"));

//在页面中添加一个 floatingBox
page.Paragraphs.Add(box1);

//保存文档
pdf.Save(dataDir + "PageNumberinHeaderFooterUsingFloatingBox_out.pdf");

```

## 结论

恭喜！您已经学会了如何使用 Aspose.PDF for .NET 中的 FloatingBox 在 PDF 文档的页眉和页脚中添加页码。现在您可以通过添加页码等动态信息来自定义页眉和页脚。

### 常见问题解答

#### 问：什么是 FloatingBox，如何使用它在 PDF 文档的页眉或页脚中添加页码？

答：FloatingBox 是 Aspose.PDF 中一个多功能的布局元素，可以容纳各种内容，包括文本和图像。在本教程中，它用于创建页码容器，允许您将当前页码和总页数动态插入到页眉或页脚中。

#### 问：提供的 C# 源代码如何实现使用 FloatingBox 添加页码？

答：代码片段演示了如何创建 PDF 文档、添加页面、创建 FloatingBox、设置其在页面中的位置以及使用 TextFragment 插入页码。TextFragment 中的语法“($p/ $P )”将替换为当前页码和总页数。

#### 问：我可以自定义使用 FloatingBox 添加的页码的外观和格式吗？

答：是的，您可以通过修改 FloatingBox 中的 TextFragment 属性来自定义页码的外观。您可以更改字体大小、颜色、样式、对齐方式和其他格式选项。

#### 问：是否可以使用类似的方法向页眉或页脚添加不同的动态元素，例如日期和时间？

答：当然可以，您可以通过修改 FloatingBox 中的 TextFragment 内容来添加不同的动态元素，如日期、时间、文档元数据或自定义文本。您可以使用宏，例如“($p/ $P )”来显示页码，或使用“($date)”来显示当前日期。

#### 问：如何指定 FloatingBox 在页眉或页脚部分中的位置？
答：提供的代码使用`Left`和`Top`属性。您可以调整这些值以根据需要在页眉或页脚部分中定位 FloatingBox。

#### 问：我可以在页眉或页脚中为页码使用不同的字体或样式吗？

答：是的，您可以通过修改 FloatingBox 内的 TextFragment 属性来自定义页码文本的字体、样式和其他格式属性。

#### 问：如果 FloatingBox 中的内容超出其尺寸会发生什么情况？

答：如果 FloatingBox 中的内容超出其尺寸，则可能会被截断或出现布局问题。请确保 FloatingBox 的尺寸适合容纳内容，并考虑根据需要调整页面布局。

#### 问：是否可以在同一页面的页眉或页脚中添加多个具有不同内容的 FloatingBox？

答：是的，您可以通过创建单独的 FloatingBox 实例并将它们添加到页面的 Paragraphs 集合中，将具有不同内容的多个 FloatingBox 添加到同一页面的页眉或页脚。

#### 问：我可以使用 FloatingBox 方法将内容添加到 PDF 文档的其他部分，例如正文或边距吗？

答：虽然浮动框通常用于页眉和页脚，但您也可以使用它们将内容添加到 PDF 文档的其他部分，例如正文或页边距，方法是在页面内相应地定位它们。