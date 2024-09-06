---
title: 确定 PDF 文件中的表格中断
linktitle: 确定 PDF 文件中的表格中断
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 确定 PDF 文件中的表格分隔符。
type: docs
weight: 60
url: /zh/net/programming-with-tables/determine-table-break/
---
在本教程中，我们将学习如何使用 Aspose.PDF for .NET 确定 PDF 文件中的表格分隔符。我们将逐步解释 C# 中的源代码。在本教程结束时，您将了解如何确定表格是否超出页边距。让我们开始吧！

## 步骤 1：设置环境
首先，确保您已使用 Aspose.PDF for .NET 设置了 C# 开发环境。添加对库的引用并导入必要的命名空间。

## 步骤 2：创建 PDF 文档
在此步骤中，我们创建一个新的`Document`对象来表示 PDF 文档。

```csharp
pdf-Document = new Document();
```

该文档将用于添加章节和表格。

## 步骤 3：添加部分和表格
现在我们要向我们的 PDF 文档添加一个部分，并在该部分内创建一个表格。

```csharp
Page page = pdf.Pages.Add();
Table table1 = new Table();
table1. Margin. Top = 300;
page.Paragraphs.Add(table1);
```

我们还为表格指定了 300 点的上边距。您可以根据需要调整此值。

## 步骤 4：表设置
在此步骤中，我们配置表格属性，例如列宽和边框。

```csharp
table1. ColumnWidths = "100 100 100";
table1.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.1F);
table1.Border = new BorderInfo(BorderSide.All, 1F);
```

这里我们定义表格列的宽度和单元格边框。您可以根据自己的喜好调整这些值。

## 步骤 5：向表中添加行和单元格
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

这里我们在表格中创建17行，每行添加三个单元格。您可以根据需要调整扣环。

## 步骤 6：确定表格分隔符
现在我们将通过比较页面的高度和表格中对象的总高度来确定表格是否超出页边距。

```csharp
float PageHeight = (float)pdf.PageInfo.Height;
float TotalObjectsHeight = (float)page.PageInfo.Margin.Top + (float)page.PageInfo.Margin.Bottom + (float)table1.Margin.Top + (float)table1.GetHeight();

if ((PageHeight - TotalObjectsHeight) <= 10)
     Console.WriteLine("The height of the page - Height of objects < 10, the table will be truncated");
```

我们计算页面高度和考虑页边距的对象总高度。如果差值小于或等于 10，则表格超出页边距。

## 步骤 7：保存 PDF 文档
最后，我们将结果保存为 PDF 文档。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
dataDir = dataDir + "DetermineTableBreak_out.pdf";
pdf.Save(dataDir);
Console.WriteLine("\nTable break determined successfully.\nFile saved at " + dataDir);
```

确保指定正确的文档目录。生成的 PDF 文件将使用确定的表格分隔符保存。

### 使用 Aspose.PDF for .NET 确定表格中断的示例源代码

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//实例化对象 PDF 类
Document pdf = new Document();
//将部分添加到 PDF 文档部分集合
Aspose.Pdf.Page page = pdf.Pages.Add();
//实例化表对象
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
//创建 MarginInfo 对象并设置其左边距、下边距、右边距和上边距
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 5f;
margin.Left = 5f;
margin.Right = 5f;
margin.Bottom = 5f;
//将默认单元格填充设置为 MarginInfo 对象
table1.DefaultCellPadding = margin;
//如果你将计数器增加到 17，桌子就会坏掉
//因为此页面无法再容纳更多内容
for (int RowCounter = 0; RowCounter <= 16; RowCounter++)
{
	//在表格中创建行，然后在行中创建单元格
	Aspose.Pdf.Row row1 = table1.Rows.Add();
	row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
}
//获取页面高度信息
float PageHeight = (float)pdf.PageInfo.Height;
//获取页面顶部和底部边距的总高度信息，
//桌面边距和桌面高度。
float TotalObjectsHeight = (float)page.PageInfo.Margin.Top + (float)page.PageInfo.Margin.Bottom + (float)table1.Margin.Top + (float)table1.GetHeight();

//显示页面高度、表格高度、表格顶部边距和页面顶部
//以及底部边距信息
Console.WriteLine("PDF document Height = " + pdf.PageInfo.Height.ToString() + "\nTop Margin Info = " + page.PageInfo.Margin.Top.ToString() + "\nBottom Margin Info = " + page.PageInfo.Margin.Bottom.ToString() + "\n\nTable-Top Margin Info = " + table1.Margin.Top.ToString() + "\nAverage Row Height = " + table1.Rows[0].MinRowHeight.ToString() + " \nTable height " + table1.GetHeight().ToString() + "\n ----------------------------------------" + "\nTotal Page Height =" + PageHeight.ToString() + "\nCummulative height including Table =" + TotalObjectsHeight.ToString());

//检查我们是否扣除页面顶部边距 + 页面底部边距的总和
// 表格顶部边距和表格高度小于页面高度
//大于10（平均一行可以大于10）
if ((PageHeight - TotalObjectsHeight) <= 10)
	//如果值小于 10，则显示消息。
	//这表明另一行不能放置，如果我们添加新的
	//行、表会断裂。这取决于行高值。
	Console.WriteLine("Page Height - Objects Height < 10, so table will break");


dataDir = dataDir + "DetermineTableBreak_out.pdf";
//保存 pdf 文档
pdf.Save(dataDir);

Console.WriteLine("\nTable break determined successfully.\nFile saved at " + dataDir);
```

## 结论
在本教程中，我们学习了如何使用 Aspose.PDF for .NET 确定 PDF 文档中的表格分隔符。您可以使用本分步指南检查表格是否超出了您自己的 C# 项目中的页边距。

### 确定 PDF 文件中表格分隔符的常见问题解答

#### 问：确定 PDF 文档中的表格分隔符的目的是什么？

答：确定 PDF 文档中的表格分隔符的目的是检查表格是否超出页边距。这可确保表格内容在可用的页面空间内正确显示。通过检测表格分隔符，您可以处理内容溢出并相应地调整表格布局。

#### 问：如何调整表格的上边距？

答：在提供的 C# 源代码中，您可以通过修改`table1.Margin.Top`属性。根据需要增加或减少该值以设置表格所需的上边距。

#### 问：我可以自定义表格的外观，例如单元格颜色和字体大小吗？

答：是的，您可以使用 Aspose.PDF for .NET 提供的各种属性和方法自定义表格及其单元格的外观。例如，您可以更改单元格背景颜色、字体大小、字体系列、文本对齐方式等。有关如何自定义表格外观的更多信息，请参阅官方文档。

#### 问：如果表格超出页边距会发生什么情况？

答：如果表格超出页边距，可能会导致内容截断或重叠，使 PDF 文档的可读性和条理性下降。通过检测表格中断并处理溢出，您可以确保内容在可用的页面区域内正确显示。

#### 问：我可以确定同一 PDF 文档中多个表格的分页符吗？

答：是的，您可以确定同一 PDF 文档中多个表格的分页符。只需对要分析的每个表格重复上述步骤，并根据需要调整表格布局，以防止内容溢出。