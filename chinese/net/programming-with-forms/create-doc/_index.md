---
title: 创建文档
linktitle: 创建文档
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 轻松创建带有单选按钮的文档。
type: docs
weight: 40
url: /zh/net/programming-with-forms/create-doc/
---

在本教程中，我们将向您展示如何使用 Aspose.PDF for .NET 创建带有单选按钮的文档。我们将逐步解释 C# 源代码，以指导您完成此过程。

##第一步：准备

首先，确保您已导入必要的库并设置文档目录的路径：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：创建新文档

创建一个新的 Document 对象来保存 PDF 文档：

```csharp
Document doc = new Document();
```

## 第三步：添加页面

向文档添加新页面：

```csharp
Page page = doc.Pages.Add();
```

## 第 4 步：添加单选按钮字段

创建一个单选按钮字段并设置其位置和大小：

```csharp
RadioButtonField field = new RadioButtonField(page);
field.Rect = new Aspose.Pdf.Rectangle(40, 650, 100, 720);
field. PartialName = "NewField";
```

## 第 5 步：添加单选按钮选项

将所需的选项添加到单选按钮字段。您可以根据需要设置每个选项的坐标和大小：

```csharp
RadioButtonOptionField opt1 = new RadioButtonOptionField();
opt1.Rect = new Aspose.Pdf.Rectangle(40, 650, 60, 670);
opt1.OptionName = "Item1";
opt1.Border = new Border(opt1);
opt1.Border.Width = 1;
opt1.Characteristics.Border = System.Drawing.Color.Black;

RadioButtonOptionField opt2 = new RadioButtonOptionField();
opt2.Rect = new Aspose.Pdf.Rectangle(60, 670, 80, 690);
opt2.OptionName = "Item2";
opt2.Border = new Border(opt2);
opt2.Border.Width = 1;
opt2.Characteristics.Border = System.Drawing.Color.Black;

RadioButtonOptionField opt3 = new RadioButtonOptionField();
opt3.Rect = new Aspose.Pdf.Rectangle(80, 690, 100, 710);
opt3.OptionName = "Item3";
opt3.Border = new Border(opt3);
opt3.Border.Width = 1;
opt3.Characteristics.Border = System.Drawing.Color.Black;

field. Add(opt1);
field. Add(opt2);
field. Add(opt3);
```

## 第 6 步：将单选按钮字段添加到表单

将单选按钮字段添加到文档表单字段集合：

```csharp
doc.Form.Add(field);
```

## 第 7 步：保存文档

保存 PDF 文档：

```csharp
dataDir = dataDir + "CreateDoc_out.pdf";
doc.Save(dataDir);
```

### 使用 Aspose.Words for .NET 创建文档的示例源代码 
```csharp
try
{
	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	//创建一个新文档
	Document doc = new Document();
	Page page = doc.Pages.Add();
	//添加单选按钮字段
	RadioButtonField field = new RadioButtonField(page);
	field.Rect = new Aspose.Pdf.Rectangle(40, 650, 100, 720);
	field.PartialName = "NewField";
	//添加单选按钮选项。请注意，这些选项位于
	//既不是水平的也不是垂直的。
	//您可以尝试为它们设置任何坐标（甚至大小）。
	RadioButtonOptionField opt1 = new RadioButtonOptionField();
	opt1.Rect = new Aspose.Pdf.Rectangle(40, 650, 60, 670);
	opt1.OptionName = "Item1";
	opt1.Border = new Border(opt1);
	opt1.Border.Width = 1;
	opt1.Characteristics.Border = System.Drawing.Color.Black;
	RadioButtonOptionField opt2 = new RadioButtonOptionField();
	opt2.Rect = new Aspose.Pdf.Rectangle(60, 670, 80, 690);
	opt2.OptionName = "Item2";
	opt2.Border = new Border(opt2);
	opt2.Border.Width = 1;
	opt2.Characteristics.Border = System.Drawing.Color.Black;
	RadioButtonOptionField opt3 = new RadioButtonOptionField();
	opt3.Rect = new Aspose.Pdf.Rectangle(80, 690, 100, 710);
	opt3.OptionName = "Item3";
	opt3.Border = new Border(opt3);
	opt3.Border.Width = 1;
	opt3.Characteristics.Border = System.Drawing.Color.Black;
	field.Add(opt1);
	field.Add(opt2);
	field.Add(opt3);
	doc.Form.Add(field);
	dataDir = dataDir + "CreateDoc_out.pdf";
	//保存 PDF 文档
	doc.Save(dataDir);
	Console.WriteLine("\nNew doc with 3 items radio button created successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## 结论

在本教程中，我们学习了如何使用 Aspose.PDF for .NET 创建带有单选按钮的文档。按照这些步骤，您可以使用 Aspose.PDF 轻松地将单选按钮添加到您的 PDF 文档。