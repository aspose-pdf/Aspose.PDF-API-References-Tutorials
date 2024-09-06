---
title: 获取 PDF 表单字段坐标
linktitle: 获取 PDF 表单字段坐标
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 轻松获取 PDF 文档中的 PDF 表单字段坐标。
type: docs
weight: 120
url: /zh/net/programming-with-forms/get-coordinates/
---
在本教程中，我们将向您展示如何使用 Aspose.PDF for .NET 获取 PDF 表单字段坐标。我们将逐步解释 C# 源代码以指导您完成此过程。

## 步骤 1：准备

确保您已经导入必要的库并设置文档目录的路径：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 步骤 2：加载输出文档

加载输出 PDF 文档：

```csharp
Document doc1 = new Document(dataDir + "input.pdf");
```

## 步骤 3：查找添加的字段

找到添加的表单字段（在此示例中，我们使用“Item1”、“Item2”和“Item3”字段）：

```csharp
RadioButtonField field0 = doc1.Form["Item1"] as RadioButtonField;
RadioButtonField field1 = doc1.Form["Item2"] as RadioButtonField;
RadioButtonField field2 = doc1.Form["Item3"] as RadioButtonField;
```

## 步骤 4：显示每个字段的子项目位置

循环浏览每个字段的选项并查看每个子项的坐标：

```csharp
foreach(RadioButtonOptionField option in field0)
{
Console.WriteLine(option.Rect);
}
foreach(RadioButtonOptionField option in field1)
{
Console.WriteLine(option.Rect);
}
foreach(RadioButtonOptionField option in field2)
{
Console.WriteLine(option.Rect);
}
```

### 使用 Aspose.PDF for .NET 获取坐标的示例源代码 
```csharp
try
{
	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	//加载输出文档
	Document doc1 = new Document( dataDir + "input.pdf");
	//查找添加的字段
	RadioButtonField field0 = doc1.Form["Item1"] as RadioButtonField;
	RadioButtonField field1 = doc1.Form["Item2"] as RadioButtonField;
	RadioButtonField field2 = doc1.Form["Item3"] as RadioButtonField;
	//并显示每个子项目的位置。
	foreach (RadioButtonOptionField option in field0)
	{
		Console.WriteLine(option.Rect);
	}
	foreach (RadioButtonOptionField option in field1)
	{
		Console.WriteLine(option.Rect);
	}
	foreach (RadioButtonOptionField option in field2)
	{
		Console.WriteLine(option.Rect);
	}
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## 结论

在本教程中，我们学习了如何使用 Aspose.PDF for .NET 获取表单字段坐标。按照以下步骤，您可以使用 Aspose.PDF 轻松检索 PDF 文档中表单字段子元素的坐标。

### 常见问题解答

#### 问：我可以使用此方法获取 Aspose.Pdf for .NET 中任何类型的表单字段的坐标吗？

答：是的，您可以使用此方法获取 Aspose.PDF for .NET 中各种表单字段的坐标。提供的 C# 源代码演示了如何获取 RadioButton 字段的坐标，但您可以将相同的方法应用于其他表单字段类型，例如 TextBox、CheckBox、ListBox 等。

#### 问：如何修改或调整表单域坐标？

答：表单字段坐标基于 PDF 文档的坐标系，其中原点 (0,0) 位于页面的左下角。要修改或调整表单字段坐标，您可以更新`Rect`相应表单字段或其子项的属性，例如 RadioButtonOptionField。

#### 问：我可以以编程方式获取添加到 PDF 文档的表单字段的坐标吗？

答：是的，您可以获取以编程方式添加到 PDF 文档的表单字段的坐标。Aspose.PDF for .NET 允许您动态添加表单字段，添加后，您可以使用本教程中演示的方法检索其坐标。

#### 问：检索表单字段坐标的目的是什么？

答：当您需要对 PDF 文档中的表单字段执行特定的布局相关操作或验证时，检索表单字段坐标会很有帮助。它允许您根据表单字段的坐标准确定位和对齐表单字段，确保它们在文档中正确显示并提供无缝的用户体验。

#### 问：表单域坐标是以点还是其他单位来表示？

答：Aspose.PDF for .NET 中的表单字段坐标以点表示。一个点相当于 1/72 英寸，是 PDF 格式的标准测量单位。