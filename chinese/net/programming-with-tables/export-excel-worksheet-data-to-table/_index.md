---
title: 将 Excel 工作表数据导出到表格
linktitle: 将 Excel 工作表数据导出到表格
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 将数据从 Excel 工作表导出到 PDF 表格。
type: docs
weight: 70
url: /zh/net/programming-with-tables/export-excel-worksheet-data-to-table/
---

在本教程中，我们将学习如何使用 Aspose.PDF for .NET 库从 Excel 工作表导出数据并在 PDF 文档中创建表格。我们将逐步浏览源代码并详细解释每个部分。在本教程结束时，您将能够生成包含 Excel 工作表数据的表格的 PDF 文件。让我们开始吧！

## 要求
在我们开始之前，请确保您拥有以下内容：

- C#编程语言的基础知识
- 计算机上安装的 Visual Studio
- Aspose.PDF for .NET 库已添加到您的项目中

## 第 1 步：设置环境
首先，在 Visual Studio 中创建一个新的 C# 项目。通过在解决方案资源管理器中右键单击您的项目，选择“管理 NuGet 包”并搜索“Aspose.PDF”，添加对 Aspose.PDF for .NET 库的引用。安装软件包，您就可以开始了。

## 第 2 步：加载 Excel 工作表
在代码的第一步中，我们定义了包含 Excel 文档的目录的路径。将“您的文档目录”替换为您的 Excel 文件所在的实际目录路径。

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Cells.Workbook workbook = new Aspose.Cells.Workbook(new FileStream(dataDir + "newBook1.xlsx", FileMode.Open));
```

在这里，我们使用 Aspose.Cells 库加载 Excel 工作簿。确保将“newBook1.xlsx”替换为您的 Excel 文件的名称。

## 第 3 步：访问工作表
接下来，我们需要访问 Excel 文件中的第一个工作表。我们使用`Worksheets`的集合`Workbook`目的。

```csharp
//访问 Excel 文件中的第一个工作表
Aspose.Cells.Worksheet worksheet = workbook.Worksheets[0];
```

如果您的 Excel 文件包含多个工作表，您可以更改索引值`[0]`访问不同的工作表。

## 第四步：导出数据到DataTable
现在，我们将 Excel 工作表的内容导出到`DataTable`目的。我们使用指定要导出的单元格范围`ExportDataTable`方法。

```csharp
//导出从第一个单元格开始的7行2列的内容到DataTable
DataTable dataTable = worksheet.Cells.ExportDataTable(0, 0, worksheet.Cells.MaxRow + 1, worksheet.Cells.MaxColumn + 1, true);
```

在此示例中，我们导出工作表中从第一个单元格 (0, 0) 到最后一个单元格的所有行和列。根据您的要求设置合适的范围。

## 步骤 5：创建 PDF 文档
现在，我们将使用 Aspose.PDF 库创建一个新的 PDF 文档。

```csharp
//实例化一个 Document 实例
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
```

这将创建一个空的 PDF 文档，我们可以在其中添加内容。

## 第 6 步：添加页面和表格
要以表格格式显示数据，我们需要在 PDF 文档中添加一个页面和一个表格。

```csharp
//在文档实例中创建一个页面
Aspose.Pdf.Page sec1 = pdf1.Pages.Add();

//创建表对象
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

//在该部分的段落集合中添加 Table 对象
sec1.Paragraphs.Add(tab1);
```

在这里，我们创建一个新页面和一个表对象。然后我们将表格添加到页面的段落集合中。

## 步骤 7：设置表格属性
在导入数据之前，我们需要设置表格的一些属性，例如列宽和默认单元格边框。

```csharp
//设置表格的列宽
tab1.ColumnWidths = "40 100 100";

//使用 BorderInfo 对象设置表格的默认单元格边框
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);
```

在此示例中，我们将列宽设置为 40、100 和 100 个单位。根据您的数据调整值。我们还设置了默认的单元格边框，以在每个单元格的所有边上显示边框。

## 步骤 8：将数据导入表
现在，我们将从`DataTable`对象到表中使用`ImportDataTable`方法。

```csharp
//从上面创建的 DataTable 中将数据导入到 Table 对象中
tab1.ImportDataTable(dataTable, true, 0, 0, dataTable.Rows.Count + 1, dataTable.Columns.Count);
```

在这里，我们指定要导入的行和列的范围。在此示例中，我们从`dataTable`目的。

## 第 9 步：格式化表格
为了增强表格的外观，我们可以将格式应用于特定的单元格或行。在此步骤中，我们将格式化表格的第一行和备用行。

```csharp
//从表中获取第一行
Aspose.Pdf.Row row1 = tab1.Rows[0];

//格式化第一行
foreach(Aspose.Pdf.Cell curCell in row1.Cells)
{
     //设置第一行单元格的背景色
     curCell.BackgroundColor = Color.Blue;//设置第一行单元格的面
     curCell.DefaultCellTextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("Helvetica-Oblique");
    
     //设置第一行单元格的字体颜色
     curCell.DefaultCellTextState.ForegroundColor = Color.Yellow;
    
     //设置第一行单元格的文本对齐方式
     curCell.DefaultCellTextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
}

//交替行格式
for (int All_Rows = 1; All_Rows <= dataTable.Rows.Count; All_Rows++)
{
     foreach(Aspose.Pdf.Cell curCell in tab1.Rows[All_Rows].Cells)
     {
         //设置交替行中单元格的背景颜色
         curCell.BackgroundColor = Color.Gray;
        
         //设置交替行中单元格的文本颜色
         curCell.DefaultCellTextState.ForegroundColor = Color.White;
     }
}
```

在这里，我们遍历第一行的单元格并设置它们的背景颜色、字体、字体颜色和文本对齐方式。然后，我们遍历交替行中的所有单元格并设置它们的背景和文本颜色。

## 步骤 10：保存 PDF 文档
最后我们将PDF文档保存到指定位置。

```csharp
//保存 PDF
pdf1.Save(dataDir + @"Exceldata_toPdf_table.pdf");
```

确保将“您的文档目录”替换为输出 PDF 文件所需的目录路径和文件名。

### 使用 Aspose.Words for .NET 将 Excel 工作表数据导出到表的示例源代码

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

Aspose.Cells.Workbook workbook = new Aspose.Cells.Workbook(new FileStream(dataDir + "newBook1.xlsx", FileMode.Open));
//访问 Excel 文件中的第一个工作表
Aspose.Cells.Worksheet worksheet = workbook.Worksheets[0];
//导出从第一个单元格开始的7行2列的内容到DataTable
DataTable dataTable = worksheet.Cells.ExportDataTable(0, 0, worksheet.Cells.MaxRow + 1, worksheet.Cells.MaxColumn + 1, true);

//实例化一个文档实例
Aspose.Pdf.Document pdf1 = new Aspose.Pdf.Document();
//在文档实例中创建一个页面
Aspose.Pdf.Page sec1 = pdf1.Pages.Add();

//创建表对象
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

//在该部分的段落集合中添加 Table 对象
sec1.Paragraphs.Add(tab1);

//设置表格的列宽。我们需要手动指定 ColumnCount。
//由于当前 excel 工作表具有三列，因此我们指定相同的计数
tab1.ColumnWidths = "40 100 100";

//使用 BorderInfo 对象设置表格的默认单元格边框
tab1.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.1F);

//从上面创建的 DataTable 中将数据导入到 Table 对象中
tab1.ImportDataTable(dataTable, true, 0, 0, dataTable.Rows.Count + 1, dataTable.Columns.Count);
//从表中获取第一行
Aspose.Pdf.Row row1 = tab1.Rows[0];

//遍历第一行中的所有单元格并将其背景颜色设置为蓝色
foreach (Aspose.Pdf.Cell curCell in row1.Cells)
{
	//设置表格第一行所有单元格的背景。
	curCell.BackgroundColor = Color.Blue;
	//为表格中第一行的单元格设置字体。
	curCell.DefaultCellTextState.Font = Aspose.Pdf.Text.FontRepository.FindFont("Helvetica-Oblique");
	//设置表格第一行所有单元格的字体颜色。
	curCell.DefaultCellTextState.ForegroundColor = Color.Yellow;
	//将第一行单元格的文本对齐设置为居中。
	curCell.DefaultCellTextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
}

for (int All_Rows = 1; All_Rows <= dataTable.Rows.Count; All_Rows++)
{
	//遍历第一行中的所有单元格并将其背景颜色设置为蓝色
	foreach (Aspose.Pdf.Cell curCell in tab1.Rows[All_Rows].Cells)
	{
		//设置除第一行以外的所有单元格的背景颜色。
		curCell.BackgroundColor = Color.Gray;
		//设置除第一行以外的所有单元格的文本颜色。
		curCell.DefaultCellTextState.ForegroundColor = Color.White;
	}
}

//保存 PDF
pdf1.Save(dataDir + @"Exceldata_toPdf_table.pdf");
```

## 结论
在本教程中，我们学习了如何使用 Aspose.PDF for .NET 库将数据从 Excel 工作表导出到 PDF 表格。我们介绍了加载 Excel 工作表、创建 PDF 文档、添加表格、导入数据和设置表格格式的分步过程。您现在可以通过编程方式生成包含 Excel 数据的表格的 PDF 文件。