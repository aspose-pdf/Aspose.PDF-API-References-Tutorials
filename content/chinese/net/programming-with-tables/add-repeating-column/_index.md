---
title: 在 PDF 文档中添加重复列
linktitle: 在 PDF 文档中添加重复列
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 文档中添加重复列。
type: docs
weight: 20
url: /zh/net/programming-with-tables/add-repeating-column/
---
在本教程中，我们将学习如何使用 Aspose.PDF for .NET 在 PDF 文档中添加重复列。我们将一步步解释C#的源代码。在本教程结束时，您将了解如何在 PDF 文档中创建带有重复列的表格。开始吧！

## 第一步：搭建环境
首先，确保您已使用 Aspose.PDF for .NET 设置 C# 开发环境。添加对库的引用并导入必要的命名空间。

## 第 2 步：创建 PDF 文档
在此步骤中，我们创建一个新的 PDF 文档。

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

我们创建了一个空的 PDF 文档，可以在其中添加内容。

## 第 3 步：创建表
在此步骤中，我们创建一个主表（`outerTable`）和嵌套表（`mytable`）这将在该列中重复。

```csharp
Table outerTable = new Table();
outerTable.ColumnWidths = "100%";
outerTable.HorizontalAlignment = HorizontalAlignment.Left;

Table mytable = new Table();
mytable.Broken = TableBroken.VerticalInSamePage;
mytable.ColumnAdjustment = ColumnAdjustment.AutoFitToContent;
```

我们指定了表属性，例如列宽和嵌套表分隔模式。

## 步骤 4：将表格添加到文档中
现在我们将创建的表格添加到 PDF 文档中。

```csharp
page.Paragraphs.Add(outerTable);
var bodyRow = outerTable.Rows.Add();
var bodyCell = bodyRow.Cells.Add();
bodyCell.Paragraphs.Add(mytable);
mytable.RepeatingColumnsCount = 5;
page.Paragraphs.Add(mytable);
```

我们首先添加主表（`outerTable`) 到 PDF 文档。接下来，我们添加嵌套表（`mytable` ) 作为主表单元格中的一个段落。我们还指定重复列的数量`mytable`（在本例中为 5 列）。

## 第 5 步：添加标题和行
现在我们将标题和行添加到表中。

```csharp
Row headerRow = mytable.Rows.Add();
headerRow.Cells.Add("header 1");
headerRow.Cells.Add("header 2");
headerRow.Cells.Add("header 3");
// ...
//在这里添加其他标题

for (int RowCounter = 0; RowCounter <= 5; RowCounter++)
{
     Row row1 = mytable.Rows.Add();
     row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
     row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
     // ...
     //在此处添加其他列
}
```

我们首先将标题添加到表格的第一行（`headerRow`）。然后我们添加循环中的数据行。在此示例中，我们添加 6 行数据。

## 第6步：保存PDF文档
最后，我们将PDF文档保存到指定的文件中。

```csharp
string outFile = dataDir + "AddRepeatingColumn_out.pdf";
doc.Save(outFile);
```

确保指定正确的目录和文件名来保存输出 PDF 文件。

### 使用 Aspose.PDF for .NET 添加重复列的示例源代码

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

string outFile = dataDir + "AddRepeatingColumn_out.pdf";
//创建一个新文档
Document doc = new Document();
Aspose.Pdf.Page page = doc.Pages.Add();

//实例化一个占据整个页面的外表
Aspose.Pdf.Table outerTable = new Aspose.Pdf.Table();
outerTable.ColumnWidths = "100%";
outerTable.HorizontalAlignment = HorizontalAlignment.Left;

//实例化一个表格对象，该对象将嵌套在outerTable中，该对象将在同一页面内中断
Aspose.Pdf.Table mytable = new Aspose.Pdf.Table();
mytable.Broken = TableBroken.VerticalInSamePage;
mytable.ColumnAdjustment = ColumnAdjustment.AutoFitToContent;

//将outerTable添加到页面段落中
//将 mytable 添加到outerTable
page.Paragraphs.Add(outerTable);
var bodyRow = outerTable.Rows.Add();
var bodyCell = bodyRow.Cells.Add();
bodyCell.Paragraphs.Add(mytable);
mytable.RepeatingColumnsCount = 5;
page.Paragraphs.Add(mytable);

//添加标题行
Aspose.Pdf.Row row = mytable.Rows.Add();
row.Cells.Add("header 1");
row.Cells.Add("header 2");
row.Cells.Add("header 3");
row.Cells.Add("header 4");
row.Cells.Add("header 5");
row.Cells.Add("header 6");
row.Cells.Add("header 7");
row.Cells.Add("header 11");
row.Cells.Add("header 12");
row.Cells.Add("header 13");
row.Cells.Add("header 14");
row.Cells.Add("header 15");
row.Cells.Add("header 16");
row.Cells.Add("header 17");

for (int RowCounter = 0; RowCounter <= 5; RowCounter++)

{
	//在表中创建行，然后在行中创建单元格
	Aspose.Pdf.Row row1 = mytable.Rows.Add();
	row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 4");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 5");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 6");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 7");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 11");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 12");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 13");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 14");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 15");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 16");
	row1.Cells.Add("col " + RowCounter.ToString() + ", 17");
}
doc.Save(outFile);
```

## 结论
在本教程中，我们学习了如何使用 Aspose.PDF for .NET 在 PDF 文档中添加重复列。您可以使用此分步指南在您自己的 C# 项目中创建具有重复列的表。

### 在 PDF 文档中添加重复列的常见问题解答

#### 问：我可以自定义嵌套表中重复列的数量吗？

答：是的，您可以自定义嵌套表中重复列的数量。在提供的示例中，我们设置`mytable.RepeatingColumnsCount = 5;`，这意味着将有 5 个重复列。您可以将此值更改为任何所需的数字。

#### 问：是否可以动态向嵌套表添加更多行？

答：是的，您可以按照教程中所示的相同方式向嵌套表动态添加更多行。您可以使用循环或任何其他逻辑根据您的数据添加行。

#### 问：我可以将样式和格式应用于表格及其单元格吗？

答：是的，您可以使用 Aspose.PDF for .NET 将样式和格式应用于表格及其单元格。该库提供了各种属性和方法来自定义表及其内容的外观。

#### 问：Aspose.PDF for .NET 与 .NET Core 兼容吗？

答：是的，Aspose.PDF for .NET 与 .NET Core 兼容。您可以在 .NET Framework 和 .NET Core 应用程序中使用它。

#### 问：我可以使用此方法在现有 PDF 文档中添加重复列吗？

答：是的，您可以使用此方法在现有 PDF 文档中添加重复列。只需使用 Aspose.PDF for .NET 加载现有文档，然后按照相同的步骤创建和添加重复列。