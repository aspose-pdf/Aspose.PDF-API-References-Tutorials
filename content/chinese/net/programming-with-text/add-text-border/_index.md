---
title: 在 PDF 文件中添加文本边框
linktitle: 在 PDF 文件中添加文本边框
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 文件中添加文本边框。
type: docs
weight: 70
url: /zh/net/programming-with-text/add-text-border/
---
本教程将指导您使用 Aspose.PDF for .NET 在 PDF 文件中添加文本边框的过程。提供的 C# 源代码演示了必要的步骤。

## 要求
开始之前，请确保您已准备好以下物品：

- 您的机器上安装的 Visual Studio 或任何其他 C# 编译器。
- Aspose.PDF for .NET 库。您可以从 Aspose 官方网站下载它，也可以使用 NuGet 等包管理器来安装它。

## 步骤 1：设置项目
1. 在您首选的开发环境中创建一个新的 C# 项目。
2. 添加对 Aspose.PDF for .NET 库的引用。

## 步骤 2：导入所需的命名空间
在要添加文本边框的代码文件中，在文件顶部添加以下使用指令：

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

## 步骤3：设置文档目录
在代码中，找到以下行`string dataDir = "YOUR DOCUMENT DIRECTORY";`并替换`"YOUR DOCUMENT DIRECTORY"`使用存储文档的目录路径。

## 步骤 4：创建一个新的 Document 对象
实例化一个新的`Document`对象，添加以下代码行：

```csharp
Document pdfDocument = new Document();
```

## 步骤 5：向文档添加页面
使用`Add`方法`Pages`集合。在提供的代码中，新页面被分配给变量`pdfPage`.

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

## 步骤 6：创建 TextFragment
创建一个`TextFragment`对象并提供所需的文本。使用`Position`属性。在提供的代码中，文本设置为“主文本”，并定位在页面上的 (100, 600)。

```csharp
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
```

## 步骤 7：设置文本属性
自定义文本属性，如字体大小、字体类型、背景颜色、前景色等。在提供的代码中，为文本片段设置了字体大小、字体、背景颜色、前景色和描边颜色等属性。

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
```

## 步骤 8：启用文本边框
要启用文本边框，请设置`DrawTextRectangleBorder`文本片段的属性`TextState`到`true`.

```csharp
textFragment.TextState.DrawTextRectangleBorder = true;
```

## 步骤 9：将 TextFragment 添加到页面
使用`TextBuilder`类来添加`TextFragment`对象到页面。

```csharp
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
```

## 步骤 10：保存 PDF 文档
使用`Save`方法`Document`对象。指定您在步骤 3 中设置的输出文件路径。

```csharp
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

### 使用 Aspose.PDF for .NET 添加文本边框的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//创建新的文档对象
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
您已成功使用 Aspose.PDF for .NET 向 PDF 文档添加文本边框。现在可以在指定的输出文件路径中找到生成的 PDF 文件。

### 常见问题解答

#### 问：本教程的重点是什么？

答：本教程将指导您使用 Aspose.PDF for .NET 库向 PDF 文件添加文本边框的过程。提供的 C# 源代码演示了实现此操作的必要步骤。

#### 问：本教程需要导入哪些命名空间？

答：在需要添加文本边框的代码文件中，在文件开头导入以下命名空间：

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

#### 问：如何指定文档目录？

答：在代码中，找到以下行`string dataDir = "YOUR DOCUMENT DIRECTORY";`并替换`"YOUR DOCUMENT DIRECTORY"`使用您的文档目录的实际路径。

#### 问：如何创建 Document 对象？

答：在第 4 步中，你将实例化一个新的`Document`对象使用以下代码行：

```csharp
Document pdfDocument = new Document();
```

#### 问：如何在文档中添加页面？

答：在第 5 步中，您将使用`Add`方法`Pages`收藏：

```csharp
Page pdfPage = (Page)pdfDocument.Pages.Add();
```

#### 问：如何创建 TextFragment 并设置其位置？

答：在第 6 步中，你将创建一个`TextFragment`对象并使用`Position`财产：

```csharp
TextFragment textFragment = new TextFragment("main text");
textFragment.Position = new Position(100, 600);
```

#### 问：如何自定义文本属性，包括文本边框？

答：在步骤 7 中，您将自定义各种文本属性，例如字体大小、字体类型、背景颜色、前景色和文本边框：

```csharp
textFragment.TextState.FontSize = 12;
textFragment.TextState.Font = FontRepository.FindFont("TimesNewRoman");
textFragment.TextState.BackgroundColor = Aspose.Pdf.Color.LightGray;
textFragment.TextState.ForegroundColor = Aspose.Pdf.Color.Red;
textFragment.TextState.StrokingColor = Aspose.Pdf.Color.DarkRed;
textFragment.TextState.DrawTextRectangleBorder = true;
```

#### 问：如何将 TextFragment 添加到 PDF 文档？

答：在第 9 步中，您将使用`TextBuilder`类来添加`TextFragment`反对该页面：

```csharp
TextBuilder tb = new TextBuilder(pdfPage);
tb.AppendText(textFragment);
```

#### 问：如何保存生成的 PDF 文档？

答：添加带边框的文本后，使用`Save`方法`Document`保存PDF文档的对象：

```csharp
pdfDocument.Save(dataDir + "PDFWithTextBorder_out.pdf");
```

#### 问：本教程的主要内容是什么？

答：通过本教程，您已成功学会如何使用 Aspose.PDF for .NET 添加文本边框来增强 PDF 文档的效果。这对于强调 PDF 文件中的特定文本内容特别有用。