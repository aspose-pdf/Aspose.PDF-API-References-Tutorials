---
title: 边距或填充
linktitle: 边距或填充
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 在表格中设置边距或填充。
type: docs
weight: 140
url: /zh/net/programming-with-tables/margins-or-padding/
---
在本教程中，我们将指导您逐步使用 Aspose.PDF for .NET 在表格中设置边距或填充。我们将提供解释和代码片段来帮助您理解并在 C# 源代码中实现此功能。

## 第 1 步：设置文档和页面
首先，您需要使用以下代码设置文档和页面：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//通过调用其空构造函数来实例化 Document 对象
Document doc = new Document();
Page page = doc.Pages.Add();
```

## 第 2 步：创建表
接下来，我们将使用 Aspose.Pdf.Table 类创建一个表格对象：

```csharp
//实例化一个表对象
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
//将表格添加到所需部分的段落集合中
page.Paragraphs.Add(tab1);
```

## 步骤 3：设置列宽和默认单元格边框
要设置表格的列宽和默认单元格边框，请使用以下代码：

```csharp
//设置表格的列宽
tab1. ColumnWidths = "50 50 50";
//使用 BorderInfo 对象设置默认单元格边框
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

## 步骤 4：设置表格边框和单元格填充
要设置表格边框和单元格填充，请创建 MarginInfo 对象并设置其属性：

```csharp
//创建 MarginInfo 对象并设置其左、下、右、上边距
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 5f;
margin. Left = 5f;
margin. Right = 5f;
margin. Bottom = 5f;

//将默认单元格填充设置为 MarginInfo 对象
tab1. DefaultCellPadding = margin;

//使用另一个自定义的 BorderInfo 对象设置表格边框
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
```

## 第 5 步：添加行和单元格
现在，让我们向表中添加行和单元格。我们将创建一个新行并向其中添加单元格：

```csharp
//在表中创建行，然后在行中创建单元格
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add();
```

## 第 6 步：向单元格添加文本
要将文本添加到单元格，请创建一个 TextFragment 对象并将其添加到所需的单元格：

```csharp
TextFragment mytext = new TextFragment("col3 with large text string");
row1.Cells[2].Paragraphs.Add(mytext);
row1.Cells[2].IsWordWrapped = false;
```

## 第 7 步：保存 PDF
要保存 PDF 文档，请使用以下代码：

```csharp
dataDir = dataDir + "MarginsOrPadding_out.pdf";
//保存 PDF
doc.Save(dataDir);

Console.WriteLine("\nCell and table border width setup successfully.\nFile saved at " + dataDir);
```

### 使用 Aspose.PDF for .NET 的边距或填充的示例源代码

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//通过调用其空构造函数来实例化 Document 对象
Document doc = new Document();
Page page = doc.Pages.Add();
//实例化一个表对象
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
//将表格添加到所需部分的段落集合中
page.Paragraphs.Add(tab1);
//设置表格的列宽
tab1.ColumnWidths = "50 50 50";
//使用 BorderInfo 对象设置默认单元格边框
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
//使用另一个自定义的 BorderInfo 对象设置表格边框
tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
//创建 MarginInfo 对象并设置其左、下、右、上边距
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
//将默认单元格填充设置为 MarginInfo 对象
tab1.DefaultCellPadding = margin;
//在表中创建行，然后在行中创建单元格
Aspose.Pdf.Row row1 = tab1.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add();
TextFragment mytext = new TextFragment("col3 with large text string");
//Row1.Cells.Add("col3，要放置在单元格内的大文本字符串");
row1.Cells[2].Paragraphs.Add(mytext);
row1.Cells[2].IsWordWrapped = false;
// Row1.Cells[2].Paragraphs[0].FixedWidth= 80;
Aspose.Pdf.Row row2 = tab1.Rows.Add();
row2.Cells.Add("item1");
row2.Cells.Add("item2");
row2.Cells.Add("item3");
dataDir = dataDir + "MarginsOrPadding_out.pdf";
//保存 PDF
doc.Save(dataDir);

Console.WriteLine("\nCell and table border width setup successfully.\nFile saved at " + dataDir); 
```

## 结论
恭喜！您已成功学习如何使用 Aspose.PDF for .NET 在表格中设置边距或填充。这些知识将帮助您增强文档格式化能力并使您的表格具有视觉吸引力。

### 常见问题解答

#### 问：我可以为表格中的各个单元格设置不同的边距或填充吗？

答：是的，您可以使用 Aspose.PDF for .NET 为表格中的各个单元格设置不同的边距或填充。在提供的示例中，我们使用以下命令设置整个表格的默认单元格填充`DefaultCellPadding`财产。要为特定单元格设置不同的填充，您可以访问`MarginInfo`单独的每个单元格并修改它们的边距。

#### 问：如何更改表格的边框颜色或样式？

 A：要改变表格的边框颜色或样式，可以修改`Color`和`Width`的属性`BorderInfo`目的。在给定的示例中，我们将边框颜色设置为黑色，宽度设置为 1F（一点），使用`tab1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);`。您可以根据您的要求调整颜色和宽度。

#### 问：是否可以在表格中添加页眉或页脚？

答：是的，您可以使用 Aspose.PDF for .NET 将页眉或页脚添加到表格中。页眉和页脚通常是单独的行，其中包含附加信息，例如列标签、表标题或摘要数据。您可以创建其他行，设置不同的样式，并将它们添加到表格内容的上方或下方。

#### 问：如何调整表格单元格内的文本对齐方式？

答：要调整表格单元格内的文本对齐方式，您可以使用`HorizontalAlignment`和`VerticalAlignment`的属性`TextFragment`目的。例如，要使文本水平居中对齐，您可以设置`mytext.HorizontalAlignment = HorizontalAlignment.Center;`。同样，你可以设置`mytext.VerticalAlignment`来控制垂直对齐。

#### 问：我可以在表格单元格中添加图像而不是文本吗？

答：是的，您可以使用 Aspose.PDF for .NET 将图像添加到表格单元格。而不是创建一个`TextFragment`对象，您可以创建一个`Image`对象，加载图像文件，然后使用以下命令将其添加到所需的单元格`cell.Paragraphs.Add(image);`方法。这允许您将图像与文本内容一起插入到表格中。