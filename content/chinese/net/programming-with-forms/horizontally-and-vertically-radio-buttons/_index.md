---
title: 水平和垂直单选按钮
linktitle: 水平和垂直单选按钮
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 轻松在 PDF 文档中创建水平和垂直单选按钮。
type: docs
weight: 180
url: /zh/net/programming-with-forms/horizontally-and-vertically-radio-buttons/
---
在本教程中，我们将向您展示如何使用 Aspose.PDF for .NET 在 PDF 文档中创建水平和垂直排列的单选按钮。我们将逐步解释 C# 源代码以指导您完成此过程。

## 步骤 1：准备

确保您已导入必要的库并设置文档目录的路径：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第 2 步：加载文档

加载现有的PDF文档：

```csharp
FormEditor formEditor = new FormEditor();
formEditor.BindPdf(dataDir + "input.pdf");
```

## 步骤 3：自定义单选按钮选项

通过设置以下属性来自定义单选按钮选项：

```csharp
formEditor. RadioGap = 4; //两个单选按钮选项之间的距离
formEditor. RadioHoriz = true; //单选按钮的水平布局
formEditor.RadioButtonItemSize = 20; //单选按钮的大小
formEditor.Facade.BorderWidth = 1; //单选按钮边框的宽度
formEditor.Facade.BorderColor = System.Drawing.Color.Black; //单选按钮边框颜色
```

## 步骤 4：添加水平单选按钮

通过指定字段的选项和位置来添加水平排列的单选按钮：

```csharp
formEditor.Items = new string[] { "First", "Second", "Third" };
formEditor.AddField(FieldType.Radio, "NewField1", 1, 40, 600, 120, 620);
```

## 步骤 5：添加垂直单选按钮

通过指定字段的选项和位置来添加垂直排列的单选按钮：

```csharp
formEditor. RadioHoriz = false; //单选按钮的垂直布局
formEditor.Items = new string[] { "First", "Second", "Third" };
formEditor.AddField(FieldType.Radio, "NewField2", 1, 40, 500, 60, 550);
```

## 步骤 6：保存文档

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
	//加载先前保存的文档
	FormEditor formEditor = new FormEditor();
	formEditor.BindPdf(dataDir + "input.pdf");
	//RadioGap 是两个单选按钮选项之间的距离。
	formEditor.RadioGap = 4;
	//添加水平单选按钮
	formEditor.RadioHoriz = true;
	//RadioButtonItemSize 是单选按钮项的大小。
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

在本教程中，我们学习了如何使用 Aspose.PDF for .NET 在 PDF 文档中创建水平和垂直排列的单选按钮。通过遵循这些步骤，您可以轻松自定义单选按钮的布局并使用 Aspose.PDF 将它们添加到您的 PDF 文档中。

### 常见问题解答

#### 问：PDF 文档中水平和垂直排列的单选按钮是什么？

答：PDF 文档中单选按钮的水平和垂直排列是指单选按钮选项的布局方向。水平布局将单选按钮选项并排放置，允许用户从左到右进行选择。而垂直布局将单选按钮选项堆叠在一起，允许用户从上到下进行选择。

#### 问：如何自定义 Aspose.PDF for .NET 中单选按钮选项的外观？

答：您可以通过调整几个属性来自定义 Aspose.PDF for .NET 中单选按钮选项的外观。API 提供了设置两个单选按钮选项之间距离的选项（`RadioGap`)、布局方向（`RadioHoriz`）、单选按钮项的大小（`RadioButtonItemSize`)、单选按钮的边框宽度和颜色等等。

#### 问：我可以向同一个 PDF 文档同时添加水平和垂直单选按钮吗？

答：是的，您可以使用 Aspose.PDF for .NET 将水平和垂直单选按钮添加到同一个 PDF 文档中。本教程中提供的示例源代码演示了如何首先添加水平排列的单选按钮，然后将另一组垂直排列的单选按钮添加到同一个 PDF 文档中。

#### 问：我可以为每组单选按钮设置不同的单选按钮选项吗？

答：是的，您可以为每组单选按钮设置不同的单选按钮选项。每组应该有一个唯一的单选按钮选项`RadioButtonField`对象，以及`RadioButtonOptionField`每个组内的对象应共享相同的页面和其选项的唯一名称。这可确保每个组内的单选按钮正常工作，并且选项是互斥的。

#### 问：所有 PDF 查看器和应用程序是否都支持单选按钮的布局和外观设置？

答：是的，所有符合标准的 PDF 查看器和应用程序都支持单选按钮的布局和外观设置。PDF 规范定义了单选按钮及其各种属性，使它们在 PDF 格式中得到普遍认可。但是，有必要在不同的 PDF 查看器中测试单选按钮的外观和行为，以确保在各个平台上的渲染一致。