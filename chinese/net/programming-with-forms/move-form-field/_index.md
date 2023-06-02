---
title: 移动表单域
linktitle: 移动表单域
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 轻松移动 PDF 文档中的表单域。
type: docs
weight: 200
url: /zh/net/programming-with-forms/move-form-field/
---

在本教程中，我们将向您展示如何使用 Aspose.PDF for .NET 在 PDF 文档中移动表单域。我们将逐步解释 C# 源代码，以指导您完成此过程。

## 第一步：准备

确保您已导入必要的库并设置文档目录的路径：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第 2 步：装入文档

加载现有的 PDF 文档：

```csharp
Document pdfDocument = new Document(dataDir + "MoveFormField.pdf");
```

## 第三步：获取表单域

获取要移动的表单域：

```csharp
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
```

## 第 4 步：更改字段位置

通过定义一个新的矩形区域来改变表单域的位置：

```csharp
textBoxField.Rect = new Aspose.Pdf.Rectangle(300, 400, 600, 500);
```

## 第五步：保存编辑好的文档

保存修改后的 PDF 文档：

```csharp
dataDir = dataDir + "MoveFormField_out.pdf";
pdfDocument.Save(dataDir);
```

### 使用 Aspose.Words for .NET 移动表单字段的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//打开文档
Document pdfDocument = new Document(dataDir + "MoveFormField.pdf");
//获取字段
TextBoxField textBoxField = pdfDocument.Form["textbox1"] as TextBoxField;
//修改字段位置
textBoxField.Rect = new Aspose.Pdf.Rectangle(300, 400, 600, 500);
dataDir = dataDir + "MoveFormField_out.pdf";
//保存修改后的文件
pdfDocument.Save(dataDir);
Console.WriteLine("\nForm field moved successfully to a new location.\nFile saved at " + dataDir);
```

## 结论

在本教程中，我们学习了如何使用 Aspose.PDF for .NET 在 PDF 文档中移动表单域。通过执行这些步骤，您可以轻松导航到特定字段并根据需要更改其位置。