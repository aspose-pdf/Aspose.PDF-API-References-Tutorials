---
title: 水平和垂直单选按钮
linktitle: 水平和垂直单选按钮
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 在您的 PDF 文档中轻松创建水平和垂直单选按钮。
type: docs
weight: 180
url: /zh/net/programming-with-forms/horizontally-and-vertically-radio-buttons/
---

在本教程中，我们将向您展示如何使用 Aspose.PDF for .NET 在 PDF 文档中创建水平和垂直排列的单选按钮。我们将逐步解释 C# 源代码，以指导您完成此过程。

## 第一步：准备

确保您已导入必要的库并设置文档目录的路径：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第 2 步：装入文档

加载现有的 PDF 文档：

```csharp
FormEditor formEditor = new FormEditor();
formEditor.BindPdf(dataDir + "input.pdf");
```

## 第 3 步：自定义单选按钮选项

通过设置以下属性自定义单选按钮选项：

```csharp
formEditor. RadioGap = 4; //两个单选按钮选项之间的距离
formEditor. RadioHoriz = true; //单选按钮的水平布局
formEditor.RadioButtonItemSize = 20; //单选按钮的大小
formEditor.Facade.BorderWidth = 1; //单选按钮边框的宽度
formEditor.Facade.BorderColor = System.Drawing.Color.Black; //单选按钮边框颜色
```

## 第 4 步：添加水平单选按钮

通过指定字段的选项和位置来添加水平排列的单选按钮：

```csharp
formEditor.Items = new string[] { "First", "Second", "Third" };
formEditor.AddField(FieldType.Radio, "NewField1", 1, 40, 600, 120, 620);
```

## 第 5 步：添加垂直单选按钮

通过指定字段的选项和位置添加垂直排列的单选按钮：

```csharp
formEditor. RadioHoriz = false; //单选按钮的垂直布局
formEditor.Items = new string[] { "First", "Second", "Third" };
formEditor.AddField(FieldType.Radio, "NewField2", 1, 40, 500, 60, 550);
```

## 第 6 步：保存文档

保存修改后的 PDF 文档：

```csharp
dataDir = dataDir + "HorizontallyAndVerticallyRadioButtons_out.pdf";
formEditor.Save(dataDir);
```

### 使用 Aspose.Words for .NET 的水平和垂直单选按钮的示例源代码 
```csharp
try
{
	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	//载入之前保存的文档
	FormEditor formEditor = new FormEditor();
	formEditor.BindPdf(dataDir + "input.pdf");
	//RadioGap 是两个单选按钮选项之间的距离。
	formEditor.RadioGap = 4;
	//添加水平单选按钮
	formEditor.RadioHoriz = true;
	//RadioButtonItemSize 如果单选按钮项目的大小。
	formEditor.RadioButtonItemSize = 20;
	formEditor.Facade.BorderWidth = 1;
	formEditor.Facade.BorderColor = System.Drawing.Color.Black;
	formEditor.Items = new string[] { "First", "Second", "Third" };
	formEditor.AddField(FieldType.Radio, "NewField1", 1, 40, 600, 120, 620);
	//添加其他垂直放置的单选按钮
	formEditor.RadioHoriz = false;
	formEditor.Items = new string[] { "First", "Second", "Third" };
	formEditor.AddField(FieldType.Radio, "NewField2", 1, 40, 500, 60, 550);
	dataDir = dataDir + "HorizontallyAndVerticallyRadioButtons_out.pdf";
	//保存 PDF 文档
	formEditor.Save(dataDir);
	Console.WriteLine("\nHorizontally and vertically laid out radio buttons successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## 结论

在本教程中，我们学习了如何使用 Aspose.PDF for .NET 在 PDF 文档中创建水平和垂直排列的单选按钮。按照这些步骤，您可以轻松地自定义单选按钮的布局，并使用 Aspose.PDF 将它们添加到您的 PDF 文档中。