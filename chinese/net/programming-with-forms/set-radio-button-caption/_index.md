---
title: 设置单选按钮标题
linktitle: 设置单选按钮标题
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 为 PDF 表单中的单选按钮设置标题。
type: docs
weight: 280
url: /zh/net/programming-with-forms/set-radio-button-caption/
---

在本指南中，我们将逐步解释如何使用 .NET 的 Aspose.PDF 库来定义 PDF 表单中单选按钮的标题。我们将向您展示如何访问单选按钮字段、创建新的单选按钮选项以及自定义按钮标题。

## 第一步：配置文档目录

第一步是配置要处理的 PDF 表单所在的文档目录。您可以使用`dataDir`变量指定目录路径。

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

务必更换`"YOUR DOCUMENTS DIRECTORY"`使用文档目录的实际路径。

## 第 2 步：加载源 PDF 表单

在此步骤中，我们将使用`Aspose.Pdf.Facades.Form`Aspose.PDF 类。

```csharp
Aspose.Pdf.Facades.Form form1 = new Aspose.Pdf.Facades.Form(dataDir + "RadioButtonField.pdf");
```

确保包含表单的 PDF 文件存在于指定的文档目录中。

## 第 3 步：编辑单选按钮标题

我们将遍历表单字段名称并搜索单选按钮字段。如果找到匹配的字段，我们将创建一个带有自定义标题的新单选按钮选项，并将其添加到现有字段中。

```csharp
foreach(var item in form1.FieldNames)
{
if (item.Contains("radio1"))
{
Aspose.Pdf.Forms.RadioButtonField field0 = PDF_Template_PDF_HTML.Form[item] as Aspose.Pdf.Forms.RadioButtonField;
Aspose.Pdf.Forms.RadioButtonOptionField fieldoption = new Aspose.Pdf.Forms.RadioButtonOptionField();
fieldoption.OptionName = "Yes";
fieldoption.PartialName = "Yesname";
var updatedFragment = new Aspose.Pdf.Text.TextFragment("test123");
updatedFragment.TextState.Font = FontRepository.FindFont("Arial");
updatedFragment.TextState.FontSize = 10;
updatedFragment.TextState.LineSpacing = 6.32f;
//创建一个 TextParagraph 对象
TextParagraph par = new TextParagraph();
//设置段落位置
par.Position = new Position(field0.Rect.LLX, field0.Rect.LLY + updatedFragment.TextState.FontSize);
//指定自动换行模式
by.FormattingOptions.WrapMode = TextFormattingOptions.WordWrapMode.ByWords;
//将新的 TextFragment 添加到段落中
par.AppendLine(updatedFragment);
//使用 TextBuilder 添加 TextParagraph
TextBuilder textBuilder = new TextBuilder(PDF_Template_PDF_HTML.Pages[1]);
textBuilder.AppendParagraph(par);
field0.DeleteOption("item1");
}
}
```

根据需要自定义标题单选按钮和其他设置。

## 第 4 步：保存生成的 PDF

现在我们已经完成了单选按钮标题的修改，我们可以使用`Save`的方法`Document`班级。

```csharp
PDF_Template_PDF_HTML.Save(dataDir + "RadioButtonField_out.pdf");
```

请务必指定生成的 PDF 的完整路径和文件名。

### 使用 Aspose.Words for .NET 设置单选按钮标题的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//加载源 PDF 表单
Aspose.Pdf.Facades.Form form1 = new Aspose.Pdf.Facades.Form(dataDir + "RadioButtonField.pdf");
Document PDF_Template_PDF_HTML = new Document(dataDir + "RadioButtonField.pdf");
foreach (var item in form1.FieldNames)
{
	Console.WriteLine(item.ToString());
	Dictionary<string, string> radioOptions = form1.GetButtonOptionValues(item);
	if (item.Contains("radio1"))
	{
		Aspose.Pdf.Forms.RadioButtonField field0 = PDF_Template_PDF_HTML.Form[item] as Aspose.Pdf.Forms.RadioButtonField;
		Aspose.Pdf.Forms.RadioButtonOptionField fieldoption = new Aspose.Pdf.Forms.RadioButtonOptionField();
		fieldoption.OptionName = "Yes";
		fieldoption.PartialName = "Yesname";
		var updatedFragment = new Aspose.Pdf.Text.TextFragment("test123");
		updatedFragment.TextState.Font = FontRepository.FindFont("Arial");
		updatedFragment.TextState.FontSize = 10;
		updatedFragment.TextState.LineSpacing = 6.32f;
		//创建 TextParagraph 对象
		TextParagraph par = new TextParagraph();
		//设置段落位置
		par.Position = new Position(field0.Rect.LLX, field0.Rect.LLY + updatedFragment.TextState.FontSize);
		//指定自动换行模式
		par.FormattingOptions.WrapMode = TextFormattingOptions.WordWrapMode.ByWords;
		//向段落添加新的 TextFragment
		par.AppendLine(updatedFragment);
		//使用 TextBuilder 添加 TextParagraph
		TextBuilder textBuilder = new TextBuilder(PDF_Template_PDF_HTML.Pages[1]);
		textBuilder.AppendParagraph(par);
		field0.DeleteOption("item1");
	}
}
PDF_Template_PDF_HTML.Save(dataDir + "RadioButtonField_out.pdf");
```

## 结论

在本指南中，我们学习了如何使用 .NET 的 Aspose.PDF 库为 PDF 表单中的单选按钮设置标题。按照描述的步骤，您可以自定义单选按钮选项并根据需要更改标题。欢迎进一步探索 Aspose.PDF for .NET 的功能，以扩展操作 PDF 文件的可能性。