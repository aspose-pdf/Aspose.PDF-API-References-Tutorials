---
title: 获取坐标
linktitle: 获取坐标
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 轻松获取 PDF 文档中的表单域坐标。
type: docs
weight: 120
url: /zh/net/programming-with-forms/get-coordinates/
---

在本教程中，我们将向您展示如何使用 Aspose.PDF for .NET 获取表单字段坐标。我们将逐步解释 C# 源代码，以指导您完成此过程。

## 第一步：准备

确保您已导入必要的库并设置文档目录的路径：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：加载输出文档

加载输出的 PDF 文档：

```csharp
Document doc1 = new Document(dataDir + "input.pdf");
```

## 第 3 步：查找添加的字段

找到添加的表单字段（在本例中，我们使用“Item1”、“Item2”和“Item3”字段）：

```csharp
RadioButtonField field0 = doc1.Form["Item1"] as RadioButtonField;
RadioButtonField field1 = doc1.Form["Item2"] as RadioButtonField;
RadioButtonField field2 = doc1.Form["Item3"] as RadioButtonField;
```

## 第 4 步：显示每个字段的子项位置

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
	//并显示每个子项的位置。
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

在本教程中，我们学习了如何使用 Aspose.PDF for .NET 获取表单字段坐标。通过执行这些步骤，您可以使用 Aspose.PDF 轻松地检索 PDF 文档中表单域子元素的坐标。