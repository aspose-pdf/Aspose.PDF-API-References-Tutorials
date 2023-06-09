---
title: 页眉页脚中使用浮动框的页码
linktitle: 页眉页脚中使用浮动框的页码
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 文档的页眉和页脚中添加页码。
type: docs
weight: 150
url: /zh/net/programming-with-stamps-and-watermarks/page-number-in-header-footer-using-floating-box/
---
在本教程中，我们将逐步指导您如何使用 FloatingBox 和 Aspose.PDF for .NET 在 PDF 文档的页眉和页脚中添加页码。我们将使用提供的 C# 源代码创建一个 PDF 文档，添加一个页面，创建一个 FloatingBox，设置其位置并为其添加页码，然后保存修改后的 PDF 文档。

## 第 1 步：设置环境

在开始之前，请确保您具备以下条件：

- 已安装的 .NET 开发环境。
- 在您的项目中下载并引用了用于 .NET 的 Aspose.PDF 库。

## 第 2 步：创建 PDF 文档并添加页面

第一步是创建 PDF 文档的实例并向其添加页面。就是这样：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//实例化PDF文档
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();

//向 PDF 文档添加页面
Aspose.Pdf.Page page = pdf.Pages.Add();
```

请务必将“您的文档目录”替换为您要保存 PDF 文档的目录的实际路径。

## 第 3 步：创建 FloatingBox 并添加页码

现在页面已添加到 PDF 文档中，我们可以创建一个 FloatingBox，设置其位置，并为其添加页码。就是这样：

```csharp
//创建一个宽为140，高为80的FloatingBox
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

上面的代码创建了一个宽度为 140，高度为 80 的 FloatingBox。接下来，我们通过指定 left 和 top 值来设置它的位置。最后，我们使用包含语法“($p/ $P )”的 TextFragment 将页码添加到 FloatingBox，该语法将替换为当前页码和总页数。

## 第 4 步：保存修改后的 PDF 文档

使用 FloatingBox 将页码添加到页眉或页脚后，我们就可以保存修改后的 PDF 文档。就是这样：

```csharp
//保存修改后的 PDF 文档
pdf.Save(dataDir + "PageNumberinHeaderFooterUsingFloatingBox_out.pdf");
```

上述代码将编辑好的PDF文档保存到指定目录。

### 使用 Aspose.PDF for .NET 使用浮动框的页码页眉页脚示例源代码 
```csharp

//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//实例化文档实例
Aspose.Pdf.Document pdf = new Aspose.Pdf.Document();

//在pdf文档中添加一个页面
Aspose.Pdf.Page page = pdf.Pages.Add();

//初始化 FloatingBox 类的新实例
Aspose.Pdf.FloatingBox box1 = new Aspose.Pdf.FloatingBox(140, 80);

//指示段落左侧位置的浮点值
box1.Left = 2;

//指示段落顶部位置的浮点值
box1.Top = 10;

//将宏添加到 FloatingBox 的段落集合
box1.Paragraphs.Add(new Aspose.Pdf.Text.TextFragment("Page: ($p/ $P )"));

//在页面中添加一个浮动框
page.Paragraphs.Add(box1);

//保存文件
pdf.Save(dataDir + "PageNumberinHeaderFooterUsingFloatingBox_out.pdf");

```

## 结论

恭喜！您已经学习了如何使用 FloatingBox 和 Aspose.PDF for .NET 在 PDF 文档的页眉和页脚中添加页码。您现在可以通过添加页码等动态信息来自定义页眉和页脚。
