---
title: 单选按钮
linktitle: 单选按钮
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 轻松地将单选按钮添加到您的 PDF 文档。
type: docs
weight: 220
url: /zh/net/programming-with-forms/radio-button/
---

在本教程中，我们将向您展示如何使用 Aspose.PDF for .NET 在 PDF 文档中添加单选按钮。我们将逐步解释 C# 源代码，以指导您完成此过程。

## 第一步：准备

确保您已导入必要的库并设置文档目录的路径：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第 2 步：实例化文档对象

实例化一个 Document 对象来创建一个新的 PDF 文档：

```csharp
Document pdfDocument = new Document();
```

## 第三步：添加页面

向 PDF 文档添加页面：

```csharp
pdfDocument.Pages.Add();
```

## 第 4 步：实例化 RadioButtonField 对象

实例化一个 RadioButtonField 对象，指定页码作为参数：

```csharp
RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
```

## 第 5 步：添加单选按钮选项

通过使用 Rectangle 对象指定每个选项的坐标，将单选按钮选项添加到 RadioButtonField 对象：

```csharp
radio.AddOption("Test", new Rectangle(0, 0, 20, 20));
radio.AddOption("Test1", new Rectangle(20, 20, 40, 40));
```

## 第 6 步：将单选按钮添加到表单

将单选按钮添加到文档的 Form 对象：

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
	//实例化文档对象
	Document pdfDocument = new Document();
	//向 PDF 文件添加页面
	pdfDocument.Pages.Add();
	//使用页码作为参数实例化 RadioButtonField 对象
	RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
	//添加第一个单选按钮选项并使用 Rectangle 对象指定其原点
	radio.AddOption("Test", new Rectangle(0, 0, 20, 20));
	//添加第二个单选按钮选项
	radio.AddOption("Test1", new Rectangle(20, 20, 40, 40));
	//将单选按钮添加到 Document 对象的表单对象
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

在本教程中，我们学习了如何使用 Aspose.PDF for .NET 在 PDF 文档中添加单选按钮。按照这些步骤，您可以轻松创建单选按钮并将其放置在 PDF 文档的特定页面上。