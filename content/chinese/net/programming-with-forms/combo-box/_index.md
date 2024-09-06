---
title: 组合框
linktitle: 组合框
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 轻松在 PDF 文档中创建组合框列表。
type: docs
weight: 30
url: /zh/net/programming-with-forms/combo-box/
---
在本教程中，我们将向您展示如何使用 Aspose.PDF for .NET 创建组合框列表。我们将逐步解释 C# 源代码以指导您完成此过程。

## 步骤 1：准备

首先，确保您已经导入了必要的库并设置了文档目录的路径：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 步骤 2：创建文档对象

创建一个 Document 对象来保存 PDF 表单：

```csharp
Document doc = new Document();
```

## 步骤 3：添加页面

向文档添加页面：

```csharp
doc.Pages.Add();
```

## 步骤 4：实例化 ComboBoxField 对象

实例化具有所需尺寸的 ComboBoxField 对象：

```csharp
ComboBoxField combo = new ComboBoxField(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 600, 150, 616));
```

## 步骤 5：向下拉列表添加选项

将所需选项添加到下拉列表中：

```csharp
combo.AddOption("Red");
combo.AddOption("Yellow");
combo.AddOption("Green");
combo.AddOption("Blue");
```

## 步骤 6：将组合框列表添加到表单

将 ComboBoxField 对象添加到文档表单字段集合：

```csharp
doc.Form.Add(combo);
```

## 步骤 7：保存文档

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
	//创建 Document 对象
	Document doc = new Document();
	//将页面添加到文档对象
	doc.Pages.Add();
	//实例化 ComboBox 字段对象
	ComboBoxField combo = new ComboBoxField(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 600, 150, 616));
	//向 ComboBox 添加选项
	combo.AddOption("Red");
	combo.AddOption("Yellow");
	combo.AddOption("Green");
	combo.AddOption("Blue");
	//将组合框对象添加到文档对象的表单字段集合中
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

在本教程中，我们学习了如何使用 Aspose.PDF for .NET 创建组合框列表。按照以下步骤，您可以使用 Aspose.PDF 轻松地将组合框列表添加到 PDF 文档中。

### 常见问题解答

#### 问：我可以使用 Aspose.PDF for .NET 自定义组合框列表的外观吗？

答：是的，您可以使用 Aspose.PDF for .NET 自定义组合框列表的外观。您可以设置字体大小、颜色、背景颜色、边框样式等属性，以匹配您想要的外观和感觉。

#### 问：我可以设置组合框列表中的默认选择选项吗？

答：是的，您可以使用 Aspose.PDF for .NET 在组合框列表中设置默认选定选项。您可以使用`Selected`的财产`ComboBoxField`对象将一个或多个选项标记为默认选择。

#### 问：用户做出选择后，如何从组合框列表中检索选定的值？

答：您可以使用 Aspose.PDF for .NET 从组合框列表中检索选定的值。用户做出选择后，您可以访问`Value`的财产`ComboBoxField`对象来获取所选的值。

#### 问：是否可以向组合框列表添加事件处理程序或动作？

答：是的，Aspose.PDF for .NET 允许您将事件处理程序或操作添加到组合框列表中。您可以关联 JavaScript 操作，例如`OnValueChanged`，添加到组合框列表中，当用户选择一个选项时执行特定的操作。

#### 问：我可以为组合框列表中的选项添加工具提示或描述吗？

答：是的，您可以使用 Aspose.PDF for .NET 向组合框列表中的选项添加工具提示或描述。您可以设置`AlternateName`每个选项的属性提供当用户将鼠标悬停在该选项上时显示的工具提示或描述。