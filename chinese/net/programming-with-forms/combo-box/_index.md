---
title: 组合框
linktitle: 组合框
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 在您的 PDF 文档中轻松创建组合框列表。
type: docs
weight: 30
url: /zh/net/programming-with-forms/combo-box/
---

在本教程中，我们将向您展示如何使用 Aspose.PDF for .NET 创建组合框列表。我们将逐步解释 C# 源代码，以指导您完成此过程。

## 第一步：准备

首先，确保您已导入必要的库并设置文档目录的路径：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：创建文档对象

创建一个 Document 对象来保存 PDF 表单：

```csharp
Document doc = new Document();
```

## 第三步：添加页面

向文档添加页面：

```csharp
doc.Pages.Add();
```

## 第 4 步：实例化一个 ComboBoxField 对象

实例化具有所需尺寸的 ComboBoxField 对象：

```csharp
ComboBoxField combo = new ComboBoxField(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 600, 150, 616));
```

## 第 5 步：向下拉列表中添加选项

将所需的选项添加到下拉列表中：

```csharp
combo.AddOption("Red");
combo.AddOption("Yellow");
combo.AddOption("Green");
combo.AddOption("Blue");
```

## 第 6 步：将组合框列表添加到窗体

将 ComboBoxField 对象添加到 Document Form Fields 集合：

```csharp
doc.Form.Add(combo);
```

## 第 7 步：保存文档

保存 PDF 文档：

```csharp
dataDir = dataDir + "ComboBox_out.pdf";
doc.Save(dataDir);
```

### 使用 Aspose.PDF for .NET 的组合框示例源代码 
```csharp
try
{
	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	//创建文档对象
	Document doc = new Document();
	//将页面添加到文档对象
	doc.Pages.Add();
	//实例化 ComboBox Field 对象
	ComboBoxField combo = new ComboBoxField(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 600, 150, 616));
	//向 ComboBox 添加选项
	combo.AddOption("Red");
	combo.AddOption("Yellow");
	combo.AddOption("Green");
	combo.AddOption("Blue");
	//添加组合框对象以形成文档对象的字段集合
	doc.Form.Add(combo);
	dataDir = dataDir + "ComboBox_out.pdf";
	//保存 PDF 文档
	doc.Save(dataDir);
	Console.WriteLine("\nCombobox field added successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## 结论

在本教程中，我们学习了如何使用 Aspose.PDF for .NET 创建组合框列表。按照这些步骤，您可以使用 Aspose.PDF 轻松地将组合框列表添加到您的 PDF 文档中。