---
title: 添加文本边框
linktitle: 添加文本边框
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 将文本边框添加到 PDF 文档。
type: docs
weight: 70
url: /zh/net/programming-with-text/add-text-border/
---

本教程将指导您完成使用 Aspose.PDF for .NET 添加文本边框的过程。提供的 C# 源代码演示了必要的步骤。

## 要求
在开始之前，请确保您具备以下条件：

- Visual Studio 或计算机上安装的任何其他 C# 编译器。
- Aspose.PDF for .NET 库。您可以从 Aspose 官方网站下载它或使用 NuGet 等包管理器来安装它。

## 第 1 步：设置项目
1. 在您首选的开发环境中创建一个新的 C# 项目。
2. 添加对 Aspose.PDF for .NET 库的引用。

## 第2步：导入所需的命名空间
在要添加文本边框的代码文件中，在文件顶部添加以下 using 指令：

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## 第三步：设置文档目录
在代码中，找到显示以下内容的行`string dataDir = "YOUR DOCUMENT DIRECTORY";`并替换`"YOUR DOCUMENT DIRECTORY"`以及存储文档的目录的路径。

## 步骤 4：创建一个新的 Document 对象
实例化一个新的`Document`对象，添加以下代码行：

```csharp
Document pdfDocument = new Document();
```

## 步骤 5：向文档添加页面
使用以下命令将新页面添加到文档中`Add`的方法`Pages`收藏。在提供的代码中，新页面被分配给变量`pdfPage`.

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

## 第 6 步：创建一个 TextFragment
创建一个`TextFragment`对象并提供所需的文本。使用设置文本片段的位置`Position`财产。在提供的代码中，文本设置为“主文本”并位于页面上的 (100, 600) 处。

```csharp
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
```

## 第 7 步：设置文本属性
自定义文本属性，如字体大小、字体类型、背景颜色、前景色等。在提供的代码中，为文本片段设置字体大小、字体、背景颜色、前景色和描边颜色等属性。

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
```

## 第 8 步：启用文本边框
要启用文本边框，请设置`DrawTextRectangleBorder`文本片段的属性`TextState`到`true`.

```csharp
textFragment.TextState.DrawTextRectangleBorder = true;
```

## 第9步：将TextFragment添加到页面
使用`TextBuilder`类来添加`TextFragment`反对该页面。

```csharp
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
```

## 第10步：保存PDF文档
使用以下命令保存 PDF 文档`Save`的方法`Document`目的。指定您在步骤 3 中设置的输出文件路径。

```csharp
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

### 使用 Aspose.PDF for .NET 添加文本边框的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//创建新文档对象
Document pdfDocument = new Document();
//获取特定页面
Page pdfPage = (Page)pdfDocument.Pages.Add();
//创建文本片段
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
//设置文本属性
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
//设置 StrokingColor 属性以在文本矩形周围绘制边框（描边）
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
//将 DrawTextRectangleBorder 属性值设置为 true
textFragment.TextState.DrawTextRectangleBorder = true;
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
//保存文档
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

## 结论
您已使用 Aspose.PDF for .NET 成功向 PDF 文档添加文本边框。现在可以在指定的输出文件路径中找到生成的 PDF 文件。