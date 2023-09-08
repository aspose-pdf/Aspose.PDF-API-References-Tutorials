---
title: 水平和垂直单选按钮
linktitle: 水平和垂直单选按钮
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 在 PDF 文档中轻松创建水平和垂直单选按钮。
type: docs
weight: 180
url: /zh/net/programming-with-forms/horizontally-and-vertically-radio-buttons/
---
在本教程中，我们将向您展示如何使用 Aspose.PDF for .NET 在 PDF 文档中创建水平和垂直排列的单选按钮。我们将逐步解释 C# 源代码，以指导您完成此过程。

## 第 1 步：准备

确保您已导入必要的库并设置文档目录的路径：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第 2 步：加载文档

加载现有的 PDF 文档：

```csharp
FormEditor formEditor = new FormEditor();
formEditor.BindPdf(dataDir + "input.pdf");
```

## 第 3 步：自定义单选按钮选项

通过设置以下属性来自定义单选按钮选项：

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

通过指定字段的选项和位置来添加垂直排列的单选按钮：

```csharp
formEditor. RadioHoriz = false; //单选按钮的垂直布局
formEditor.Items = new string[] { "First", "Second", "Third" };
formEditor.AddField(FieldType.Radio, "NewField2", 1, 40, 500, 60, 550);
```

## 第 6 步：保存文档

保存修改后的PDF文档：

```csharp
dataDir = dataDir + "HorizontallyAndVerticallyRadioButtons_out.pdf";
formEditor.Save(dataDir);
```

### 使用 Aspose.PDF for .NET 的水平和垂直单选按钮的示例源代码 
```csharp
try
{
	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	//加载之前保存的文档
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

在本教程中，我们学习了如何使用 Aspose.PDF for .NET 在 PDF 文档中创建水平和垂直排列的单选按钮。通过执行这些步骤，您可以轻松自定义单选按钮的布局，并使用 Aspose.PDF 将它们添加到 PDF 文档中。

### 常见问题解答

#### 问：PDF 文档中水平和垂直排列的单选按钮是什么？

答：PDF文档中单选按钮的水平和垂直排列是指单选按钮选项的布局方向。水平布局将单选按钮选项并排放置，允许用户从左到右进行选择。另一方面，垂直布局将单选按钮选项堆叠在一起，使用户能够从上到下进行选择。

#### 问：如何自定义 Aspose.PDF for .NET 中单选按钮选项的外观？

答：您可以通过调整多个属性来自定义 Aspose.PDF for .NET 中单选按钮选项的外观。 API 提供了设置两个单选按钮选项之间距离的选项（`RadioGap`），布局方向（`RadioHoriz`)、单选按钮项的大小 (`RadioButtonItemSize`)、单选按钮的边框宽度和颜色等等。

#### 问：我可以在同一个 PDF 文档中添加水平和垂直单选按钮吗？

答：是的，您可以使用 Aspose.PDF for .NET 将水平和垂直单选按钮添加到同一 PDF 文档中。本教程中提供的示例源代码演示了如何首先添加水平排列的单选按钮，然后向同一个 PDF 文档添加另一组垂直排列的单选按钮。

#### 问：我可以为每组单选按钮设置不同的单选按钮选项吗？

答：是的，您可以为每组单选按钮设置不同的单选按钮选项。每个组都应该有独特的`RadioButtonField`对象，以及`RadioButtonOptionField`每个组中的对象应共享相同的页面和其选项的唯一名称。这可确保每组中的单选按钮正常工作，并且选择是互斥的。

#### 问：所有 PDF 查看器和应用程序都支持单选按钮的布局和外观设置吗？

答：是的，所有符合标准的 PDF 查看器和应用程序都支持单选按钮的布局和外观设置。 PDF 规范定义了单选按钮及其各种属性，使它们在 PDF 格式中得到普遍认可。但是，必须测试单选按钮在不同 PDF 查看器中的外观和行为，以确保跨不同平台的渲染一致。