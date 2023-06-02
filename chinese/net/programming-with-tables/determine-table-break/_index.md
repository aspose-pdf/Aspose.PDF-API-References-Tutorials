---
title: 确定表中断
linktitle: 确定表中断
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 确定 PDF 文档中的分表符。
type: docs
weight: 60
url: /zh/net/programming-with-tables/determine-table-break/
---

在本教程中，我们将学习如何使用 Aspose.PDF for .NET 确定 PDF 文档中的分表符。我们将逐步解释 C# 中的源代码。在本教程结束时，您将了解如何确定表格是否超出页边距。开始吧！

## 第 1 步：设置环境
首先，确保您已经使用 Aspose.PDF for .NET 设置了 C# 开发环境。添加对库的引用并导入必要的命名空间。

## 第 2 步：创建 PDF 文档
在这一步中，我们创建一个新的`Document`对象来表示 PDF 文档。

```csharp
pdf-Document = new Document();
```

该文档将用于添加部分和表格。

## 第 3 步：添加部分和表格
现在我们要在我们的 PDF 文档中添加一个部分，并在该部分中创建一个表格。

```csharp
Page page = pdf.Pages.Add();
Table table1 = new Table();
table1. Margin. Top = 300;
page.Paragraphs.Add(table1);
```

我们还为表格指定了 300 点的上边距。您可以根据需要调整此值。

## 第 4 步：表格设置
在此步骤中，我们配置表格属性，例如列宽和边框。

```csharp
table1. ColumnWidths = "100 100 100";
table1.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.1F);
table1.Border = new BorderInfo(BorderSide.All, 1F);
```

这里我们定义表格列的宽度和单元格边框。您可以根据自己的喜好调整这些值。

## 第 5 步：向表中添加行和单元格
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

在这里，我们在表中创建 17 行，并向每行添加三个单元格。您可以根据需要调整带扣。

## 第 6 步：确定表格分隔符
现在我们将通过比较页面高度与表格中对象的总高度来确定表格是否超出页边距。

```csharp
float PageHeight = (float)pdf.PageInfo.Height;
float TotalObjectsHeight = (float)page.PageInfo.Margin.Top + (float)page.PageInfo.Margin.Bottom + (float)table1.Margin.Top + (float)table1.GetHeight();

if ((PageHeight - TotalObjectsHeight) <= 10)
     Console.WriteLine("The height of the page - Height of objects < 10, the table will be truncated");
```

我们计算页面的高度和对象的总高度，同时考虑到边距。如果差异为 10 或更小，则表格超出了页边距。

## 步骤 7：保存 PDF 文档
最后，我们将结果保存为 PDF 文档。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
dataDir = dataDir + "DetermineTableBreak_out.pdf";
pdf.Save(dataDir);
Console.WriteLine("\nTable break determined successfully.\nFile saved at " + dataDir);
```

请务必指定正确的文档目录。生成的 PDF 文件将与确定的表格分隔符一起保存。

### Determine Table Break using Aspose.Words for .NET 的示例源代码

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//实例化对象 PDF 类
Document pdf = new Document();
//将节添加到 PDF 文档节集合
Aspose.Pdf.Page page = pdf.Pages.Add();
//实例化一个表对象
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
table1.Margin.Top = 300;
//在所需部分的段落集合中添加表格
page.Paragraphs.Add(table1);
//设置表格的列宽
table1.ColumnWidths = "100 100 100";
//使用 BorderInfo 对象设置默认单元格边框
table1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
//使用另一个自定义的 BorderInfo 对象设置表格边框
table1.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 1F);
//创建 MarginInfo 对象并设置其左、下、右和上边距
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
//将默认单元格填充设置为 MarginInfo 对象
table1.DefaultCellPadding = margin;
//如果将计数器增加到 17，表将损坏
//因为不能再在这个页面上容纳它
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
//获取Page Top & Bottom margin的总高度信息，
//桌面边距和桌面高度。
float TotalObjectsHeight = (float)page.PageInfo.Margin.Top + (float)page.PageInfo.Margin.Bottom + (float)table1.Margin.Top + (float)table1.GetHeight();

//显示页面高度、表格高度、表格顶部边距和页面顶部
//和底边距信息
Console.WriteLine("PDF document Height = " + pdf.PageInfo.Height.ToString() + "\nTop Margin Info = " + page.PageInfo.Margin.Top.ToString() + "\nBottom Margin Info = " + page.PageInfo.Margin.Bottom.ToString() + "\n\nTable-Top Margin Info = " + table1.Margin.Top.ToString() + "\nAverage Row Height = " + table1.Rows[0].MinRowHeight.ToString() + " \nTable height " + table1.GetHeight().ToString() + "\n ----------------------------------------" + "\nTotal Page Height =" + PageHeight.ToString() + "\nCummulative height including Table =" + TotalObjectsHeight.ToString());

//检查我们是否扣除页面上边距+页面底部边距的总和
// 表格顶部边距和表格高度来自页面高度及其更小
//大于 10（平均行可以大于 10）
if ((PageHeight - TotalObjectsHeight) <= 10)
	//如果值小于 10，则显示消息。
	//这表明不能放置另一行，如果我们添加新的
	//排，表会断。这取决于行高值。
	Console.WriteLine("Page Height - Objects Height < 10, so table will break");


dataDir = dataDir + "DetermineTableBreak_out.pdf";
//保存pdf文件
pdf.Save(dataDir);

Console.WriteLine("\nTable break determined successfully.\nFile saved at " + dataDir);
```

## 结论
在本教程中，我们学习了如何使用 Aspose.PDF for .NET 确定 PDF 文档中的分表符。您可以使用此分步指南来检查表格是否超出了您自己的 C# 项目中的页边距。