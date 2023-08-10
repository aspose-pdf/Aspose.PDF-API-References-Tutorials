---
title: PDF 文件中表格内的 HTML 标签
linktitle: PDF 文件中表格内的 HTML 标签
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 文件的表格内使用 HTML 标签。
type: docs
weight: 100
url: /zh/net/programming-with-tables/html-tags-inside-table/
---
在本教程中，我们将学习如何使用 Aspose.PDF for .NET 在 PDF 文档的表格内使用 HTML 标签。我们将一步步解释C#的源代码。在本教程结束时，您将了解如何将 HTML 内容插入到 PDF 文档的表格中。开始吧！

## 第一步：搭建环境
确保您已使用 Aspose.PDF for .NET 配置 C# 开发环境。添加对库的引用并导入必要的命名空间。

## 步骤2：创建表数据
我们创建一个包含字符串类型的“数据”列的数据表。然后，我们使用 HTML 内容将行添加到此 DataTable。

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
我们创建一个新的 PDF 文档并在该文档中添加一个页面。接下来，我们初始化 Table 类的实例并设置表属性。

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

## 第四步：将数据导入表中
我们使用“ImportDataTable”方法将数据从 DataTable 导入到表中。我们指定方法参数来指示应导入 DataTable 的行和列的范围。

```csharp
tableProvider.ImportDataTable(dt, false, 0, 0, 3, 1, true);
```

## 步骤 5：将表格添加到文档中
我们将表格添加到文档页面。

```csharp
doc.Pages[1].Paragraphs.Add(tableProvider);
```

## 第 6 阶段：保存文档
我们将 PDF 文档与包含 HTML 内容的表格一起保存。

```csharp
doc.Save(dataDir + "HTMLInsideTableCell_out.pdf");
```

### 使用 Aspose.PDF for .NET 的 HTML Tags Inside Table 的示例源代码

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
//初始化表的新实例
Aspose.Pdf.Table tableProvider = new Aspose.Pdf.Table();
//设置表格的列宽
tableProvider.ColumnWidths = "400 50 ";
//将表格边框颜色设置为浅灰色
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
在本教程中，我们学习了如何使用 Aspose.PDF for .NET 在 PDF 文档的表格内使用 HTML 标签。您可以使用此分步指南，使用 C# 将 HTML 内容插入到 PDF 文档的表格单元格中。

### PDF 文件中表格内 HTML 标签的常见问题解答

#### 问：我可以在表格单元格内使用其他 HTML 标签和属性吗？

答：是的，您可以在表格单元格内使用各种 HTML 标签和属性，例如`<b>`, `<i>`, `<a>`， 还有很多。 Aspose.PDF for .NET 支持多种 HTML 元素和样式，您可以使用它们来格式化表格单元格中的内容。

#### 问：我可以将 CSS 样式应用到表格单元格内的 HTML 内容吗？

答：是的，您可以将 CSS 样式应用到表格单元格内的 HTML 内容。 Aspose.PDF for .NET 提供对可应用于 HTML 元素的基本 CSS 样式的支持。

#### 问：是否可以在表格单元格内添加图像和 HTML 内容？

答：是的，您可以在表格单元格内添加图像和 HTML 内容。您可以使用 HTML`<img>`标签以包含来自各种来源的图像，例如本地文件或 URL。

#### 问：如何为表格指定不同的列宽？

答：您可以使用以下命令为表格指定不同的列宽`ColumnWidths`表的属性。该属性采用包含空格分隔值的字符串，其中每个值代表列的宽度（以磅为单位）。

#### 问：我可以在包含 HTML 内容的单元格内使用嵌套表格吗？

答：是的，您可以在包含 HTML 内容的单元格内使用嵌套表格。您可以创建单独的表实例并将它们添加为单元格内 HTML 内容的一部分以实现嵌套效果。