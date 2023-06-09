---
title: 选择单选按钮
linktitle: 选择单选按钮
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 选择 PDF 文档中的单选按钮。
type: docs
weight: 250
url: /zh/net/programming-with-forms/select-radio-button/
---

下面是关于如何使用 Aspose.PDF for .NET 选择单选按钮的详细教程。按着这些次序：

## 第 1 步：首先通过在`dataDir` variable.

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第 2 步：使用打开 PDF 文档`Document` class and the document path.

```csharp
Document pdfDocument = new Document(dataDir + "RadioButton.pdf");
```

## 第 3 步：从文档表单中获取单选按钮字段。

```csharp
RadioButtonField radioField = pdfDocument.Form["radio"] as RadioButtonField;
```

## 第 4 步：指定要从组中选择的单选按钮的索引。

```csharp
radioField. Selected = 2;
```

## 第五步：设置编辑好的PDF文件的输出路径。

```csharp
dataDir = dataDir + "SelectRadioButton_out.pdf";
```

## 第 6 步：保存修改后的 PDF 文件。

```csharp
pdfDocument.Save(dataDir);
```

## 第 7 步：显示确认消息和保存文件的位置。

```csharp
Console.WriteLine("\nRadio button successfully selected in group.\nFile saved to location: " + dataDir);
```

### 使用 Aspose.PDF for .NET 选择单选按钮的示例源代码 
```csharp
try
{
	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	//打开文档
	Document pdfDocument = new Document(dataDir + "RadioButton.pdf");
	//获取字段
	RadioButtonField radioField = pdfDocument.Form["radio"] as RadioButtonField;
	//指定组中单选按钮的索引
	radioField.Selected = 2;
	dataDir = dataDir + "SelectRadioButton_out.pdf";
	//保存 PDF 文件
	pdfDocument.Save(dataDir);
	Console.WriteLine("\nRadioButton from group selected successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## 结论

在本教程中，我们学习了如何使用 Aspose.PDF for .NET 选择单选按钮。按照上述步骤，您可以使用 Aspose.PDF for .NET 操作和修改 PDF 文档中的单选按钮。