---
title: 创建表元素
linktitle: 创建表元素
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 创建数组元素的分步指南。轻松生成带表格的动态 PDF。
type: docs
weight: 80
url: /zh/net/programming-with-tagged-pdf/create-table-element/
---
在本分步指南中，我们将引导您完成使用 Aspose.PDF for .NET 创建数组元素的过程。 Aspose.PDF 是一个功能强大的库，可让您以编程方式操作 PDF 文档。创建数组元素是生成动态 PDF 时的常见要求，Aspose.PDF 提供了一种简单有效的方法来完成此任务。

让我们深入研究代码并了解如何使用 Aspose.PDF for .NET 创建数组元素。

## 先决条件

在开始之前，请确保您具备以下条件：

1. 安装了适用于.NET 的 Aspose.PDF 库。
2. C# 编程语言的基础知识。

## 第一步：搭建环境

首先，打开 C# 开发环境并创建一个新项目。确保您已在项目中添加对 .NET 的 Aspose.PDF 库的引用。

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第 2 步：创建文档

第一步是使用以下命令创建一个新的 PDF 文档`Document`班级。

```csharp
//创建文档
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example Array");
taggedContent.SetLanguage("fr-FR");
```

在这里我们还设置标记内容的标题和语言。

## 步骤 3：创建数组元素

接下来，我们需要创建数组元素并将其添加到文档中。我们首先获取根结构元素，然后使用以下命令创建一个新的表元素`CreateTableElement`方法。

```csharp
//获取根结构元素
StructureElement rootElement = taggedContent.RootElement;
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
tableElement.Border = new BorderInfo(BorderSide.All, 1.2F, Color.DarkBlue);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 50;
int colCount = 4;
int rowIndex;
int colIndex;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Header Row";
headTrElement.BackgroundColor = Color.LightGray;
for (colIndex = 0; colIndex < colCount; colIndex++)
{
TableTHElement theElement = headTrElement.CreateTH();
thElement.SetText(String.Format("Header {0}", colIndex));
theElement.BackgroundColor = Color.GreenYellow;
theElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
theElement. IsNoBorder = true;
theElement.Margin = new MarginInfo(16.0, 2

.0, 8.0, 2.0);
theElement.Alignment = HorizontalAlignment.Right;
}
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
TableTRElement trElement = tableTBodyElement.CreateTR();
trElement.AlternativeText = String.Format("Row {0}", rowIndex);
for (colIndex = 0; colIndex < colCount; colIndex++)
{
int colSpan = 1;
int rowSpan = 1;
if (colIndex == 1 && rowIndex == 1)
{
colSpan = 2;
rowSpan = 2;
}
else if (colIndex == 2 && (rowIndex == 1 || rowIndex == 2))
{
keep on going;
}
else if (rowIndex == 2 && (colIndex == 1 || colIndex == 2))
{
keep on going;
}
TableTDElement tdelement = trElement.CreateTD();
tdElement.SetText(String.Format("Cell [{0}, {1}]", rowIndex, colIndex));
tdElement.BackgroundColor = Color.Yellow;
tdElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
tdElement.IsNoBorder = false;
tdElement.Margin = new MarginInfo(8.0, 2.0, 8.0, 2.0);
tdElement.Alignment = HorizontalAlignment.Center;
TextState cellTextState = new TextState();
cellTextState.ForegroundColor = Color.DarkBlue;
cellTextState.FontSize = 7.5F;
cellTextState.FontStyle = FontStyles.Bold;
cellTextState.Font = FontRepository.FindFont("Arial");
tdElement. DefaultCellTextState = cellTextState;
tdElement.IsWordWrapped = true;
tdElement.VerticalAlignment = VerticalAlignment.Center;
tdElement.ColSpan = colSpan;
tdElement. RowSpan = rowSpan;
}
}
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Footline";
footTrElement.BackgroundColor = Color.LightSeaGreen;
for (colIndex = 0; colIndex < colCount; colIndex++)
{
TableTDElement tdElement = footTrElement.CreateTD();
tdElement.SetText(String.Format("Foot {0}", colIndex));
tdElement.Alignment = HorizontalAlignment.Center;
tdElement.StructureTextState.FontSize = 7F;
tdElement.StructureTextState.FontStyle = FontStyles.Bold;
}
StructureAttributes tableAttributes = tableElement.Attributes.GetAttributes(AttributeOwnerStandard.Table);
StructureAttribute summaryAttribute = new StructureAttribute(AttributeKey.Summary);
summaryAttribute.SetStringValue("The summary text for the table");
tableAttributes.SetAttribute(summaryAttribute);

//保存标记的 PDF 文档
document.Save(dataDir + "CreateTableElement.pdf");

//PDF/UA 合规性检查
document = new Document(dataDir + "CreateTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "table.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

### 使用 Aspose.PDF for .NET 创建表元素的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//创建文档
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table");
taggedContent.SetLanguage("en-US");

//获取根结构元素
StructureElement rootElement = taggedContent.RootElement;
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
tableElement.Border = new BorderInfo(BorderSide.All, 1.2F, Color.DarkBlue);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 50;
int colCount = 4;
int rowIndex;
int colIndex;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
headTrElement.BackgroundColor = Color.LightGray;
for (colIndex = 0; colIndex < colCount; colIndex++)
{
	TableTHElement thElement = headTrElement.CreateTH();
	thElement.SetText(String.Format("Head {0}", colIndex));
	thElement.BackgroundColor = Color.GreenYellow;
	thElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
	thElement.IsNoBorder = true;
	thElement.Margin = new MarginInfo(16.0, 2.0, 8.0, 2.0);
	thElement.Alignment = HorizontalAlignment.Right;
}
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
	TableTRElement trElement = tableTBodyElement.CreateTR();
	trElement.AlternativeText = String.Format("Row {0}", rowIndex);
	for (colIndex = 0; colIndex < colCount; colIndex++)
	{
		int colSpan = 1;
		int rowSpan = 1;
		if (colIndex == 1 && rowIndex == 1)
		{
			colSpan = 2;
			rowSpan = 2;
		}
		else if (colIndex == 2 && (rowIndex == 1 || rowIndex == 2))
		{
			continue;
		}
		else if (rowIndex == 2 && (colIndex == 1 || colIndex == 2))
		{
			continue;
		}
		TableTDElement tdElement = trElement.CreateTD();
		tdElement.SetText(String.Format("Cell [{0}, {1}]", rowIndex, colIndex));
		tdElement.BackgroundColor = Color.Yellow;
		tdElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
		tdElement.IsNoBorder = false;
		tdElement.Margin = new MarginInfo(8.0, 2.0, 8.0, 2.0);
		tdElement.Alignment = HorizontalAlignment.Center;
		TextState cellTextState = new TextState();
		cellTextState.ForegroundColor = Color.DarkBlue;
		cellTextState.FontSize = 7.5F;
		cellTextState.FontStyle = FontStyles.Bold;
		cellTextState.Font = FontRepository.FindFont("Arial");
		tdElement.DefaultCellTextState = cellTextState;
		tdElement.IsWordWrapped = true;
		tdElement.VerticalAlignment = VerticalAlignment.Center;
		tdElement.ColSpan = colSpan;
		tdElement.RowSpan = rowSpan;
	}
}
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Foot Row";
footTrElement.BackgroundColor = Color.LightSeaGreen;
for (colIndex = 0; colIndex < colCount; colIndex++)
{
	TableTDElement tdElement = footTrElement.CreateTD();
	tdElement.SetText(String.Format("Foot {0}", colIndex));
	tdElement.Alignment = HorizontalAlignment.Center;
	tdElement.StructureTextState.FontSize = 7F;
	tdElement.StructureTextState.FontStyle = FontStyles.Bold;
}
StructureAttributes tableAttributes = tableElement.Attributes.GetAttributes(AttributeOwnerStandard.Table);
StructureAttribute summaryAttribute = new StructureAttribute(AttributeKey.Summary);
summaryAttribute.SetStringValue("The summary text for table");
tableAttributes.SetAttribute(summaryAttribute);

//保存标记的 PDF 文档
document.Save(dataDir + "CreateTableElement.pdf");

//检查 PDF/UA 合规性
document = new Document(dataDir + "CreateTableElement.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "table.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## 结论

您已经学习了如何使用 Aspose.PDF for .NET 创建数组元素。您现在可以使用此方法生成带有动态表格的 PDF 文档。请随意探索 Aspose.PDF 的更多功能，以发现其全部潜力。

### 常见问题解答

#### 问：什么是 PDF 文档中的数组元素？为什么我需要使用 Aspose.PDF for .NET 创建一个数组元素？

答：PDF 文档中的数组元素表示结构化数据集合，通常用于创建表格或网格。在生成需要结构化数据呈现（例如表格信息或网格）的动态 PDF 时，您可能需要使用 Aspose.PDF for .NET 创建数组元素。

#### 问：Aspose.PDF for .NET 如何简化创建数组元素的过程？

答：Aspose.PDF for .NET 提供了一套全面的类和方法，允许您以编程方式创建、自定义和管理 PDF 文档中的数组元素（表）。这消除了手动 PDF 操作的需要，并简化了结构化数据表示的创建。

#### 问：使用 Aspose.PDF for .NET 创建数组元素涉及哪些关键步骤？

答：关键步骤包括设置环境、创建文档、获取根结构元素、创建表格元素、定义表格内的行和单元格以及指定元素的格式和属性。提供的代码示例演示了这些步骤。

#### 问： 有何作用`taggedContent` object play in creating an array element?

答： 的`taggedContent`对象，从文档中获取`TaggedContent`属性，允许您定义 PDF 文档中标记内容的结构。这包括以分层方式创建和组织数组元素及其子元素。

#### 问：代码如何确保创建的数组元素的可访问性和语义？

 A：代码设置属性，例如`AlternativeText`, `BackgroundColor`, `Border`, `Margin`, `Alignment`， 和`ColSpan`增强数组元素的可访问性和语义。这些属性有助于形成结构良好、信息丰富且具有视觉吸引力的数据表示。

#### 问：在创建数组元素时，PDF/UA 合规性有何意义？

答：PDF/UA（通用辅助功能）合规性可确保生成的 PDF 文档可供残障用户访问，并满足某些辅助功能标准。该代码示例使用以下命令检查 PDF/UA 合规性`Validate`方法，帮助您创建包容且易于访问的文档。

#### 问：我可以进一步自定义数组元素的格式和外观吗？

答：是的，您可以通过调整背景颜色、边框样式、字体大小和对齐方式等属性来自定义数组元素的格式和外观。 Aspose.PDF for .NET 提供了广泛的属性来根据您的要求定制视觉呈现。

#### 问：如何扩展这些知识来创建更复杂的表格结构或将数组元素合并到更大的 PDF 文档中？

答：您可以通过探索 Aspose.PDF for .NET 的其他功能来扩展这些知识，例如合并多个数组元素、创建嵌套表格、添加页眉和页脚以及将数组元素集成到更大的 PDF 布局中。该库的文档和示例为这些高级场景提供了指导。

#### 问：是否可以从外部源（例如数据库或电子表格）导入数据来填充数组元素？

答：是的，您可以从外部源导入数据来填充数组元素。您可以使用 C# 中的数据检索和转换技术从数据库、电子表格或其他源获取数据，然后相应地填充数组元素。

#### 问：如何利用从本教程中获得的知识来提高以编程方式创建的 PDF 文档的质量和可用性？

答：从本教程中获得的知识使您能够在 PDF 文档中创建结构化且具有视觉吸引力的数组元素（表格）。通过结合这些技术，您可以提高动态生成的 PDF 的可读性、可访问性和用户体验，使其信息更丰富且用户友好。