---
title: 表格行内容的文本对齐
linktitle: 表格行内容的文本对齐
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 对齐 PDF 表格中的行内容。
type: docs
weight: 210
url: /zh/net/programming-with-tables/text-alignment-for-table-row-content/
---
在本教程中，我们将逐步指导您使用 Aspose.PDF for .NET 对齐 PDF 文档表格中的行内容。我们将解释提供的 C# 源代码并向您展示如何实现它。

## 第 1 步：创建 PDF 文档
首先，我们将创建 PDF 文档：

```csharp
var dataDir = "YOUR DOCUMENTS DIRECTORY";
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

## 步骤2：表初始化
接下来，我们将初始化表：

```csharp
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
```

## 第三步：设置表格边框颜色
我们将配置表格边框颜色：

```csharp
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

## 步骤 4：配置表格单元格边框
我们将配置表格单元格边框：

```csharp
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

## 第 5 步：循环向表中添加 10 行
现在，我们将使用循环向表中添加 10 行：

```csharp
for (int row_count = 0; row_count < 10; row_count++)
{
     Aspose.Pdf.Row row = table.Rows.Add();
     row.VerticalAlignment = VerticalAlignment.Center;

     row.Cells.Add("Column("+row_count+",1)"+DateTime.Now.Ticks);
     row.Cells.Add("Column("+row_count+",2)");
     row.Cells.Add("Column("+row_count+",3)");
}
```

## 步骤 6：配置垂直线对齐
我们将配置表行的垂直对齐方式：

```csharp
row.VerticalAlignment = VerticalAlignment.Center;
```

## 步骤 7：向行单元格添加内容
我们将向行单元格添加内容：

```csharp
row.Cells.Add("Column("+row_count+",1)"+DateTime.Now.Ticks);
row.Cells.Add("Column("+row_count+",2)");
row.Cells.Add("Column("+row_count+",3)");
```

## 步骤8：将表格添加到文档页面
现在让我们将表格添加到文档页面：

```csharp
Page tocPage = doc.Pages.Add();
tocPage.Paragraphs.Add(table);
```

## 第9步：保存PDF文档
最后，我们保存PDF文档：

```csharp
doc.Save(dataDir + "43620_ByWords_out.pdf");
```

### 使用 Aspose.PDF for .NET 进行表行内容文本对齐的示例源代码

```csharp
var dataDir = "YOUR DOCUMENT DIRECTORY";

//创建 PDF 文档
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
//初始化表的新实例
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
//将表格边框颜色设置为浅灰色
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
//设置表格单元格的边框
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
//创建一个循环以添加 10 行
for (int row_count = 0; row_count < 10; row_count++)
{
	//将行添加到表中
	Aspose.Pdf.Row row = table.Rows.Add();
	row.VerticalAlignment = VerticalAlignment.Center;

	row.Cells.Add("Column (" + row_count + ", 1)" + DateTime.Now.Ticks);
	row.Cells.Add("Column (" + row_count + ", 2)");
	row.Cells.Add("Column (" + row_count + ", 3)");
}
Page tocPage = doc.Pages.Add();
//将表格对象添加到输入文档的第一页
tocPage.Paragraphs.Add(table);
//保存包含表对象的更新文档
doc.Save(dataDir + "43620_ByWords_out.pdf");
```

## 结论
恭喜！您现在已经了解了如何使用 Aspose.PDF for .NET 对齐 PDF 文档表格中的行内容。本分步指南向您展示了如何创建文档、初始化表格、配置边框和对齐方式、添加内容以及保存 PDF 文档。现在您可以将这些知识应用到您自己的项目中。

### 常见问题解答

#### 问：如何水平对齐表格单元格的内容？

答：您可以通过设置水平对齐表格单元格的内容`HorizontalAlign`细胞的属性`TextState`目的。例如，要居中对齐文本，请使用`cell.TextState.HorizontalAlignment = HorizontalAlignment.Center`。您也可以将其设置为`HorizontalAlignment.Left`或者`HorizontalAlignment.Right`分别用于左对齐和右对齐。

#### 问：我可以对表格中的各个单元格应用不同的边框样式和颜色吗？

答：是的，您可以对表格中的各个单元格应用不同的边框样式和颜色。要自定义特定单元格的边框，请设置`cell.Border`属性为新的`BorderInfo`具有所需设置的对象，例如边框边、宽度和颜色。

#### 问：如何调整单元格内表格内容的垂直对齐方式？

答：您可以通过设置单元格内的表格内容的垂直对齐方式`VerticalAlignment`行的属性为`VerticalAlignment.Center`, `VerticalAlignment.Top`， 或者`VerticalAlignment.Bottom`。此属性控制该行中所有单元格的垂直对齐方式。

#### 问：是否可以动态向表添加更多列或行？

答：是的，您可以使用以下命令动态向表中添加更多列和行`table.Rows.Add()`添加新行的方法和`row.Cells.Add()`方法将新单元格添加到行中。您可以在循环内或根据您的具体要求执行此操作。

#### 问：如何为特定单元格或整个表格设置背景颜色？

答：要为特定单元格或整个表格设置背景颜色，请使用`BackgroundColor`的财产`Cell`或者`Table`目的。例如，要设置单元格的背景颜色，请使用`cell.BackgroundColor = Aspose.Pdf.Color.LightBlue`.