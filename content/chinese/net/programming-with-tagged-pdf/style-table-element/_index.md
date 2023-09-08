---
title: 样式表元素
linktitle: 样式表元素
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 设置表格元素的格式。自定义样式和属性的分步指南。
type: docs
weight: 170
url: /zh/net/programming-with-tagged-pdf/style-table-element/
---
在这个详细的教程中，我们将引导您逐步完成所提供的 C# 源代码，以使用 Aspose.PDF for .NET 格式化数组元素。请按照以下说明了解如何自定义数组元素的样式和属性。

## 第一步：搭建环境

在开始之前，请确保您已将开发环境配置为使用 Aspose.PDF for .NET。这包括安装 Aspose.PDF 库并配置您的项目以引用它。

## 第 2 步：创建文档

在这一步中，我们将创建一个新的文档对象Aspose.PDF。

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//文档创建
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example of table formatting");
taggedContent.SetLanguage("fr-FR");
```

我们创建了一个新文档并设置了文档标题和语言。

## 第三步：获取根结构元素

在此步骤中，我们将获取文档的根结构元素。

```csharp
//获取根结构元素
StructureElement rootElement = taggedContent.RootElement;
```

我们得到了根结构元素，它将用作数组元素的容器。

## 第四步：创建数组结构元素

现在让我们为文档创建一个新的表结构元素。

```csharp
//创建数组结构元素
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
```

我们创建了一个新的数组结构元素并将其添加到根结构元素中。

## 第 5 步：自定义数组元素样式和属性

在此步骤中，我们将自定义数组元素的样式和属性。

```csharp
//自定义数组元素的样式和属性
tableElement.BackgroundColor = Color.Beige;
tableElement.Border = new BorderInfo(BorderSide.All, 0.80F, Color.Gray);
tableElement. Alignment = HorizontalAlignment. Center;
tableElement.Broken = TableBroken.Vertical;
tableElement.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;
tableElement. ColumnWidths = "80 80 80 80 80";
tableElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.DarkBlue);
tableElement. DefaultCellPadding = new MarginInfo(16.0, 2.0, 8.0, 2.0);
tableElement.DefaultCellTextState.ForegroundColor = Color.DarkCyan;
tableElement.DefaultCellTextState.FontSize = 8F;
tableElement. DefaultColumnWidth = "70";
tableElement. IsBroken = false;
tableElement.IsBordersIncluded = true;
tableElement. Left = 0F;
tableElement. Top = 40F;
tableElement.RepeatingColumnsCount = 2;
tableElement.RepeatingRowsCount = 3;

//自定义重复线的样式
TextState rowStyle = new TextState();
rowStyle.BackgroundColor = Color.LightCoral;
tableElement.RepeatingRowsStyle = rowStyle;
```

我们使用各种属性来自定义表格元素，例如背景颜色、边框、对齐方式、默认单元格样式、边距、列宽等。

## 第 6 步：添加表头、正文和页脚

现在让我们将表头、正文和页脚添加到表元素中。
```csharp
//添加表格标题
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();

//表中的行数和列数
int rowCount = 10;
int colCount = 5;
int rowIndex;
int colIndex;

//创建表标题行
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Header Row";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTHElement theElement = headTrElement.CreateTH();
     theElement.SetText(string.Format("Header {0}", colIndex));
}

//添加表体的行
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
     TableTRElement trElement = tableTBodyElement.CreateTR();
     trElement.AlternativeText = string.Format("Row {0}", rowIndex);

     for (colIndex = 0; colIndex < colCount; colIndex++)
     {
         TableTDElement tdelement = trElement.CreateTD();
         tdElement.SetText(string.Format("Cell [{0}, {1}]", rowIndex, colIndex));
     }
}

//添加表格的底脚线
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Footline";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTDElement tdElement = footTrElement.CreateTD();
     tdElement.SetText(string.Format("Foot {0}", colIndex));
}
```

我们使用相应的元素将标题行、正文行和页脚行添加到表中。

## 步骤 7：保存标记的 PDF 文档

现在我们已经使用样式表元素创建了文档，我们将其保存为带标签的 PDF 文档。

```csharp
//保存标记的 PDF 文档
document.Save(dataDir + "StyleTableElement.pdf");
```

我们将标记的PDF文档保存在指定的目录中。

## 第 8 步：PDF/UA 合规性验证

接下来，我们将验证文档的 PDF/UA 一致性。

```csharp
//PDF/UA 合规性检查
document = new Document(dataDir + "StyleTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableElement.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(string.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

我们上传了带标签的 PDF 文档，并通过生成 XML 报告来验证其 PDF/UA 合规性。

### 使用 Aspose.PDF for .NET 的样式表元素示例源代码 

```csharp

//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//创建文档
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table style");
taggedContent.SetLanguage("en-US");

//获取根结构元素
StructureElement rootElement = taggedContent.RootElement;

//创建表结构元素
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
tableElement.BackgroundColor = Color.Beige;
tableElement.Border = new BorderInfo(BorderSide.All, 0.80F, Color.Gray);
tableElement.Alignment = HorizontalAlignment.Center;
tableElement.Broken = TableBroken.Vertical;
tableElement.ColumnAdjustment = ColumnAdjustment.AutoFitToWindow;
tableElement.ColumnWidths = "80 80 80 80 80";
tableElement.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.50F, Color.DarkBlue);
tableElement.DefaultCellPadding = new MarginInfo(16.0, 2.0, 8.0, 2.0);
tableElement.DefaultCellTextState.ForegroundColor = Color.DarkCyan;
tableElement.DefaultCellTextState.FontSize = 8F;
tableElement.DefaultColumnWidth = "70";
tableElement.IsBroken = false;
tableElement.IsBordersIncluded = true;
tableElement.Left = 0F;
tableElement.Top = 40F;
tableElement.RepeatingColumnsCount = 2;
tableElement.RepeatingRowsCount = 3;
TextState rowStyle = new TextState();
rowStyle.BackgroundColor = Color.LightCoral;
tableElement.RepeatingRowsStyle = rowStyle;
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 10;
int colCount = 5;
int rowIndex;
int colIndex;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
for (colIndex = 0; colIndex < colCount; colIndex++)
{
	TableTHElement thElement = headTrElement.CreateTH();
	thElement.SetText(String.Format("Head {0}", colIndex));
}
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
	TableTRElement trElement = tableTBodyElement.CreateTR();
	trElement.AlternativeText = String.Format("Row {0}", rowIndex);
	for (colIndex = 0; colIndex < colCount; colIndex++)
	{
		TableTDElement tdElement = trElement.CreateTD();
		tdElement.SetText(String.Format("Cell [{0}, {1}]", rowIndex, colIndex));
	}
}
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Foot Row";
for (colIndex = 0; colIndex < colCount; colIndex++)
{
	TableTDElement tdElement = footTrElement.CreateTD();
	tdElement.SetText(String.Format("Foot {0}", colIndex));
}

//保存标记的 PDF 文档
document.Save(dataDir + "StyleTableElement.pdf");

//检查 PDF/UA 合规性
document = new Document(dataDir + "StyleTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableElement.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## 结论

在本教程中，我们学习了如何使用 Aspose.PDF for .NET 格式化数组元素。我们定制了表格元素的样式和属性，添加了页眉、正文行和页脚，保存了标记的 PDF 文档，并验证了其 PDF/UA 合规性。

### 常见问题解答

#### 问：本教程使用 Aspose.PDF for .NET 格式化数组元素的目的是什么？

答：本教程的目标是指导您完成使用 Aspose.PDF for .NET 在 PDF 文档中格式化数组元素的过程。它提供分步说明和 C# 源代码示例，帮助您自定义数组元素的样式和属性。

#### 问：学习本教程的先决条件是什么？

答：开始之前，请确保您已设置开发环境以使用 Aspose.PDF for .NET。这涉及安装 Aspose.PDF 库并配置您的项目以引用它。

#### 问：如何使用 Aspose.PDF for .NET 创建新的 PDF 文档并设置其标题和语言？

答：要创建一个新的 PDF 文档，您需要创建一个`Document`来自 Aspose.PDF 库的对象。本教程提供的 C# 源代码演示了如何创建文档并设置其标题和语言属性。

#### 问：PDF 文档中的根结构元素有何意义？

答：根结构元素充当其他结构元素的容器，有助于组织和分类 PDF 文档的内容。它在建立文档的逻辑结构方面起着至关重要的作用。

#### 问：如何使用 Aspose.PDF for .NET 创建和自定义数组结构元素？

答：您可以使用以下命令创建数组结构元素`CreateTableElement()`方法。本教程的源代码提供了自定义表格元素的各种属性的示例，例如背景颜色、边框、对齐方式、列宽度等。

#### 问：我可以自定义数组元素中表格单元格的样式和属性吗？

答：是的，教程涵盖了如何自定义整个表格元素的样式和属性，包括页眉、正文行和页脚。但是，它并没有专门解决自定义单个表格单元格的问题。

#### 问：如何向表格元素添加页眉、正文行和页脚？

答：本教程介绍了如何使用 Aspose.PDF for .NET 提供的适当方法创建页眉、正文行和页脚并将其添加到表格元素。

#### 问：什么是 PDF/UA 合规性？如何验证我的已标记 PDF 文档的合规性？

答：PDF/UA 合规性可确保 PDF 文档符合辅助功能标准，从而更方便残障用户使用。本教程演示了如何使用以下方法验证 PDF/UA 一致性`Validate()`方法并生成 XML 合规性报告。

#### 问：如何将这些概念融入到我自己的 .NET 应用程序中？

答：您可以使用提供的 C# 源代码示例作为在您自己的 .NET 应用程序中实现数组元素格式设置的指南。修改和调整代码以满足您的要求并将其集成到您的项目中。

#### 问：对于格式化 PDF 文档中的数组元素，是否有任何推荐的最佳实践？

A：在格式化数组元素（表格）时，要考虑内容的可读性和可访问性。使用清晰易读的字体、适当的颜色并保持一致的布局。验证 PDF/UA 合规性以确保满足辅助功能标准。

#### 问：我可以探索 Aspose.PDF for .NET 的哪些其他功能来自定义 PDF 文档？

答：Aspose.PDF for .NET 提供了一系列用于 PDF 文档自定义的功能，包括文本操作、图像插入、表单字段管理、数字签名、注释等。请查阅官方文档和资源以探索其他功能。