---
title: 确定 PDF 文件中的表格中断
linktitle: 确定 PDF 文件中的表格中断
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 确定 PDF 文件中的换表符。
type: docs
weight: 60
url: /zh/net/programming-with-tables/determine-table-break/
---
在本教程中，我们将学习如何使用 Aspose.PDF for .NET 确定 PDF 文件中的换表符。我们将一步步解释C#的源代码。在本教程结束时，您将了解如何确定表格是否超出页边距。开始吧！

## 第一步：搭建环境
首先，确保您已使用 Aspose.PDF for .NET 设置 C# 开发环境。添加对库的引用并导入必要的命名空间。

## 第 2 步：创建 PDF 文档
在这一步中，我们创建一个新的`Document`代表 PDF 文档的对象。

```csharp
pdf-Document = new Document();
```

该文档将用于添加部分和表格。

## 步骤 3：添加部分和表格
现在我们将向 PDF 文档添加一个部分，并在该部分内创建一个表格。

```csharp
Page page = pdf.Pages.Add();
Table table1 = new Table();
table1. Margin. Top = 300;
page.Paragraphs.Add(table1);
```

我们还指定表格的上边距为 300 点。您可以根据需要调整该值。

## 第 4 步：表格设置
在此步骤中，我们配置表格属性，例如列宽和边框。

```csharp
table1. ColumnWidths = "100 100 100";
table1.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.1F);
table1.Border = new BorderInfo(BorderSide.All, 1F);
```

这里我们定义表格列和单元格边框的宽度。您可以根据自己的喜好调整这些值。

## 步骤 5：向表格添加行和单元格
现在我们将使用循环在表中创建行和单元格。

```csharp
for (int RowCounter = 0; RowCounter <= 16; RowCounter++)
{
     Row row1 = table1.Rows.Add();
     row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
}
```

此处，我们在表中创建 17 行，并向每行添加三个单元格。您可以根据需要调整带扣。

## 第 6 步：确定表中断
现在，我们将通过将页面高度与表格中对象的总高度进行比较来确定表格是否超出页边距。

```csharp
float PageHeight = (float)pdf.PageInfo.Height;
float TotalObjectsHeight = (float)page.PageInfo.Margin.Top + (float)page.PageInfo.Margin.Bottom + (float)table1.Margin.Top + (float)table1.GetHeight();

if ((PageHeight - TotalObjectsHeight) <= 10)
     Console.WriteLine("The height of the page - Height of objects < 10, the table will be truncated");
```

我们计算页面的高度和对象的总高度，同时考虑边距。如果差异为 10 或更少，则表格超出页边距。

## 步骤7：保存PDF文档
最后，我们将结果保存为 PDF 文档。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
dataDir = dataDir + "DetermineTableBreak_out.pdf";
pdf.Save(dataDir);
Console.WriteLine("\nTable break determined successfully.\nFile saved at " + dataDir);
```

请务必指定正确的文档目录。生成的 PDF 文件将与确定的表格分隔符一起保存。

### 使用 Aspose.PDF for .NET 确定表中断的示例源代码

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//实例化对象 PDF 类
Document pdf = new Document();
//将部分添加到 PDF 文档部分集合
Aspose.Pdf.Page page = pdf.Pages.Add();
//实例化一个表对象
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
table1.Margin.Top = 300;
//将表格添加到所需部分的段落集合中
page.Paragraphs.Add(table1);
//设置表格的列宽
table1.ColumnWidths = "100 100 100";
//使用 BorderInfo 对象设置默认单元格边框
table1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
//使用另一个自定义的 BorderInfo 对象设置表格边框
table1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
//创建 MarginInfo 对象并设置其左、下、右、上边距
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
//将默认单元格填充设置为 MarginInfo 对象
table1.DefaultCellPadding = margin;
//如果将计数器增加到 17，桌子就会损坏
//因为这个页面已经无法容纳更多内容了
for (int RowCounter = 0; RowCounter <= 16; RowCounter++)
{
	//在表中创建行，然后在行中创建单元格
	Aspose.Pdf.Row row1 = table1.Rows.Add();
	row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
}
//获取页面高度信息
float PageHeight = (float)pdf.PageInfo.Height;
//获取页面上下边距的总高度信息，
//表格顶部边距和表格高度。
float TotalObjectsHeight = (float)page.PageInfo.Margin.Top + (float)page.PageInfo.Margin.Bottom + (float)table1.Margin.Top + (float)table1.GetHeight();

//显示页面高度、表格高度、表格上边距和页面顶部
//和下边距信息
Console.WriteLine("PDF document Height = " + pdf.PageInfo.Height.ToString() + "\nTop Margin Info = " + page.PageInfo.Margin.Top.ToString() + "\nBottom Margin Info = " + page.PageInfo.Margin.Bottom.ToString() + "\n\nTable-Top Margin Info = " + table1.Margin.Top.ToString() + "\nAverage Row Height = " + table1.Rows[0].MinRowHeight.ToString() + " \nTable height " + table1.GetHeight().ToString() + "\n ----------------------------------------" + "\nTotal Page Height =" + PageHeight.ToString() + "\nCummulative height including Table =" + TotalObjectsHeight.ToString());

//检查是否扣除页面上边距 + 页面下边距之和
// 表格顶部边距和表格高度与页面高度及其减去值
//超过 10（平均行可以大于 10）
if ((PageHeight - TotalObjectsHeight) <= 10)
	//如果该值小于 10，则显示该消息。
	//这表明不能放置另一行，如果我们添加新的
	//行、表都会断。这取决于行高值。
	Console.WriteLine("Page Height - Objects Height < 10, so table will break");


dataDir = dataDir + "DetermineTableBreak_out.pdf";
//保存pdf文档
pdf.Save(dataDir);

Console.WriteLine("\nTable break determined successfully.\nFile saved at " + dataDir);
```

## 结论
在本教程中，我们学习了如何使用 Aspose.PDF for .NET 确定 PDF 文档中的换表符。您可以使用此分步指南来检查表格是否超出您自己的 C# 项目中的页边距。

### 确定 PDF 文件中表格中断的常见问题解答

#### 问：确定 PDF 文档中的换表符的目的是什么？

答：确定 PDF 文档中的表格分隔符的目的是检查表格是否超出页边距。这可确保表的内容在可用页面空间内正确显示。通过检测表格中断，您可以处理内容溢出并相应地调整表格布局。

#### 问：如何调整表格的上边距？

 A：在提供的C#源代码中，可以通过修改`table1.Margin.Top`财产。根据需要增加或减少该值以设置所需的表格上边距。

#### 问：我可以自定义表格的外观，例如单元格颜色和字体大小吗？

答：是的，您可以使用 Aspose.PDF for .NET 提供的各种属性和方法来自定义表格及其单元格的外观。例如，您可以更改单元格背景颜色、字体大小、字体系列、文本对齐方式等。有关如何自定义表格外观的更多信息，请参阅官方文档。

#### 问：如果表格超出页边距怎么办？

答：如果表格超出页边距，可能会导致内容截断或重叠，从而降低 PDF 文档的可读性和组织性。通过检测表格中断并处理溢出，您可以确保内容在可用页面区域内保持正确显示。

#### 问：我可以确定同一 PDF 文档中多个表格的表格分隔符吗？

答：是的，您可以确定同一 PDF 文档中多个表格的表格分隔符。只需对要分析的每个表格重复这些步骤，并根据需要调整表格布局以防止内容溢出。