---
title: 删除表格
linktitle: 删除表格
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 删除 PDF 文档中的表格。
type: docs
weight: 160
url: /zh/net/programming-with-tables/remove-table/
---

在本教程中，我们将指导您使用 Aspose.PDF for .NET 逐步删除 PDF 文档中的表格。我们将解释提供的 C# 源代码并向您展示如何实现它。

## 第 1 步：加载现有的 PDF 文档
首先，您需要使用以下代码加载现有的 PDF 文档：

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//加载现有的 PDF 文档
Document pdfDocument = new Document(dataDir + "Table_input.pdf");
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
为了能够删除表格，我们将获取页面的第一个表格：

```csharp
//获取页面上的第一个表
AbsorbedTable table = absorb.TableList[0];
```

## 第五步：删除表
现在让我们使用吸收器移除桌子：

```csharp
//删除表
absorb.Remove(table);
```

## 第 6 步：保存 PDF
最后，我们保存修改后的PDF文档：

```csharp
//保存 PDF
pdfDocument.Save(dataDir + "Table_out.pdf");
```

### 使用 Aspose.Words for .NET 删除表格的示例源代码

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//加载现有的 PDF 文档
Document pdfDocument = new Document(dataDir + "Table_input.pdf");

//创建 TableAbsorber 对象以查找表
TableAbsorber absorber = new TableAbsorber();

//使用吸收器访问第一页
absorber.Visit(pdfDocument.Pages[1]);

//获取页面上的第一个表
AbsorbedTable table = absorber.TableList[0];

//删除表
absorber.Remove(table);

//保存PDF
pdfDocument.Save(dataDir + "Table_out.pdf");
```

## 结论
恭喜！您现在已经学习了如何使用 Aspose.PDF for .NET 删除 PDF 文档中的表格。本分步指南向您展示了如何加载文档、查找表格并将其删除。现在您可以将这些知识应用到您自己的项目中。