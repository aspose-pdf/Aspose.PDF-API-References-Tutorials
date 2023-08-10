---
title: PDF 文档中的分组复选框
linktitle: PDF 文档中的分组复选框
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 在 PDF 文档中轻松创建分组复选框。
type: docs
weight: 170
url: /zh/net/programming-with-forms/grouped-check-boxes/
---
在本教程中，我们将向您展示如何使用 Aspose.PDF for .NET 在 PDF 文档中创建分组复选框。我们将逐步解释 C# 源代码，以指导您完成此过程。

## 第 1 步：准备

确保您已导入必要的库并设置文档目录的路径：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第 2 步：实例化文档对象

实例化一个 Document 对象：

```csharp
Document pdfDocument = new Document();
```

## 步骤 3：将页面添加到 PDF 文档

向 PDF 文档添加页面：

```csharp
Page page = pdfDocument.Pages.Add();
```

## 第 4 步：实例化 RadioButtonField 对象

使用页码作为参数实例化 RadioButtonField 对象：

```csharp
RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
```

## 第 5 步：添加单选按钮选项

使用 RadioButtonOptionField 对象添加单选按钮选项并使用 Rectangle 对象指定其位置：

```csharp
RadioButtonOptionField opt1 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(0, 0, 20, 20));
RadioButtonOptionField opt2 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(100, 0, 120, 20));
opt1.OptionName = "Test1";
opt2.OptionName = "Test2";
radio.Add(opt1);
radio.Add(opt2);
```

## 第 6 步：自定义单选按钮选项

通过设置单选按钮选项的样式、边框和外观来自定义单选按钮选项：

```csharp
opt1.Style = BoxStyle.Square;
opt2.Style = BoxStyle.Square;
opt1.Border = new Border(opt1);
opt1.Border.Style = BorderStyle.Solid;
opt1.Border.Width = 1;
opt2.Border = new Border(opt2);
opt2.Border.Width = 1;
opt2.Border.Style = BorderStyle.Solid;
```

## 第 7 步：将单选按钮添加到表单中

将单选按钮添加到文档表单对象：

```csharp
pdfDocument.Form.Add(radio);
```

## 步骤 8：保存文档

保存 PDF 文档：

```csharp
dataDir = dataDir + "GroupedCheckBoxes_out.pdf";
pdfDocument.Save(dataDir);
```

### 使用 Aspose.PDF for .NET 的分组复选框的示例源代码 
```csharp
try
{
	//文档目录的路径。
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	//实例化文档对象
	Document pdfDocument = new Document();
	//将页面添加到 PDF 文件
	Page page = pdfDocument.Pages.Add();
	//以页码作为参数实例化 RadioButtonField 对象
	RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
	//添加第一个单选按钮选项，并使用 Rectangle 对象指定其原点
	RadioButtonOptionField opt1 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(0, 0, 20, 20));
	RadioButtonOptionField opt2 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(100, 0, 120, 20));
	opt1.OptionName = "Test1";
	opt2.OptionName = "Test2";
	radio.Add(opt1);
	radio.Add(opt2);
	opt1.Style = BoxStyle.Square;
	opt2.Style = BoxStyle.Square;
	opt1.Style = BoxStyle.Cross;
	opt2.Style = BoxStyle.Cross;
	opt1.Border = new Border(opt1);
	opt1.Border.Style = BorderStyle.Solid;
	opt1.Border.Width = 1;
	opt1.Characteristics.Border = System.Drawing.Color.Black;
	opt2.Border = new Border(opt2);
	opt2.Border.Width = 1;
	opt2.Border.Style = BorderStyle.Solid;
	opt2.Characteristics.Border = System.Drawing.Color.Black;
	//添加单选按钮以形成 Document 对象的对象
	pdfDocument.Form.Add(radio);
	dataDir = dataDir + "GroupedCheckBoxes_out.pdf";
	//保存 PDF 文档
	pdfDocument.Save(dataDir);
	Console.WriteLine("\nGrouped checkboxes added successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## 结论

在本教程中，我们学习了如何使用 Aspose.PDF for .NET 在 PDF 文档中创建分组复选框。通过执行这些步骤，您可以轻松添加自定义单选按钮选项，并使用 Aspose.PDF 将它们捆绑到 PDF 文档中。

### 常见问题解答

#### 问：PDF 文档中的分组复选框是什么？

答：PDF 文档中的分组复选框是指分组在一起的一组单选按钮选项。单选按钮允许用户从一组互斥的选项中仅选择一个选项。当选择一个单选按钮时，同一组中的其他单选按钮将自动取消选择。当您想要向用户提供多个选项但将他们的选择限制为一个选项时，这种分组行为非常有用。

#### 问：我可以在 Aspose.PDF for .NET 中自定义分组复选框的外观吗？

答：是的，您可以在 Aspose.PDF for .NET 中自定义分组复选框的外观。 API 提供了各种选项来设置单选按钮选项的样式、边框和外观。您可以定义每个选项的位置，在不同的框样式（例如，方形、圆形、十字形）之间进行选择，并调整边框属性以获得所需的视觉表示。

#### 问：如何将分组复选框添加到 PDF 文档的特定页面？

答：要将分组复选框添加到 PDF 文档中的特定页面，您需要实例化一个`RadioButtonField`以所需页码作为参数的对象。然后，创建`RadioButtonOptionField`代表每个单选按钮选项的对象并使用`Rectangle`目的。最后，将这些选项添加到`RadioButtonField`并在添加之前根据需要自定义其外观`RadioButtonField`到文件表格。

#### 问：我可以在单个 PDF 文档中添加多组复选框吗？

答：是的，您可以将多组复选框添加到单个 PDF 文档中。每个组都应该有独特的`RadioButtonField`对象，以及`RadioButtonOptionField`每个组中的对象应共享相同的页面和其选项的唯一名称。这可确保每组中的单选按钮正常工作，并且选择是互斥的。

#### 问：所有 PDF 查看器和应用程序都支持分组复选框吗？

答：是的，所有符合标准的 PDF 查看器和应用程序都支持分组复选框。 PDF 规范定义了单选按钮及其分组行为，使它们在 PDF 格式中得到普遍认可。但是，必须在不同的 PDF 查看器中测试功能，以确保跨不同平台的行为一致。