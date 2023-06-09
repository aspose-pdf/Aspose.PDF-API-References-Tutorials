---
title: 与数据库集成
linktitle: 与数据库集成
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 将数据库中的数据嵌入到 PDF 文档中。
type: docs
weight: 120
url: /zh/net/programming-with-tables/integrate-with-database/
---

在本教程中，我们将学习如何使用 Aspose.PDF for .NET 将数据库中的数据嵌入到 PDF 文档中。我们将逐步解释 C# 中的源代码。在本教程结束时，您将了解如何将表格数据从数据库导入 PDF 文档。开始吧！

## 第 1 步：设置环境
确保您已经使用 Aspose.PDF for .NET 配置了 C# 开发环境。添加对库的引用并导入必要的命名空间。

## 第 2 步：创建数据表
我们创建一个 DataTable 实例来表示我们要嵌入 PDF 文档的数据。在此示例中，我们创建了一个包含三列的 DataTable：Employee_ID、Employee_Name 和 Gender。我们还使用虚拟数据向 DataTable 添加了两行。

```csharp
DataTable dt = new DataTable("Employee");
dt.Columns.Add("Employee_ID", typeof(Int32));
dt.Columns.Add("Employee_Name", typeof(string));
dt.Columns.Add("Gender", typeof(string));

DataRow dr = dt.NewRow();
dr[0] = 1;
dr[1] = "John Smith";
dr[2] = "Male";
dt.Rows.Add(dr);

dr = dt. NewRow();
dr[0] = 2;
dr[1] = "Mary Miller";
dr[2] = "Female";
dt.Rows.Add(dr);
```

## 第 3 步：创建 PDF 文档和表格
我们创建一个 Document 实例并向该文档添加一个页面。接下来，我们创建一个 Table 实例来表示 PDF 文档中的表格。我们定义表格列宽和边框样式。

```csharp
Document doc = new Document();
doc.Pages.Add();

Aspose.Pdf.Table table = new Aspose.Pdf.Table();
table. ColumnWidths = "40 100 100 100";
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
```

## 第四步：将DataTable中的数据导入表中
我们使用 ImportDataTable 方法将 DataTable 中的数据导入到 PDF 文档中的表格中。

```csharp
table.ImportDataTable(dt, true, 0, 1, 3, 3);
```

## 第 5 步：将表格添加到文档
我们将表格添加到文档页面的段落集合中。

```csharp
doc.Pages[1].Paragraphs.Add(table);
```

## 第 6 步：保存文档
我们使用嵌入式数据库中的数据保存 PDF 文档。

```csharp
doc.Save(dataDir + "DataIntegrated_out.pdf");
```

恭喜！您现在知道如何使用 Aspose.PDF for .NET 将数据库数据嵌入到 PDF 文档中。

### 使用 Aspose.PDF for .NET 与数据库集成的示例源代码

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

DataTable dt = new DataTable("Employee");
dt.Columns.Add("Employee_ID", typeof(Int32));
dt.Columns.Add("Employee_Name", typeof(string));
dt.Columns.Add("Gender", typeof(string));
//以编程方式将 2 行添加到 DataTable 对象中
DataRow dr = dt.NewRow();
dr[0] = 1;
dr[1] = "John Smith";
dr[2] = "Male";
dt.Rows.Add(dr);
dr = dt.NewRow();
dr[0] = 2;
dr[1] = "Mary Miller";
dr[2] = "Female";
dt.Rows.Add(dr);
//创建文档实例
Document doc = new Document();
doc.Pages.Add();
//初始化 Table 的新实例
Aspose.Pdf.Table table = new Aspose.Pdf.Table();
//设置表格的列宽
table.ColumnWidths = "40 100 100 100";
//将表格边框颜色设置为 LightGray
table.Border = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
//设置表格单元格的边框
table.DefaultCellBorder = new Aspose.Pdf.BorderInfo(Aspose.Pdf.BorderSide.All, .5f, Aspose.Pdf.Color.FromRgb(System.Drawing.Color.LightGray));
table.ImportDataTable(dt, true, 0, 1, 3, 3);

//将表格对象添加到输入文档的第一页
doc.Pages[1].Paragraphs.Add(table);
dataDir = dataDir + "DataIntegrated_out.pdf";
//保存包含表格对象的更新文档
doc.Save(dataDir);

Console.WriteLine("\nDatabase integrated successfully.\nFile saved at " + dataDir);
```

## 结论
在本教程中，我们学习了如何使用 Aspose.PDF for .NET 将数据库中的数据嵌入到 PDF 文档中。您可以使用此分步指南从您自己的数据库中导入数据并将其显示在 PDF 文档中。进一步探索 Aspose.PDF 文档，发现这个功能强大的库提供的其他功能和可能性。