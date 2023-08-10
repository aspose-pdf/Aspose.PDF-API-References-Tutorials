---
title: 样式表单元格
linktitle: 样式表单元格
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 设置表格单元格的样式。创建和自定义表格的分步指南。
type: docs
weight: 160
url: /zh/net/programming-with-tagged-pdf/style-table-cell/
---
欢迎阅读有关使用 Aspose.PDF for .NET 设置表格单元格格式的详细教程。在本指南中，我们将详细解释所提供的 C# 源代码的每个步骤，以帮助您了解如何设置表格单元格的样式。在开始之前，请确保您已安装 Aspose.PDF for .NET 并设置您的开发环境。

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
taggedContent.SetTitle("Example of table cell formatting");
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
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
```

我们创建了一个新的数组结构元素并将其添加到根结构元素中。我们还创建了表头、正文和页脚元素。

## 第 5 步：添加表头

在此步骤中，我们将表头添加到表中。

```csharp
//表中的行数和列数
int rowCount = 4;
int colCount = 4;

int rowIndex;
int colIndex;

//创建表标题行
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Header Row";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTHElement theElement = headTrElement.CreateTH();
     theElement.SetText(string.Format("Header {0}", colIndex));
     theElement.BackgroundColor = Color.GreenYellow;
     theElement.Border = new BorderInfo(BorderSide.All, 4.0F, Color.Gray);
     theElement. IsNoBorder = true;
     theElement.Margin = new MarginInfo(16.0, 2.0, 8.0, 2.0);
     theElement.Alignment = HorizontalAlignment.Right;
}
```

我们为表格创建了一个标题行，并添加了具有格式属性（例如背景颜色、边框、边距和对齐方式）的标题单元格。

## 步骤 6：添加表格主体行

现在让我们将表主体行添加到表中。
```csharp
for (rowIndex = 0; rowIndex < rowCount; rowIndex++)
{
     TableTRElement trElement = tableTBodyElement.CreateTR();
     trElement.AlternativeText = string.Format("Row {0}", rowIndex);

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
         tdElement.SetText(string.Format("Cell [{0}, {1}]", rowIndex, colIndex));
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
```

我们使用循环迭代每个表格单元格将行添加到表格主体。我们为每个单元格设置格式属性，例如背景颜色、边框、边距、文本对齐方式等。

## 第7步：添加页脚

最后，我们将表页脚添加到表格中。

```csharp
TableTRElement footTrElement = tableTFootElement.CreateTR();
footTrElement.AlternativeText = "Footline";

for (colIndex = 0; colIndex < colCount; colIndex++)
{
     TableTDElement tdElement = footTrElement.CreateTD();
     tdElement.SetText(string.Format("Foot {0}", colIndex));
}
```

我们为表格创建了页脚，并添加了带有文本的页脚单元格。



## 步骤 8：保存标记的 PDF 文档

现在我们已经使用样式表创建了文档，我们将其另存为带标签的 PDF 文档。

```csharp
//保存标记的 PDF 文档
document.Save(dataDir + "StyleTableCell.pdf");
```

我们将标记的PDF文档保存在指定的目录中。

## 第 9 步：PDF/UA 合规性验证

接下来，我们将验证文档的 PDF/UA 一致性。

```csharp
//PDF/UA 合规性检查
document = new Document(dataDir + "StyleTableCell.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableCell.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(string.Format("PDF/UA Compliance: {0}", isPdfUaCompliance));
```

我们上传了带标签的 PDF 文档，并通过生成 XML 报告来验证其 PDF/UA 合规性。

### 使用 Aspose.PDF for .NET 的样式表单元格示例源代码 
```csharp

//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//创建文档
Document document = new Document();
ITaggedContent taggedContent = document.TaggedContent;
taggedContent.SetTitle("Example table cell style");
taggedContent.SetLanguage("en-US");

//获取根结构元素
StructureElement rootElement = taggedContent.RootElement;

//创建表结构元素
TableElement tableElement = taggedContent.CreateTableElement();
rootElement.AppendChild(tableElement);
TableTHeadElement tableTHeadElement = tableElement.CreateTHead();
TableTBodyElement tableTBodyElement = tableElement.CreateTBody();
TableTFootElement tableTFootElement = tableElement.CreateTFoot();
int rowCount = 4;
int colCount = 4;
int rowIndex;
int colIndex;
TableTRElement headTrElement = tableTHeadElement.CreateTR();
headTrElement.AlternativeText = "Head Row";
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
for (colIndex = 0; colIndex < colCount; colIndex++)
{
	TableTDElement tdElement = footTrElement.CreateTD();
	tdElement.SetText(String.Format("Foot {0}", colIndex));
}

//保存标记的 PDF 文档
document.Save(dataDir + "StyleTableCell.pdf");

//检查 PDF/UA 合规性
document = new Document(dataDir + "StyleTableCell.pdf");
bool isPdfUaCompliance = document.Validate(dataDir + "StyleTableCell.xml", PdfFormat.PDF_UA_1);
Console.WriteLine(String.Format("PDF/UA compliance: {0}", isPdfUaCompliance));

```

## 结论

在本教程中，我们学习了如何使用 Aspose.PDF for .NET 设置表格单元格的样式。我们已经了解了如何创建文档、添加包含标题、正文行和页脚的表格以及自定义单元格样式。最后，我们保存了带标签的 PDF 文档并验证了其 PDF/UA 合规性。您现在可以使用 Aspose.PDF for .NET 在 .NET 应用程序中创建表格并设置表格样式。

### 常见问题解答

#### 问：本教程关于使用 Aspose.PDF for .NET 格式化表格单元格的目的是什么？

答：本教程旨在提供有关如何使用 .NET 的 Aspose.PDF 库设置 PDF 文档中的表格单元格样式的全面指南。它涵盖分步说明和 C# 源代码示例，可帮助您理解和实现表格单元格格式设置。

#### 问：学习本教程的先决条件是什么？

答：开始之前，请确保您已经安装了 Aspose.PDF for .NET 并设置了开发环境。这包括配置您的项目以引用 Aspose.PDF 库。

#### 问：如何使用 Aspose.PDF for .NET 创建新的 PDF 文档？

A：要创建一个新的PDF文档，您需要实例化一个`Document`来自 Aspose.PDF 库的对象。提供的 C# 源代码演示了如何创建文档并设置其标题和语言。

#### 问：PDF 文档中的根结构元素有何意义？

答：根结构元素充当其他结构元素的容器，帮助组织和分类 PDF 文档的内容。它在建立文档的逻辑结构方面起着至关重要的作用。

#### 问：如何使用 Aspose.PDF for .NET 创建表格结构元素并自定义其外观？

答：您可以使用以下命令创建表结构元素`CreateTableElement()`方法。提供的源代码演示了如何通过设置背景颜色、边框、边距和对齐等属性来自定义表格的外观，包括其页眉、正文和页脚。

#### 问：我可以在表体中添加多行和多列并自定义其格式吗？

答：是的，教程演示了如何使用循环向表体添加多行和多列。它还提供了自定义单元格格式的示例，例如背景颜色、边框、文本对齐方式、字体样式等。

#### 问：验证 PDF/UA 合规性的目的是什么？如何执行此验证？

答：验证 PDF/UA 合规性可确保 PDF 文档符合辅助功能标准，从而更方便残障用户使用。本教程展示了如何使用以下方法验证 PDF/UA 一致性`Validate()`方法并生成 XML 报告。

#### 问：如何将这些概念应用到我自己的 .NET 应用程序中？

答：您可以使用提供的 C# 源代码示例作为在您自己的 .NET 应用程序中实现表格单元格格式的指南。根据需要自定义代码以满足您的要求并将其集成到您的项目中。

#### 问：对于 PDF 文档中的表格单元格样式，是否有任何推荐的最佳实践？

答：在设计表格单元格样式时，请考虑受众的需求，包括可访问性要求。使用对比色、适当的字体和清晰的单元格对齐来增强可读性。此外，验证 PDF/UA 合规性以确保满足辅助功能标准。

#### 问：我可以探索 Aspose.PDF for .NET 的哪些其他功能来进行 PDF 文档操作？

答：Aspose.PDF for .NET 提供了广泛的 PDF 文档操作功能，包括文本提取、图像插入、表单字段管理、数字签名等。浏览官方文档和资源以了解其他功能。
