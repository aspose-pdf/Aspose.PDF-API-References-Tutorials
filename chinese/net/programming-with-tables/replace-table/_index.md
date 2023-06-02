---
title: 替换表
linktitle: 替换表
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 替换 PDF 文档中的表格。
type: docs
weight: 180
url: /zh/net/programming-with-tables/replace-table/
---

在本教程中，我们将逐步指导您使用 Aspose.PDF for .NET 替换 PDF 文档中的表格。我们将解释提供的 C# 源代码并向您展示如何实现它。

## 第 1 步：加载现有的 PDF 文档
首先，您需要使用以下代码加载现有的 PDF 文档：

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//加载现有的 PDF 文档
Document pdfDocument = new Document(dataDir + @"Table_input.pdf");
```

## 第 2 步：创建 TableAbsorber 对象以查找表
接下来，我们将创建一个 TableAbsorber 对象来查找 PDF 文档中的表格：

```csharp
//创建一个 TableAbsorber 对象来查找表
TableAbsorber absorber = new TableAbsorber();
```

## 第 3 步：使用吸收器访问第一页
我们现在将使用吸收器访问 PDF 文档的第一页：

```csharp
//使用吸收器访问第一页
absorb.Visit(pdfDocument.Pages[1]);
```

## 第 4 步：获取页面上的第一个表
为了能够替换表格，我们将获取页面的第一个表格：

```csharp
//获取页面上的第一个表
AbsorbedTable table = absorb.TableList[0];
```

## 第 5 步：创建新表
现在我们将创建一个包含所需列和单元格的新表：

```csharp
Table newTable = new Table();
newTable.ColumnWidths = "100 100 100";
newTable.DefaultCellBorder = new BorderInfo(BorderSide.All, 1F);

Row row = newTable.Rows.Add();
row. Cells. Add("Col 1");
row. Cells. Add("Col 2");
row. Cells. Add("Col 3");
```

## 第 6 步：用新表替换现有表
我们现在将在文档的第一页用新表格替换现有表格：

```csharp
//用新表替换表
absorb.Replace(pdfDocument.Pages[1], table, newTable);
```

## 第 7 步：保存文档
最后，我们保存修改后的PDF文档：

```csharp
pdfDocument.Save(dataDir + "TableReplaced_out.pdf");
```

### 使用 Aspose.Words for .NET 替换表的示例源代码

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//加载现有的 PDF 文档
Document pdfDocument = new Document(dataDir + @"Table_input.pdf");

//创建 TableAbsorber 对象以查找表
TableAbsorber absorber = new TableAbsorber();

//使用吸收器访问第一页
absorber.Visit(pdfDocument.Pages[1]);

//获取页面上的第一个表
AbsorbedTable table = absorber.TableList[0];

//创建新表
Table newTable = new Table();
newTable.ColumnWidths = "100 100 100";
newTable.DefaultCellBorder = new BorderInfo(BorderSide.All, 1F);

Row row = newTable.Rows.Add();
row.Cells.Add("Col 1");
row.Cells.Add("Col 2");
row.Cells.Add("Col 3");

//换一张新桌子
absorber.Replace(pdfDocument.Pages[1], table, newTable);

//保存文件
pdfDocument.Save(dataDir + "TableReplaced_out.pdf");
```

## 结论
恭喜！您现在已经了解了如何使用 Aspose.PDF for .NET 替换 PDF 文档中的表格。这个分步指南向您展示了如何加载文档、查找现有表、创建新表以及替换它。现在您可以将这些知识应用到您自己的项目中。