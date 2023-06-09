---
title: 文本框
linktitle: 文本框
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 文档中创建文本字段。
type: docs
weight: 290
url: /zh/net/programming-with-forms/text-box/
---

在本指南中，我们将逐步解释如何使用 Aspose.PDF .NET 库在 PDF 文档中创建文本字段。我们将向您展示如何打开文档、创建文本字段、自定义其属性以及保存编辑后的 PDF。

## 第一步：配置文档目录

第一步是配置要处理的 PDF 文件所在的文档目录。您可以使用`dataDir`变量指定目录路径。

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

务必更换`"YOUR DOCUMENTS DIRECTORY"`使用文档目录的实际路径。

## 第 2 步：打开 PDF 文档

在此步骤中，我们将使用`Document`Aspose.PDF 类。

```csharp
Document pdfDocument = new Document(dataDir + "TextField.pdf");
```

确保 PDF 文件存在于指定的文档目录中。

## 第 3 步：创建文本字段

我们将使用`TextBoxField`班级。您可以使用`Rectangle`班级。

```csharp
TextBoxField textBoxField = new TextBoxField(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(100, 200, 300, 300));
textBoxField. PartialName = "textbox1";
textBoxField.Value = "Text Field";
```

根据需要自定义坐标、大小、部分名称和文本字段值。

## 第 4 步：自定义文本字段属性

在此步骤中，我们将自定义文本字段属性，例如边框、颜色等。

```csharp
Border border = new Border(textBoxField);
border. width = 5;
border. Dash = new Dash(1, 1);
textBoxField. Border = border;
textBoxField.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
```

根据您的喜好自定义文本字段属性。

## 第 5 步：将字段添加到文档

现在我们已经创建并配置了文本字段，我们可以将它添加到 PDF 文档中。

```csharp
pdfDocument.Form.Add(textBoxField, 1);
```

## 第 6 步：保存修改后的 PDF

最后，我们可以使用`Save`的方法`Document`班级。

```csharp
dataDir = dataDir + "TextBox_out.pdf";
pdfDocument.Save(dataDir);
```

请务必指定已编辑 PDF 的完整路径和文件名。

### 使用 Aspose.PDF for .NET 的文本框示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//打开文档
Document pdfDocument = new Document(dataDir + "TextField.pdf");
//创建字段
TextBoxField textBoxField = new TextBoxField(pdfDocument.Pages[1], new Aspose.Pdf.Rectangle(100, 200, 300, 300));
textBoxField.PartialName = "textbox1";
textBoxField.Value = "Text Box";
//TextBoxField.Border = 新边框(
Border border = new Border(textBoxField);
border.Width = 5;
border.Dash = new Dash(1, 1);
textBoxField.Border = border;
textBoxField.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
//向文档添加字段
pdfDocument.Form.Add(textBoxField, 1);
dataDir = dataDir + "TextBox_out.pdf";
//保存修改后的 PDF
pdfDocument.Save(dataDir);
Console.WriteLine("\nTextbox field added successfully.\nFile saved at " + dataDir);
```

## 结论

在本指南中，我们学习了如何使用 .NET 的 Aspose.PDF 库在 PDF 文档中创建文本字段。按照描述的步骤，您可以自定义文本字段的属性，并根据需要将其添加到文档中。欢迎进一步探索 Aspose.PDF for .NET 的功能，以扩展操作 PDF 文件的可能性。