---
title: 在 PDF 文档中渲染表格
linktitle: 在 PDF 文档中渲染表格
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 文档中显示表格。
type: docs
weight: 170
url: /zh/net/programming-with-tables/render-table/
---
在本教程中，我们将逐步指导您使用 Aspose.PDF for .NET 在 PDF 文档中显示表格。我们将解释提供的 C# 源代码并向您展示如何实现它。

## 第 1 步：创建文档
首先，我们将创建一个新的 PDF 文档：

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//创建一个新文档
Document doc = new Document();
```

## 步骤 2：配置页边距和方向
接下来，我们将配置页边距并将方向设置为横向模式：

```csharp
PageInfo pageInfo = doc.PageInfo;
Aspose.Pdf.MarginInfo marginInfo = pageInfo.Margin;

marginInfo. Left = 37;
marginInfo. Right = 37;
marginInfo. Top = 37;
marginInfo.Bottom = 37;

pageInfo.IsLandscape = true;
```

## 步骤 3：创建表和列
现在让我们创建一个表并设置列宽：

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table. ColumnWidths = "50 100";
```

## 步骤 4：向表格添加行和单元格
接下来，我们将使用循环将行和单元格添加到表中：

```csharp
for (int i = 1; i <= 120; i++)
{
     Aspose.Pdf.Row row = table.Rows.Add();
     row. FixedRowHeight = 15;
     Aspose.Pdf.Cell cell1 = row.Cells.Add();
     cell1.Paragraphs.Add(new TextFragment("Content 1"));
     Aspose.Pdf.Cell cell2 = row.Cells.Add();
     cell2.Paragraphs.Add(new TextFragment("HHHHH"));
}
```

## 第5步：将表格添加到页面
现在让我们将表格添加到文档页面：

```csharp
Page curPage = doc.Pages.Add();
Aspose.Pdf.Paragraphs paragraphs = curPage.Paragraphs;
paragraphs. Add(table);
```

## 步骤 6：在新页面上显示表格
接下来，我们将创建一个新表并将“IsInNewPage”属性设置为“true”以在新页面上显示该表：

```csharp
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
table. ColumnWidths = "100 100";
for (int i = 1; i <= 10; i++)
{
     Aspose.Pdf.Row row = table1.Rows.Add();
     Aspose.Pdf.Cell cell1 = row.Cells.Add();
     cell1.Paragraphs.Add(new TextFragment("LAAAAAAA"));
     Aspose.Pdf.Cell cell2 = row.Cells.Add();
     cell2.Paragraphs.Add(new TextFragment("LAAGGGGGG"));
}
table1.IsInNewPage = true;
paragraphs. Add(table1);
```

## 第7步：保存PDF
最后，我们保存PDF文档：

```csharp
dataDir = dataDir + "IsNewPageProperty_Test_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nTable displayed successfully on a page.\nFile saved at location: " + dataDir);
```

### 使用 Aspose.PDF for .NET 的渲染表示例源代码

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
PageInfo pageInfo = doc.PageInfo;
Aspose.Pdf.MarginInfo marginInfo = pageInfo.Margin;

marginInfo.Left = 37;
marginInfo.Right = 37;
marginInfo.Top = 37;
marginInfo.Bottom = 37;

pageInfo.IsLandscape = true;

Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table.ColumnWidths = "50 100";
//添加页面。
Page curPage = doc.Pages.Add();
for (int i = 1; i <= 120; i++)
{
	Aspose.Pdf.Row row = table.Rows.Add();
	row.FixedRowHeight = 15;
	Aspose.Pdf.Cell cell1 = row.Cells.Add();
	cell1.Paragraphs.Add(new TextFragment("Content 1"));
	Aspose.Pdf.Cell cell2 = row.Cells.Add();
	cell2.Paragraphs.Add(new TextFragment("HHHHH"));
}
Aspose.Pdf.Paragraphs paragraphs = curPage.Paragraphs;
paragraphs.Add(table);
/********************************************/
Aspose.Pdf.Table table1 = new Aspose.Pdf.Table();
table.ColumnWidths = "100 100";
for (int i = 1; i <= 10; i++)
{
	Aspose.Pdf.Row row = table1.Rows.Add();
	Aspose.Pdf.Cell cell1 = row.Cells.Add();
	cell1.Paragraphs.Add(new TextFragment("LAAAAAAA"));
	Aspose.Pdf.Cell cell2 = row.Cells.Add();
	cell2.Paragraphs.Add(new TextFragment("LAAGGGGGG"));
}
table1.IsInNewPage = true;
//我想将表 1 保留到下一页...
paragraphs.Add(table1);
dataDir = dataDir + "IsNewPageProperty_Test_out.pdf";
doc.Save(dataDir);

Console.WriteLine("\nTable render successfully on a page.\nFile saved at " + dataDir);
```

## 结论
恭喜！您现在已经了解了如何使用 Aspose.PDF for .NET 在 PDF 文档中显示表格。本分步指南向您展示了如何创建文档、配置页边距和方向、添加表格以及在新页面上显示表格。现在您可以将这些知识应用到您自己的项目中。

### PDF 文档中渲染表的常见问题解答

#### 问：如何修改表格的外观，例如更改单元格颜色或添加边框？

A：要修改表格的外观，可以设置表格的各种属性`Aspose.Pdf.Table`及其细胞。例如，您可以设置`BackgroundColor`单元格的属性来更改其背景颜色。您还可以设置`Border`表格或单个单元格的属性来添加边框。此外，您还可以通过修改表格内容来自定义字体、文本颜色和对齐方式。`TextState`的`TextFragment`添加到单元格的对象。

#### 问：我可以在表格中添加页眉或页脚吗？

答：是的，您可以通过在表格的开头或结尾创建附加行并在单元格中设置适当的内容来向表格添加页眉或页脚。您可以通过向这些特定行添加不同的样式或内容来独立于表格内容的其余部分自定义页眉或页脚。

#### 问：如何控制表格在页面上的位置？

 A：要控制表格在页面上的位置，您可以调整`MarginInfo`的`PageInfo`目的。这`MarginInfo`允许您设置页面的左、右、上、下边距，这会影响表格的可用空间。您还可以使用`PositioningType`的财产`Aspose.Pdf.Table`控制其在页面内容区域内的水平和垂直对齐。

#### 问：我可以将表格导出为不同的文件格式，例如 Excel 或 CSV 吗？

答：Aspose.PDF for .NET 主要是为处理 PDF 文档而设计的。虽然它可以将 PDF 文档导出为图像或 XPS，但它不直接支持将表格导出为 Excel 或 CSV 等格式。要将表格数据导出为不同的文件格式，您可能需要使用其他库或方法将 PDF 内容转换为所需的格式。

#### 问：如何向表格单元格添加超链接？

答：要向表格单元格添加超链接，您可以使用`Aspose.Pdf.WebHyperlink`类来创建超链接，然后将其作为锚点添加到`TextFragment`细胞内。这允许您将 URL 或链接目标与单元格内的特定文本或内容相关联，从而创建可单击的超链接。