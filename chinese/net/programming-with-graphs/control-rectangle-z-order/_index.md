---
title: 控制矩形 Z 顺序
linktitle: 控制矩形 Z 顺序
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 控制 PDF 文件中矩形的 Z 顺序。
type: docs
weight: 40
url: /zh/net/programming-with-graphs/control-rectangle-z-order/
---

在本教程中，我们将通过以下 C# 源代码逐步引导您使用 Aspose.PDF for .NET 控制矩形的 Z 顺序。

在开始之前，请确保您已经安装了 Aspose.PDF 库并设置了您的开发环境。还具有 C# 编程的基本知识。

## 第 1 步：文档目录设置

在提供的源代码中，您需要指定要保存生成的 PDF 文件的目录。将“dataDir”变量更改为所需的目录。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第 2 步：实例化文档对象并添加页面

我们创建一个 Document 类的实例并向该文档添加一个页面。

```csharp
Document doc1 = new Document();
Aspose.Pdf.Page page1 = doc1.Pages.Add();
```

## 第 3 步：设置页面大小

我们使用 SetPageSize 方法设置 PDF 页面大小。

```csharp
page1.SetPageSize(375, 300);
```

## 第 4 步：设置页边距

我们可以使用 PageInfo 对象的属性来配置页边距。

```csharp
page1.PageInfo.Margin.Left = 0;
page1.PageInfo.Margin.Top = 0;
```

## 第 5 步：添加具有指定 Z 顺序的矩形

我们创建矩形并将其添加到具有不同颜色和指定 Z 顺序的页面。

```csharp
AddRectangle(page1, 50, 40, 60, 40, Aspose.Pdf.Color.Red, 2);
AddRectangle(page1, 20, 20, 30, 30, Aspose.Pdf.Color.Blue, 1);
AddRectangle(page1, 40, 40, 60, 30, Aspose.Pdf.Color.Green, 0);
```

## 第 6 步：保存生成的 PDF 文件

最后，我们将生成的 PDF 文件保存在指定目录中，名称为“ControlRectangleZOrder_out.pdf”。

```csharp
doc1.Save(dataDir);
```
### 使用 Aspose.Words for .NET 的控制矩形 Z 顺序的示例源代码 

```csharp

//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//实例化文档类对象
Document doc1 = new Document();
//添加页面到 PDF 文件的页面集合
Aspose.Pdf.Page page1 = doc1.Pages.Add();
//设置PDF页面大小
page1.SetPageSize(375, 300);
//将页面对象的左边距设置为 0
page1.PageInfo.Margin.Left = 0;
//将页面对象的上边距设置为 0
page1.PageInfo.Margin.Top = 0;
//创建一个 Color 为 Red，Z-Order 为 0 和特定尺寸的新矩形
AddRectangle(page1, 50, 40, 60, 40, Aspose.Pdf.Color.Red, 2);
//创建一个颜色为蓝色、Z-Order 为 0 和特定尺寸的新矩形
AddRectangle(page1, 20, 20, 30, 30, Aspose.Pdf.Color.Blue, 1);
//创建一个颜色为绿色、Z-Order 为 0 和特定尺寸的新矩形
AddRectangle(page1, 40, 40, 60, 30, Aspose.Pdf.Color.Green, 0);
dataDir = dataDir + "ControlRectangleZOrder_out.pdf";
//保存生成的 PDF 文件
doc1.Save(dataDir);

```

## 结论

在本教程中，我们解释了如何使用 Aspose.PDF for .NET 控制矩形的 Z 顺序。您现在可以使用这些知识在 PDF 文件中精确排列和分层矩形。
