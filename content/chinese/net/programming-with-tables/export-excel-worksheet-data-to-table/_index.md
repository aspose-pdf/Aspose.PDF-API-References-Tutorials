---
title: 将 Excel 工作表数据导出到表
linktitle: 将 Excel 工作表数据导出到表
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 将数据从 Excel 表导出到 PDF 表。
type: docs
weight: 70
url: /zh/net/programming-with-tables/export-excel-worksheet-data-to-table/
---
在本教程中，我们将学习如何使用 Aspose.PDF for .NET 库从 Excel 工作表导出数据并在 PDF 文档中创建表格。我们将逐步介绍源代码并详细解释每个部分。在本教程结束时，您将能够生成包含 Excel 工作表数据的表格的 PDF 文件。让我们开始吧！

## 要求
在开始之前，请确保您已准备好以下内容：

- 具备 C# 编程语言的基础知识
- 您的计算机上安装了 Visual Studio
- Aspose.PDF for .NET 库已添加到您的项目中

## 步骤 1：设置环境
首先，在 Visual Studio 中创建一个新的 C# 项目。在解决方案资源管理器中右键单击您的项目，选择“管理 NuGet 包”，然后搜索“Aspose.PDF”，添加对 Aspose.PDF for .NET 库的引用。安装该包即可开始使用。

## 步骤 2：加载 Excel 工作表
在我们代码的第一步中，我们定义了包含 Excel 文档的目录的路径。将“YOUR DOCUMENT DIRECTORY”替换为您的 Excel 文件所在的实际目录路径。

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Cells.Workbook workbook = new Aspose.Cells.Workbook(new FileStream(dataDir + "newBook1.xlsx", FileMode.Open));
```

这里我们使用 Aspose.Cells 库来加载 Excel 工作簿。确保将“newBook1.xlsx”替换为您的 Excel 文件的名称。

## 步骤 3：访问工作表
接下来，我们需要访问 Excel 文件中的第一个工作表。我们使用`Worksheets`收集`Workbook`目的。

```csharp
//访问 Excel 文件中的第一个工作表
Aspose.Cells.Worksheet worksheet = workbook.Worksheets[0];
```

如果您的 Excel 文件包含多个工作表，则可以更改索引值`[0]`访问不同的工作表。

## 步骤 4：将数据导出到 DataTable
现在，我们将 Excel 工作表的内容导出到`DataTable`对象。我们使用`ExportDataTable`方法。

```csharp
//将从第一个单元格开始的 7 行 2 列的内容导出到 DataTable
DataTable dataTable = worksheet.Cells.ExportDataTable(0, 0, worksheet.Cells.MaxRow + 1, worksheet.Cells.MaxColumn + 1, true);
```

在此示例中，我们导出工作表中从第一个单元格 (0, 0) 到最后一个单元格的所有行和列。请根据您的需求设置适当的范围。

## 步骤 5：创建 PDF 文档
现在，我们将使用 Aspose.PDF 库创建一个新的 PDF 文档。

```csharp
//实例化 Document 实例
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
```

这将创建一个空的 PDF 文档，我们可以在其中添加内容。

## 步骤 6：添加页面和表格
为了以表格形式显示数据，我们需要在 PDF 文档中添加页面和表格。

```csharp
//在文档实例中创建页面
Aspose.Pdf.Page sec1 = pdf1.Pages.Add();

//创建表对象
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

//在该节的段落集合中添加 Table 对象
sec1.Paragraphs.Add(tab1);
```

这里，我们创建一个新页面和一个表格对象。然后我们将表格添加到页面的段落集合中。

## 步骤 7：设置表属性
在导入数据之前，我们需要设置表格的一些属性，例如列宽和默认单元格边框。

```csharp
//设置表格的列宽
tab1.ColumnWidths = "40 100 100";

//使用 BorderInfo 对象设置表格的默认单元格边框
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

在此示例中，我们将列宽设置为 40、100 和 100 个单位。根据您的数据调整值。我们还设置了默认单元格边框，以在每个单元格的所有边上显示边框。

## 步骤 8：将数据导入表
现在，我们将从`DataTable`使用`ImportDataTable`方法。

```csharp
//从上面创建的 DataTable 中将数据导入到 Table 对象中
tab1.ImportDataTable(dataTable, true, 0, 0, dataTable.Rows.Count + 1, dataTable.Columns.Count);
```

在这里，我们指定要导入的行和列的范围。在此示例中，我们导入`dataTable`目的。

## 步骤 9：格式化表格
为了增强表格的外观，我们可以将格式应用于特定单元格或行。在此步骤中，我们将格式化表格的第一行和交替行。

```csharp
//获取表格中第一行
Aspose.Pdf.Row row1 = tab1.Rows[0];

//格式化第一行
foreach(Aspose.Pdf.Cell curCell in row1.Cells)
{
     //设置第一行单元格的背景颜色
     curCell.BackgroundColor = Color.Blue;//设置第一行单元格的表面
     curCell.DefaultCellTextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("Helvetica-Oblique");
    
     //设置第一行单元格的字体颜色
     curCell.DefaultCellTextState.ForegroundColor = Color.Yellow;
    
     //设置第一行单元格的文本对齐方式
     curCell.DefaultCellTextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
}

//隔行格式
for (int All_Rows = 1; All_Rows <= dataTable.Rows.Count; All_Rows++)
{
     foreach(Aspose.Pdf.Cell curCell in tab1.Rows[All_Rows].Cells)
     {
         //设置隔行单元格的背景颜色
         curCell.BackgroundColor = Color.Gray;
        
         //设置隔行单元格的文本颜色
         curCell.DefaultCellTextState.ForegroundColor = Color.White;
     }
}
```

这里，我们遍历第一行的单元格并设置它们的背景颜色、字体、字体颜色和文本对齐方式。然后，我们遍历交替行中的所有单元格并设置它们的背景和文本颜色。

## 步骤 10：保存 PDF 文档
最后我们将PDF文档保存到指定位置。

```csharp
//保存 PDF
pdf1.Save(dataDir + @"Exceldata_toPdf_table.pdf");
```

确保将“您的文档目录”替换为输出 PDF 文件所需的目录路径和文件名。

### 使用 Aspose.PDF for .NET 将 Excel 工作表数据导出到表格的示例源代码

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Cells.Workbook workbook = new Aspose.Cells.Workbook(new FileStream(dataDir + "newBook1.xlsx", FileMode.Open));
//访问 Excel 文件中的第一个工作表
Aspose.Cells.Worksheet worksheet = workbook.Worksheets[0];
//将从第一个单元格开始的 7 行 2 列的内容导出到 DataTable
DataTable dataTable = worksheet.Cells.ExportDataTable(0, 0, worksheet.Cells.MaxRow + 1, worksheet.Cells.MaxColumn + 1, true);

//实例化 Document 实例
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
//在文档实例中创建页面
Aspose.Pdf.Page sec1 = pdf1.Pages.Add();

//创建表对象
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

//在该节的段落集合中添加 Table 对象
sec1.Paragraphs.Add(tab1);

//设置表格的列宽。我们需要手动指定 ColumnCount。
//由于当前 Excel 工作表有三列，因此我们指定相同的计数
tab1.ColumnWidths = "40 100 100";

//使用 BorderInfo 对象设置表格的默认单元格边框
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

//从上面创建的 DataTable 中将数据导入到 Table 对象中
tab1.ImportDataTable(dataTable, true, 0, 0, dataTable.Rows.Count + 1, dataTable.Columns.Count);
//获取表格中第一行
Aspose.Pdf.Row row1 = tab1.Rows[0];

//遍历第一行的所有单元格并将其背景颜色设置为蓝色
foreach (Aspose.Pdf.Cell curCell in row1.Cells)
{
	//设置表格第一行所有单元格的背景。
	curCell.BackgroundColor = Color.Blue;
	//设置表格第一行单元格的字体。
	curCell.DefaultCellTextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("Helvetica-Oblique");
	//设置表格第一行所有单元格的字体颜色。
	curCell.DefaultCellTextState.ForegroundColor = Color.Yellow;
	//将第一行单元格的文本对齐方式设置为居中。
	curCell.DefaultCellTextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
}

for (int All_Rows = 1; All_Rows <= dataTable.Rows.Count; All_Rows++)
{
	//遍历第一行的所有单元格并将其背景颜色设置为蓝色
	foreach (Aspose.Pdf.Cell curCell in tab1.Rows[All_Rows].Cells)
	{
		//设置除第一行之外的所有单元格的背景颜色。
		curCell.BackgroundColor = Color.Gray;
		//设置除第一行之外的所有单元格的文本颜色。
		curCell.DefaultCellTextState.ForegroundColor = Color.White;
	}
}

//保存 PDF
pdf1.Save(dataDir + @"Exceldata_toPdf_table.pdf");
```

## 结论
在本教程中，我们学习了如何使用 Aspose.PDF for .NET 库将数据从 Excel 工作表导出到 PDF 表。我们介绍了加载 Excel 工作表、创建 PDF 文档、添加表格、导入数据和格式化表格的分步过程。现在，您可以通过编程方式生成包含 Excel 数据的表格的 PDF 文件。

### 常见问题解答

#### 问：将 Excel 工作表数据导出到 PDF 表的目的是什么？

答：将 Excel 工作表数据导出到 PDF 表格可让您以结构化和有组织的格式呈现数据。它使您能够生成包含 Excel 工作表数据的表格的 PDF 文件，从而更轻松地以可移植文档格式共享和保存信息。

#### 问：我可以自定义 PDF 表格的外观吗？

答：是的，您可以使用 Aspose.PDF for .NET 提供的各种属性自定义 PDF 表的外观。在提供的 C# 源代码中，您可以修改列宽、单元格边框、文本对齐方式、字体样式等以满足您的特定要求。

#### 问：如何处理包含多个工作表的 Excel 文件？

答：在提供的 C# 代码中，我们使用索引访问了 Excel 文件中的第一个工作表`[0]`。如果您的 Excel 文件包含多个工作表，您可以通过相应地更改索引值来访问它们，例如`[1]`对于第二张工作表或`[2]`对于第三张工作表。

#### 问：我可以将不同的格式应用于 PDF 表中的特定行或单元格吗？

答：是的，您可以将不同的格式应用于 PDF 表中的特定行或单元格。在提供的 C# 源代码中，我们演示了如何通过更改背景颜色、字体样式和字体颜色来对第一行和交替行进行不同的格式化。您可以根据需要将类似的格式化技术应用于任何特定的行或单元格。

#### 问：Aspose.PDF for .NET 是唯一允许将 Excel 数据导出到 PDF 表的库吗？

答：Aspose.PDF for .NET 是一个功能强大的库，可用于在 .NET 应用程序中处理 PDF 文档。虽然可能还有其他库可用，但 Aspose.PDF for .NET 提供了广泛的功能和能力，可用于生成、操作和导出包含 Excel 数据表的 PDF 文件，使其成为此类任务的热门选择。