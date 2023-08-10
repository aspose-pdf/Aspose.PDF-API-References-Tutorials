---
title: 组合框
linktitle: 组合框
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 在 PDF 文档中轻松创建组合框列表。
type: docs
weight: 30
url: /zh/net/programming-with-forms/combo-box/
---
在本教程中，我们将向您展示如何使用 Aspose.PDF for .NET 创建组合框列表。我们将逐步解释 C# 源代码，以指导您完成此过程。

## 第 1 步：准备

首先，确保您已导入必要的库并设置文档目录的路径：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：创建文档对象

创建一个 Document 对象来保存 PDF 表单：

```csharp
Document doc = new Document();
```

## 第 3 步：添加页面

向文档添加页面：

```csharp
doc.Pages.Add();
```

## 第 4 步：实例化 ComboBoxField 对象

实例化具有所需尺寸的 ComboBoxField 对象：

```csharp
ComboBoxField combo = new ComboBoxField(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 600, 150, 616));
```

## 步骤 5：将选项添加到下拉列表

将所需的选项添加到下拉列表中：

```csharp
combo.AddOption("Red");
combo.AddOption("Yellow");
combo.AddOption("Green");
combo.AddOption("Blue");
```

## 步骤 6：将组合框列表添加到表单中

将 ComboBoxField 对象添加到文档表单字段集合：

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
	//将选项添加到组合框
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

在本教程中，我们学习了如何使用 Aspose.PDF for .NET 创建组合框列表。通过执行以下步骤，您可以使用 Aspose.PDF 轻松地将组合框列表添加到 PDF 文档中。

### 常见问题解答

#### 问：我可以使用 Aspose.PDF for .NET 自定义组合框列表的外观吗？

答：是的，您可以使用 Aspose.PDF for .NET 自定义组合框列表的外观。您可以设置字体大小、颜色、背景颜色、边框样式等属性，以匹配您所需的外观和感觉。

#### 问：我可以在组合框列表中设置默认选择的选项吗？

答：是的，您可以使用 Aspose.PDF for .NET 在组合框列表中设置默认选定选项。您可以使用`Selected`的财产`ComboBoxField`对象将一个或多个选项标记为默认选择。

#### 问：用户做出选择后，如何从组合框列表中检索所选值？

答：您可以使用 Aspose.PDF for .NET 从组合框列表中检索所选值。用户做出选择后，您可以访问`Value`的财产`ComboBoxField`对象来获取选定的值。

#### 问：是否可以将事件处理程序或操作添加到组合框列表中？

答：是的，Aspose.PDF for .NET 允许您将事件处理程序或操作添加到组合框列表中。您可以关联 JavaScript 操作，例如`OnValueChanged`，到组合框列表以在用户选择选项时执行特定操作。

#### 问：我可以向组合框列表中的选项添加工具提示或说明吗？

答：是的，您可以使用 Aspose.PDF for .NET 将工具提示或描述添加到组合框列表中的选项。您可以设置`AlternateName`每个选项的属性，以提供当用户将鼠标悬停在选项上时将显示的工具提示或说明。