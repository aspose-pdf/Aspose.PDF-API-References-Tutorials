---
title: 删除多个表
linktitle: 删除多个表
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 删除 PDF 文档中的多个表格。
type: docs
weight: 150
url: /zh/net/programming-with-tables/remove-multiple-tables/
---

在本教程中，我们将指导您使用 Aspose.PDF for .NET 逐步删除 PDF 文档中的多个表格。我们将解释提供的 C# 源代码并向您展示如何实现它。

## 第 1 步：加载现有的 PDF 文档
首先，您需要使用以下代码加载现有的 PDF 文档：

```csharp
//文档目录的路径
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//加载现有的 PDF 文档
Document pdfDocument = new Document(dataDir + "Table_input2.pdf");
```

## 第 2 步：创建 TableAbsorber 对象以查找表
接下来，我们将创建一个 TableAbsorber 对象来查找 PDF 文档中的表格：

```csharp
//创建一个 TableAbsorber 对象来查找表
TableAbsorber absorber = new TableAbsorber();
```

## 第 3 步：使用吸收器访问第二页
我们现在将使用吸收器访问 PDF 文档的第二页：

```csharp
//使用吸收器访问第二页
absorb.Visit(pdfDocument.Pages[1]);
```

## 第 4 步：获取表集合的副本
为了能够删除表，我们需要获取表集合的副本：

```csharp
//获取表集合的副本
AbsorbedTable[] tables = new AbsorbedTable[absorb.TableList.Count];
absorb.TableList.CopyTo(tables, 0);
```

## 第 5 步：浏览集合的副本并删除表
现在让我们遍历表集合的副本并一张一张地删除它们：

```csharp
//浏览集合的副本并删除表格
foreach(AbsorbedTable table in tables)
     absorb.Remove(table);
```

## 第 6 步：保存文档
最后，我们保存修改后的PDF文档：

```csharp
//保存文件
pdfDocument.Save(dataDir + "Table2_out.pdf");
```

### 使用 Aspose.Words for .NET 删除多个表的示例源代码

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//加载现有的 PDF 文档
Document pdfDocument = new Document(dataDir + "Table_input2.pdf");

//创建 TableAbsorber 对象以查找表
TableAbsorber absorber = new TableAbsorber();

//使用吸收器访问第二页
absorber.Visit(pdfDocument.Pages[1]);

//获取表集合的副本
AbsorbedTable[] tables = new AbsorbedTable[absorber.TableList.Count];
absorber.TableList.CopyTo(tables, 0);

//遍历集合副本并删除表
foreach (AbsorbedTable table in tables)
	absorber.Remove(table);

//保存文件
pdfDocument.Save(dataDir + "Table2_out.pdf");
```

## 结论
恭喜！您现在已经了解了如何使用 Aspose.PDF for .NET 删除 PDF 文档中的多个表格。本分步指南向您展示了如何上传文档、查找表格以及删除表格。现在您可以将这些知识应用到您自己的项目中。