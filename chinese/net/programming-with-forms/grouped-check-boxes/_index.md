---
title: 分组复选框
linktitle: 分组复选框
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 在您的 PDF 文档中轻松创建分组复选框。
type: docs
weight: 170
url: /zh/net/programming-with-forms/grouped-check-boxes/
---

在本教程中，我们将向您展示如何使用 Aspose.PDF for .NET 在 PDF 文档中创建分组复选框。我们将逐步解释 C# 源代码，以指导您完成此过程。

## 第一步：准备

确保您已导入必要的库并设置文档目录的路径：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第 2 步：实例化文档对象

实例化一个文档对象：

```csharp
Document pdfDocument = new Document();
```

## 第 3 步：将页面添加到 PDF 文档

向 PDF 文档添加页面：

```csharp
Page page = pdfDocument.Pages.Add();
```

## 第 4 步：实例化 RadioButtonField 对象

使用页码作为参数实例化一个 RadioButtonField 对象：

```csharp
RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
```

## 第 5 步：添加单选按钮选项

使用 RadioButtonOptionField 对象添加单选按钮选项，并使用 Rectangle 对象指定它们的位置：

```csharp
RadioButtonOptionField opt1 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(0, 0, 20, 20));
RadioButtonOptionField opt2 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(100, 0, 120, 20));
opt1.OptionName = "Test1";
opt2.OptionName = "Test2";
radio.Add(opt1);
radio.Add(opt2);
```

## 第 6 步：自定义单选按钮选项

通过设置样式、边框和外观来自定义单选按钮选项：

```csharp
opt1.Style = BoxStyle.Square;
opt2.Style = BoxStyle.Square;
opt1.Border = new Border(opt1);
opt1.Border.Style = BorderStyle.Solid;
opt1.Border.Width = 1;
opt2.Border = new Border(opt2);
opt2.Border.Width = 1;
opt2.Border.Style = BorderStyle.Solid;
```

## 第 7 步：将单选按钮添加到表单

将单选按钮添加到文档表单对象：

```csharp
pdfDocument.Form.Add(radio);
```

## 第 8 步：保存文档

保存 PDF 文档：

```csharp
dataDir = dataDir + "GroupedCheckBoxes_out.pdf";
pdfDocument.Save(dataDir);
```

### 使用 Aspose.Words for .NET 的分组复选框示例源代码 
```csharp
try
{
	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	//实例化文档对象
	Document pdfDocument = new Document();
	//向 PDF 文件添加页面
	Page page = pdfDocument.Pages.Add();
	//使用页码作为参数实例化 RadioButtonField 对象
	RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
	//添加第一个单选按钮选项并使用 Rectangle 对象指定其原点
	RadioButtonOptionField opt1 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(0, 0, 20, 20));
	RadioButtonOptionField opt2 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(100, 0, 120, 20));
	opt1.OptionName = "Test1";
	opt2.OptionName = "Test2";
	radio.Add(opt1);
	radio.Add(opt2);
	opt1.Style = BoxStyle.Square;
	opt2.Style = BoxStyle.Square;
	opt1.Style = BoxStyle.Cross;
	opt2.Style = BoxStyle.Cross;
	opt1.Border = new Border(opt1);
	opt1.Border.Style = BorderStyle.Solid;
	opt1.Border.Width = 1;
	opt1.Characteristics.Border = System.Drawing.Color.Black;
	opt2.Border = new Border(opt2);
	opt2.Border.Width = 1;
	opt2.Border.Style = BorderStyle.Solid;
	opt2.Characteristics.Border = System.Drawing.Color.Black;
	//将单选按钮添加到 Document 对象的表单对象
	pdfDocument.Form.Add(radio);
	dataDir = dataDir + "GroupedCheckBoxes_out.pdf";
	//保存 PDF 文档
	pdfDocument.Save(dataDir);
	Console.WriteLine("\nGrouped checkboxes added successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## 结论

在本教程中，我们学习了如何使用 Aspose.PDF for .NET 在 PDF 文档中创建分组复选框。按照这些步骤，您可以轻松地添加自定义单选按钮选项，并使用 Aspose.PDF 将它们捆绑在您的 PDF 文档中。