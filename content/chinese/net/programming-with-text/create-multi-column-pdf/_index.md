---
title: 创建多列 PDF
linktitle: 创建多列 PDF
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 创建多列 PDF。
type: docs
weight: 110
url: /zh/net/programming-with-text/create-multi-column-pdf/
---
本教程将指导您完成使用 Aspose.PDF for .NET 创建多列 PDF 的过程。提供的 C# 源代码演示了必要的步骤。

## 要求
在开始之前，请确保您具备以下条件：

- Visual Studio 或计算机上安装的任何其他 C# 编译器。
- Aspose.PDF for .NET 库。您可以从 Aspose 官方网站下载它或使用 NuGet 等包管理器来安装它。

## 第 1 步：设置项目
1. 在您首选的开发环境中创建一个新的 C# 项目。
2. 添加对 Aspose.PDF for .NET 库的引用。

## 第2步：导入所需的命名空间
在要创建多列 PDF 的代码文件中，在文件顶部添加以下 using 指令：

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Drawing;
```

## 第三步：设置文档目录
在代码中，找到显示以下内容的行`string dataDir = "YOUR DOCUMENT DIRECTORY";`并替换`"YOUR DOCUMENT DIRECTORY"`以及存储文档的目录的路径。

## 步骤 4：创建一个新的 Document 实例
实例化一个新的`Document`对象，添加以下代码行：

```csharp
Document doc = new Document();
```

## 步骤 5：设置页边距
使用以下命令指定 PDF 文件的左右边距信息`PageInfo.Margin`的财产`Document`.

```csharp
doc.PageInfo.Margin.Left = 40;
doc.PageInfo.Margin.Right = 40;
```

## 步骤 6：向文档添加页面
使用以下命令向文档添加新页面`Add`的方法`Pages`收藏。在提供的代码中，新页面被分配给变量`page`.

```csharp
Page page = doc.Pages.Add();
```

## 第7步：创建一个Graph对象并添加一条线
创建一个新的`Graph`具有特定尺寸的对象并向其添加一条线。然后，添加`Graph`反对`Paragraphs`页面的集合。

```csharp
Aspose.Pdf.Drawing.Graph graph1 = new Aspose.Pdf.Drawing.Graph(500, 2);
float[] backPos = new float[] { 1, 2, 500, 2 };
Aspose.Pdf.Drawing.Line l1 = new Aspose.Pdf.Drawing.Line(posArr);
graph1.Shapes.Add(l1);
page.Paragraphs.Add(graph1);
```

## 步骤 8：添加 HTML 格式的标题文本
创建一个`HtmlFragment`对象并将其内容设置为所需的 HTML 文本。然后，将片段添加到`Paragraphs`页面的集合。

```csharp
string s = "<font face=\"Times New Roman\" size=4>" +
     "<strong>How to Steer Clear of money scams</<strong>" +
     "</font>";
HtmlFragment heading_text = new HtmlFragment(s);
page.Paragraphs.Add(heading_text);
```

## 第 9 步：创建一个具有多列的 FloatingBox
创建一个`FloatingBox`对象并设置列数和列间距。然后，将文本片段和一行添加到`Paragraphs`的集合`FloatingBox`.

```csharp
Aspose.Pdf.FloatingBox box = new Aspose.Pdf.FloatingBox();
box. ColumnInfo. ColumnCount = 2;
box.ColumnInfo.ColumnSpacing = "5";
box.ColumnInfo.ColumnWidths = "105 105";

TextFragment text1 = new TextFragment("By A Googling (The Official Google Blog)");
text1.TextState.FontSize = 8;
text1.TextState.LineSpacing = 2;
box.Paragraphs.Add(text1);

TextFragment text2 = new TextFragment("Sed augue tortor, sodales id, luctus et, pulvinar ut, eros. Suspendisse vel dolor. Sed quam. Curabitur ut massa vitae eros euismod aliquam...");
box.Paragraphs.Add(text2);

Aspose.Pdf.Drawing.Graph graph2 = new Aspose.Pdf.Drawing.Graph(50, 10);
float[] posArr2 = new float[] { 1, 10, 100, 10 };
Aspose.Pdf.Drawing.Line l2 = new Aspose.Pdf.Drawing.Line(posArr2);
graph2.Shapes.Add(l2);
box.Paragraphs.Add(graph2);

page.Paragraphs.Add(box);
```

## 第10步：保存PDF文档
使用以下命令保存 PDF 文档`Save`的方法`Document`目的。

```csharp
doc.Save(dataDir);
```

### 使用 Aspose.PDF for .NET 创建多列 Pdf 的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
//指定 PDF 文件的左边距信息
doc.PageInfo.Margin.Left = 40;
//指定 PDF 文件的右边距信息
doc.PageInfo.Margin.Right = 40;
Page page = doc.Pages.Add();
Aspose.Pdf.Drawing.Graph graph1 = new Aspose.Pdf.Drawing.Graph(500, 2);
//将行添加到节对象的释义集合中
page.Paragraphs.Add(graph1);
//指定线的坐标
float[] posArr = new float[] { 1, 2, 500, 2 };
Aspose.Pdf.Drawing.Line l1 = new Aspose.Pdf.Drawing.Line(posArr);
graph1.Shapes.Add(l1);
//使用包含 html 标签的文本创建字符串变量
string s = "<font face=\"Times New Roman\" size=4>" +
"<strong> How to Steer Clear of money scams</<strong> "
+ "</font>";
//创建包含 HTML 文本的文本段落
HtmlFragment heading_text = new HtmlFragment(s);
page.Paragraphs.Add(heading_text);
Aspose.Pdf.FloatingBox box = new Aspose.Pdf.FloatingBox();
//在该部分中添加四列
box.ColumnInfo.ColumnCount = 2;
//设置列之间的间距
box.ColumnInfo.ColumnSpacing = "5";
box.ColumnInfo.ColumnWidths = "105 105";
TextFragment text1 = new TextFragment("By A Googler (The Official Google Blog)");
text1.TextState.FontSize = 8;
text1.TextState.LineSpacing = 2;
box.Paragraphs.Add(text1);
text1.TextState.FontSize = 10;
text1.TextState.FontStyle = FontStyles.Italic;
//创建一个图形对象来绘制一条线
Aspose.Pdf.Drawing.Graph graph2 = new Aspose.Pdf.Drawing.Graph(50, 10);
//指定线的坐标
float[] posArr2 = new float[] { 1, 10, 100, 10 };
Aspose.Pdf.Drawing.Line l2 = new Aspose.Pdf.Drawing.Line(posArr2);
graph2.Shapes.Add(l2);
//将行添加到节对象的段落集合中
box.Paragraphs.Add(graph2);
TextFragment text2 = new TextFragment(@"Sed augue tortor, sodales id, luctus et, pulvinar ut, eros. Suspendisse vel dolor. Sed quam. Curabitur ut massa vitae eros euismod aliquam. Pellentesque sit amet elit. Vestibulum interdum pellentesque augue. Cras mollis arcu sit amet purus. Donec augue. Nam mollis tortor a elit. Nulla viverra nisl vel mauris. Vivamus sapien. nascetur ridiculus mus. Nam justo lorem, aliquam luctus, sodales et, semper sed, enim Nam justo lorem, aliquam luctus, sodales et,nAenean posuere ante ut neque. Morbi sollicitudin congue felis. Praesent turpis diam, iaculis sed, pharetra non, mollis ac, mauris. Phasellus nisi ipsum, pretium vitae, tempor sed, molestie eu, dui. Duis lacus purus, tristique ut, iaculis cursus, tincidunt vitae, risus. Sed commodo. *** sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Nam justo lorem, aliquam luctus, sodales et, semper sed, enim Nam justo lorem, aliquam luctus, sodales et, semper sed, enim Nam justo lorem, aliquam luctus, sodales et, semper sed, enim nAenean posuere ante ut neque. Morbi sollicitudin congue felis. Praesent turpis diam, iaculis sed, pharetra non, mollis ac, mauris. Phasellus nisi ipsum, pretium vitae, tempor sed, molestie eu, dui. Duis lacus purus, tristique ut, iaculis cursus, tincidunt vitae, risus. Sed commodo. *** sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Sed urna. . Duis convallis ultrices nisi. Maecenas non ligula. Nunc nibh est, tincidunt in, placerat sit amet, vestibulum a, nulla. Praesent porttitor turpis eleifend ante. Morbi sodales.nAenean posuere ante ut neque. Morbi sollicitudin congue felis. Praesent turpis diam, iaculis sed, pharetra non, mollis ac, mauris. Phasellus nisi ipsum, pretium vitae, tempor sed, molestie eu, dui. Duis lacus purus, tristique ut, iaculis cursus, tincidunt vitae, risus. Sed commodo. *** sociis natoque penatibus et magnis dis parturient montes, nascetur ridiculus mus. Sed urna. . Duis convallis ultrices nisi. Maecenas non ligula. Nunc nibh est, tincidunt in, placerat sit amet, vestibulum a, nulla. Praesent porttitor turpis eleifend ante. Morbi sodales.");
box.Paragraphs.Add(text2);
page.Paragraphs.Add(box);
dataDir = dataDir + "CreateMultiColumnPdf_out.pdf";
//保存 PDF 文件
doc.Save(dataDir);
Console.WriteLine("\nMulti column pdf file created successfully.\nFile saved at " + dataDir);
```

## 结论
您已使用 Aspose.PDF for .NET 成功创建了多列 PDF。现在可以在指定的输出文件路径中找到生成的 PDF 文件。

### 常见问题解答

#### 问：本教程的重点是什么？

本教程的重点是指导您完成使用 Aspose.PDF for .NET 库创建多列 PDF 的过程。提供的 C# 源代码演示了实现此目的的必要步骤。

#### 问：在本教程中我应该导入哪些命名空间？

答：在要创建多列 PDF 的代码文件中，在文件开头导入以下命名空间：

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Drawing;
```

#### 问：如何指定文档目录？

 A：在代码中找到这一行`string dataDir = "YOUR DOCUMENT DIRECTORY";`并替换`"YOUR DOCUMENT DIRECTORY"`与文档目录的实际路径。

#### 问：如何创建新的 Document 实例？

答：在第 4 步中，您将实例化一个新的`Document`使用提供的代码的对象。

#### 问：如何设置页边距？

答：在第 5 步中，您将使用`PageInfo.Margin`的财产`Document`指定 PDF 文件的左右边距信息。

#### 问：如何向文档添加页面？

答：在第 6 步中，您将使用`Add`的方法`Pages`收藏。

#### 问：如何创建 Graph 对象并添加线条？

答：在第 7 步中，您将创建一个新的`Graph`对象，向其添加一条线，然后添加`Graph`反对`Paragraphs`页面的集合。

#### 问：如何添加 HTML 格式的标题文本？

答：在第 8 步中，您将创建一个`HtmlFragment`对象并将其内容设置为所需的 HTML 文本，然后将片段添加到`Paragraphs`页面的集合。

#### 问：如何创建具有多列的 FloatingBox？

答：在第 9 步中，您将创建一个`FloatingBox`具有多个列和列间距的对象，然后向其中添加文本片段和一行`Paragraphs`的集合`FloatingBox`.

#### 问：如何保存PDF文档？

答：在步骤 10 中，您将使用以下命令保存 PDF 文档：`Save`的方法`Document`目的。

#### 问：本教程的主要内容是什么？

答：通过学习本教程，您已经了解了如何使用 Aspose.PDF for .NET 创建多列 PDF 文档。这对于以结构化且有组织的布局显示内容非常有用。