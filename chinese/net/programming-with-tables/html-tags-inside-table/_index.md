---
title: 表格内的 HTML 标签
linktitle: 表格内的 HTML 标签
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 文档的表格内使用 HTML 标签。
type: docs
weight: 100
url: /zh/net/programming-with-tables/html-tags-inside-table/
---

在本教程中，我们将学习如何使用 Aspose.PDF for .NET 在 PDF 文档的表格内使用 HTML 标签。我们将逐步解释 C# 中的源代码。在本教程结束时，您将了解如何将 HTML 内容插入 PDF 文档的表格中。开始吧！

## 第 1 步：设置环境
确保您已经使用 Aspose.PDF for .NET 配置了 C# 开发环境。添加对库的引用并导入必要的命名空间。

## 第二步：创建表数据
我们创建一个包含字符串类型的“数据”列的数据表。然后，我们使用 HTML 内容向此 DataTable 添加行。

```csharp
DataTable dt = new DataTable("Employee");
dt.Columns.Add("data", System.Type.GetType("System.String"));

DataRow dr = dt.NewRow();
dr[0] = "<li>Department of Emergency Medicine: 3400 Spruce Street Ground Silverstein Bldg Philadelphia PA 19104-4206</li>";
dt.Rows.Add(dr);
dr = dt. NewRow();
dr[0] = "<li>Penn Observation Medicine Service: 3400 Spruce Street Ground Floor Donner Philadelphia PA 19104-4206</li>";
dt.Rows.Add(dr);
dr = dt. NewRow();
dr[0] = "<li>UPHS/Presbyterian - Dept. of Emergency Medicine: 51 N. 39th Street . Philadelphia PA 19104-2640</li>";
dt.Rows.Add(dr);
```

## 第 3 步：创建文档和表格
我们新建一个PDF文档，并在这个文档中添加一个页面。接下来，我们初始化 Table 类的实例并设置表属性。

```csharp
Document doc = new Document();
doc.Pages.Add();

Aspose.Pdf.Table tableProvider = new Aspose.Pdf.Table();
tableProvider. ColumnWidths = "400 50";
tableProvider.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
tableProvider.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin. Top = 2.5F;
margin. Left = 2.5F;
margin. Bottom = 1.0F;
tableProvider. DefaultCellPadding = margin;
```

## 第四步：导入数据到表中
我们使用“ImportDataTable”方法将数据从 DataTable 导入到表中。我们指定方法参数来指示应导入 DataTable 的行和列的范围。

```csharp
tableProvider.ImportDataTable(dt, false, 0, 0, 3, 1, true);
```

## 第 5 步：将表格添加到文档
我们将表格添加到文档页面。

```csharp
doc.Pages[1].Paragraphs.Add(tableProvider);
```

## 第 6 阶段：保存文档
我们用包含 HTML 内容的表格保存 PDF 文档。

```csharp
doc.Save(dataDir + "HTMLInsideTableCell_out.pdf");
```

### 使用 Aspose.Words for .NET 的表内 HTML 标签示例源代码

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

DataTable dt = new DataTable("Employee");
dt.Columns.Add("data", System.Type.GetType("System.String"));

DataRow dr = dt.NewRow();
dr[0] = "<li>Department of Emergency Medicine: 3400 Spruce Street Ground Silverstein Bldg Philadelphia PA 19104-4206</li>";
dt.Rows.Add(dr);
dr = dt.NewRow();
dr[0] = "<li>Penn Observation Medicine Service: 3400 Spruce Street Ground Floor Donner Philadelphia PA 19104-4206</li>";
dt.Rows.Add(dr);
dr = dt.NewRow();
dr[0] = "<li>UPHS/Presbyterian - Dept. of Emergency Medicine: 51 N. 39th Street . Philadelphia PA 19104-2640</li>";
dt.Rows.Add(dr);

Document doc = new Document();
doc.Pages.Add();
//初始化 Table 的新实例
Aspose.Pdf.Table tableProvider = new Aspose.Pdf.Table();
//设置表格的列宽
tableProvider.ColumnWidths = "400 50 ";
//将表格边框颜色设置为 LightGray
tableProvider.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
//设置表格单元格的边框
tableProvider.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, 0.5F, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
Aspose.Pdf.MarginInfo margin = new Aspose.Pdf.MarginInfo();
margin.Top = 2.5F;
margin.Left = 2.5F;
margin.Bottom = 1.0F;
tableProvider.DefaultCellPadding = margin;

tableProvider.ImportDataTable(dt, false, 0, 0, 3, 1, true);

doc.Pages[1].Paragraphs.Add(tableProvider);
doc.Save(dataDir + "HTMLInsideTableCell_out.pdf");
```

## 结论
在本教程中，我们学习了如何使用 Aspose.PDF for .NET 在 PDF 文档的表格内使用 HTML 标签。您可以使用此分步指南使用 C# 将 HTML 内容插入到 PDF 文档的表格单元格中。