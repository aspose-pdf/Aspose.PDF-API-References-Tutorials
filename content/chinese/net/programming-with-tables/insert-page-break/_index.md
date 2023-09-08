---
title: 在 PDF 文件中插入分页符
linktitle: 在 PDF 文件中插入分页符
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 文件中插入分页符。
type: docs
weight: 110
url: /zh/net/programming-with-tables/insert-page-break/
---
在本教程中，我们将学习如何使用 Aspose.PDF for .NET 在 PDF 文件中插入分页符。我们将一步步解释C#的源代码。在本教程结束时，您将了解如何在 PDF 文档表格中的一定行数之后添加分页符。开始吧！

## 第一步：搭建环境
确保您已使用 Aspose.PDF for .NET 配置 C# 开发环境。添加对库的引用并导入必要的命名空间。

## 第2步：创建文档和表格
我们创建一个新的 Document 实例并向该文档添加一个页面。接下来，我们创建一个 Table 实例来表示 PDF 文档中的表格。我们还定义了表格的边框样式。

```csharp
Document doc = new Document();
doc.Pages.Add();

Aspose.Pdf.Table tab = new Aspose.Pdf.Table();
tab.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
tab.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
tab. ColumnWidths = "100 100";
```

## 步骤 3：向表中添加行
我们使用循环向数组添加 200 行。对于每一行，我们创建一个 Row 实例并添加两个包含文本内容的单元格。

```csharp
for (int counter = 0; counter <= 200; counter++)
{
     Aspose.Pdf.Row row = new Aspose.Pdf.Row();
     tab. Rows. Add(row);
    
     Aspose.Pdf.Cell cell1 = new Aspose.Pdf.Cell();
     cell1.Paragraphs.Add(new TextFragment("Cell " + counter + ", 0"));
     row. Cells. Add(cell1);
    
     Aspose.Pdf.Cell cell2 = new Aspose.Pdf.Cell();
     cell2.Paragraphs.Add(new TextFragment("Cell " + counter + ", 1"));
     row. Cells. Add(cell2);
    
     //当添加 10 行时，我们插入一个新的分页符
     if (counter % 10 == 0 && counter != 0)
         row. IsInNewPage = true;
}
```

## 步骤 4：将表格添加到文档中
我们将表格添加到文档页面的段落集合中。

```csharp
doc.Pages[1].Paragraphs.Add(tab);
```

## 第 5 步：保存文档
我们保存插入分页符的 PDF 文档。

```csharp
doc.Save(dataDir + "InsertPageBreak_out.pdf");
```

### 使用 Aspose.PDF for .NET 插入分页符的示例源代码

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//实例化文档实例
Document doc = new Document();
//将页面添加到 PDF 文件的页面集合
doc.Pages.Add();
//创建表实例
Aspose.Pdf.Table tab = new Aspose.Pdf.Table();
//设置表格边框样式
tab.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
//设置表格的默认边框样式，边框颜色为红色
tab.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, Aspose.Pdf.Color.Red);
//指定表列宽度
tab.ColumnWidths = "100 100";
//创建一个循环为表添加 200 行
for (int counter = 0; counter <= 200; counter++)
{
	Aspose.Pdf.Row row = new Aspose.Pdf.Row();
	tab.Rows.Add(row);
	Aspose.Pdf.Cell cell1 = new Aspose.Pdf.Cell();
	cell1.Paragraphs.Add(new TextFragment("Cell " + counter + ", 0"));
	row.Cells.Add(cell1); Aspose.Pdf.Cell cell2 = new Aspose.Pdf.Cell();
	cell2.Paragraphs.Add(new TextFragment("Cell " + counter + ", 1"));
	row.Cells.Add(cell2);
	//添加 10 行时，在新页面中呈现新行
	if (counter % 10 == 0 && counter != 0) row.IsInNewPage = true;
}
//将表格添加到 PDF 文件的段落集合中
doc.Pages[1].Paragraphs.Add(tab);

dataDir = dataDir + "InsertPageBreak_out.pdf";
//保存 PDF 文档
doc.Save(dataDir);

Console.WriteLine("\nPage break inserted successfully.\nFile saved at " + dataDir);
```

## 结论
在本教程中，我们学习了如何使用 Aspose.PDF for .NET 在 PDF 文档中插入分页符。您可以使用此分步指南，使用 C# 在 PDF 文档的表格中的特定行数之后添加分页符。

### 在 PDF 文件中插入分页符的常见问题解答

#### 问：如何更改分页后创建的新页面的页面大小？

答：要更改分页符后创建的新页面的页面大小，您可以设置`PageSize`的财产`Page`目的。例如，您可以使用以下代码将页面尺寸设置为A4：

```csharp
//将页面大小设置为A4
doc.Pages[1].SetPageSize(PageSize.A4);
```

#### 问：我可以控制分页后新页面的页边距吗？

答：是的，您可以控制分页后新页面的页边距。使用`Margin`的财产`Page`对象设置页边距。例如，要将所有边距设置为 10 磅，可以使用以下代码：

```csharp
//将所有边距设置为 10 点
doc.Pages[1].Margin = new MarginInfo(10, 10, 10, 10);
```

#### 问：分页后的新页面是否可以添加页眉和页脚？

答：是的，您可以在分页符后的新页面中添加页眉和页脚。使用`Page.Header`和`Page.Footer`属性将内容添加到页面的页眉和页脚部分。例如：

```csharp
//将标题添加到新页面
doc.Pages[1].Header = new HeaderFooter()
{
    Margin = new MarginInfo(10, 10, 10, 10),
    Paragraphs = { new TextFragment("Header content") }
};

//将页脚添加到新页面
doc.Pages[1].Footer = new HeaderFooter()
{
    Margin = new MarginInfo(10, 10, 10, 10),
    Paragraphs = { new TextFragment("Footer content") }
};
```

#### 问：除了一定数量的行之后，我可以在特定位置插入分页符吗？

答：是的，您可以在特定位置插入分页符，而不是在一定行数之后。您可以设置`IsInNewPage`行的属性为`true`强制表在该行之后开始一个新页面。

#### 问：如何根据内容高度调整分页行为？

答：您可以使用`IsBroken`表的属性可启用或禁用跨页自动断行。当设置为`true`，它允许根据内容高度跨页面分隔行。