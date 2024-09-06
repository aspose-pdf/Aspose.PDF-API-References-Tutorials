---
title: 单选按钮
linktitle: 单选按钮
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 轻松地将单选按钮添加到您的 PDF 文档中。
type: docs
weight: 220
url: /zh/net/programming-with-forms/radio-button/
---
在本教程中，我们将向您展示如何使用 Aspose.PDF for .NET 在 PDF 文档中添加单选按钮。我们将逐步解释 C# 源代码以指导您完成此过程。

## 步骤 1：准备

确保您已导入必要的库并设置文档目录的路径：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 步骤 2：实例化文档对象

实例化一个 Document 对象来创建一个新的 PDF 文档：

```csharp
Document pdfDocument = new Document();
```

## 步骤 3：添加页面

向 PDF 文档添加页面：

```csharp
pdfDocument.Pages.Add();
```

## 步骤 4：实例化 RadioButtonField 对象

实例化一个 RadioButtonField 对象并指定页码作为参数：

```csharp
RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
```

## 步骤 5：添加单选按钮选项

通过使用 Rectangle 对象指定每个选项的坐标，将单选按钮选项添加到 RadioButtonField 对象：

```csharp
radio.AddOption("Test", new Rectangle(0, 0, 20, 20));
radio.AddOption("Test1", new Rectangle(20, 20, 40, 40));
```

## 步骤 6：将单选按钮添加到表单

将单选按钮添加到文档的表单对象：

```csharp
pdfDocument.Form.Add(radio);
```

## 步骤 7：保存 PDF 文档

保存创建的PDF文档：

```csharp
dataDir = dataDir + "RadioButton_out.pdf";
pdfDocument.Save(dataDir);
```

### 使用 Aspose.PDF for .NET 的单选按钮示例源代码 
```csharp
try
{
	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	//实例化 Document 对象
	Document pdfDocument = new Document();
	//向 PDF 文件添加页面
	pdfDocument.Pages.Add();
	//使用页码作为参数来实例化 RadioButtonField 对象
	RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
	//添加第一个单选按钮选项并使用矩形对象指定其原点
	radio.AddOption("Test", new Rectangle(0, 0, 20, 20));
	//添加第二个单选按钮选项
	radio.AddOption("Test1", new Rectangle(20, 20, 40, 40));
	//向 Document 对象的表单对象中添加单选按钮
	pdfDocument.Form.Add(radio);
	dataDir = dataDir + "RadioButton_out.pdf";
	//保存 PDF 文件
	pdfDocument.Save(dataDir);
	Console.WriteLine("\nRadio button field added successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## 结论

在本教程中，我们学习了如何使用 Aspose.PDF for .NET 在 PDF 文档中添加单选按钮。按照以下步骤，您可以轻松创建单选按钮并将其放置在 PDF 文档的特定页面上。


### 常见问题解答

#### 问：我可以自定义单选按钮的外观，例如其大小和颜色吗？

答：是的，您可以使用`Rectangle`对象的坐标来定义其大小和位置。Aspose.PDF for .NET 允许您调整单选按钮的外观以满足您的需要。

#### 问：我可以在同一页面上添加具有不同组的多个单选按钮吗？

答：可以，您可以在同一页面上添加多个不同组的单选按钮。每组单选按钮可以有唯一的名称，并且每次只能选择每组中的一个选项。

#### 问：如何为单选按钮选项添加标签或文字描述？

答：要为单选按钮选项添加标签或文本描述，您可以使用`TextStamp`来自 Aspose.PDF for .NET 的类，在特定坐标处的 PDF 文档上叠加文本。

#### 问：Aspose.PDF for .NET 是否与所有版本的 .NET Framework 兼容？

答：是的，Aspose.PDF for .NET 与所有版本的 .NET Framework 兼容，包括 .NET Core 和 .NET Standard。

#### 问：我可以以编程方式控制 PDF 文档中单选按钮选项的选择吗？

答：是的，你可以使用以下方式以编程方式控制单选按钮选项的选择：`IsSelected`的财产`RadioButtonOption`类。此属性允许您将特定选项设置为已选择。