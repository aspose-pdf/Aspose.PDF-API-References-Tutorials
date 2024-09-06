---
title: 页眉页脚中的可替换符号
linktitle: 页眉页脚中的可替换符号
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 文档的页眉和页脚中使用可替换符号。
type: docs
weight: 320
url: /zh/net/programming-with-text/replaceable-symbols-in-header-footer/
---
在本教程中，我们将解释如何使用 .NET 的 Aspose.PDF 库在 PDF 文档的页眉和页脚中使用可替换符号。我们将逐步介绍创建 PDF、设置边距、添加带有可替换符号的页眉和页脚以及使用提供的 C# 源代码保存 PDF 的过程。

## 先决条件

开始之前，请确保您已准备好以下物品：

- 已安装 Aspose.PDF for .NET 库。
- 对 C# 编程有基本的了解。

## 步骤 1：设置文档目录

首先，您需要设置要保存生成的 PDF 文件的目录路径。替换`"YOUR DOCUMENT DIRECTORY"`在`dataDir`变量为您所需目录的路径。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 步骤 2：创建 PDF 文档和页面

接下来，我们创建一个新的 PDF 文档，并使用`Document`类和`Page`Aspose.PDF 库中的类。

```csharp
Document doc = new Document();
Page page = doc.Pages.Add();
```

## 步骤 3：设置边距

我们使用`MarginInfo`类。根据您的要求调整边距值。

```csharp
MarginInfo marginInfo = new MarginInfo();
marginInfo.Top = 90;
marginInfo.Bottom = 50;
marginInfo.Left = 50;
marginInfo.Right = 50;
page.PageInfo.Margin = marginInfo;
```

## 步骤 4：添加带有可替换符号的标题

我们创建`HeaderFooter`页面的对象并添加一个`TextFragment`带有可替换的符号。

```csharp
HeaderFooter hfFirst = new HeaderFooter();
page.Header = hfFirst;
hfFirst.Margin.Left = 50;
hfFirst.Margin.Right = 50;

TextFragment t1 = new TextFragment("report title");
//如果需要，设置文本属性
t1.TextState.Font = FontRepository.FindFont("Arial");
t1.TextState.FontSize = 16;
t1.TextState.ForegroundColor = Aspose.Pdf.Color.Black;
t1.TextState.FontStyle = FontStyles.Bold;
t1.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
t1.TextState.LineSpacing = 5f;

hfFirst.Paragraphs.Add(t1);

//添加更多 TextFragments 或根据需要自定义
```

## 步骤 5：添加带有可替换符号的页脚

类似地，我们创建一个`HeaderFooter`页脚对象并添加`TextFragment`具有可替换符号的对象。

```csharp
HeaderFooter hfFoot = new HeaderFooter();
page.Footer = hfFoot;
hfFoot.Margin.Left = 50;
hfFoot.Margin.Right = 50;

TextFragment t3 = new TextFragment("Generated on test date");
TextFragment t4 = new TextFragment("report name ");
TextFragment t5 = new TextFragment("Page $p of $P");

//添加更多 TextFragments 或根据需要自定义

hfFoot.Paragraphs.Add(tab2);
```

## 步骤 6：保存 PDF 文档

最后，我们将PDF文档保存到指定的输出文件。

```csharp
dataDir = dataDir + "ReplaceableSymbolsInHeaderFooter_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nReplaceable symbols replaced successfully in the header and footer.\nFile saved at " + dataDir);
```

### 使用 Aspose.PDF for .NET 的页眉页脚中可替换符号的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
Page page = doc.Pages.Add();
MarginInfo marginInfo = new MarginInfo();
marginInfo.Top = 90;
marginInfo.Bottom = 50;
marginInfo.Left = 50;
marginInfo.Right = 50;
//将 marginInfo 实例分配给 sec1.PageInfo 的 Margin 属性
page.PageInfo.Margin = marginInfo;
HeaderFooter hfFirst = new HeaderFooter();
page.Header = hfFirst;
hfFirst.Margin.Left = 50;
hfFirst.Margin.Right = 50;
//实例化一个文本段落，用于存储要显示为标题的内容
TextFragment t1 = new TextFragment("report title");
t1.TextState.Font = FontRepository.FindFont("Arial");
t1.TextState.FontSize = 16;
t1.TextState.ForegroundColor = Aspose.Pdf.Color.Black;
t1.TextState.FontStyle = FontStyles.Bold;
t1.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
t1.TextState.LineSpacing = 5f;
hfFirst.Paragraphs.Add(t1);
TextFragment t2 = new TextFragment("Report_Name");
t2.TextState.Font = FontRepository.FindFont("Arial");
t2.TextState.ForegroundColor = Aspose.Pdf.Color.Black;
t2.TextState.HorizontalAlignment = Aspose.Pdf.HorizontalAlignment.Center;
t2.TextState.LineSpacing = 5f;
t2.TextState.FontSize = 12;
hfFirst.Paragraphs.Add(t2);
//为该部分创建 HeaderFooter 对象
HeaderFooter hfFoot = new HeaderFooter();
//将 HeaderFooter 对象设置为奇数和偶数页脚
page.Footer = hfFoot;
hfFoot.Margin.Left = 50;
hfFoot.Margin.Right = 50;
//添加包含当前页码和总页数的文本段落
TextFragment t3 = new TextFragment("Generated on test date");
TextFragment t4 = new TextFragment("report name ");
TextFragment t5 = new TextFragment("Page $p of $P");
//实例化表对象
Table tab2 = new Table();
//在所需部分的段落集合中添加表格
hfFoot.Paragraphs.Add(tab2);
//设置表格的列宽
tab2.ColumnWidths = "165 172 165";
//在表格中创建行，然后在行中创建单元格
Row row3 = tab2.Rows.Add();
row3.Cells.Add();
row3.Cells.Add();
row3.Cells.Add();
//将文本的垂直对齐方式设置为居中对齐
row3.Cells[0].Alignment = Aspose.Pdf.HorizontalAlignment.Left;
row3.Cells[1].Alignment = Aspose.Pdf.HorizontalAlignment.Center;
row3.Cells[2].Alignment = Aspose.Pdf.HorizontalAlignment.Right;
row3.Cells[0].Paragraphs.Add(t3);
row3.Cells[1].Paragraphs.Add(t4);
row3.Cells[2].Paragraphs.Add(t5);
//Sec1.Paragraphs.Add(New Text("Aspose.Total for Java 是 Aspose 提供的每个 Java 组件的汇编。它每天编译一次，以确保它包含我们每个 Java 组件的最新版本。#$NL " + "使用 Aspose.Total for Java 开发人员可以创建各种应用程序。#$NL #$NL #$NP" + "Aspose.Total for Java 是 Aspose 提供的每个 Java 组件的汇编。它每天编译一次，以确保它包含我们每个 Java 组件的最新版本。#$NL " + "使用 Aspose.Total for Java 开发人员可以创建各种应用程序。#$NL #$NL #$NP" + "Aspose.Total for Java 是 Aspose 提供的每个 Java 组件的汇编。它每天编译一次，以确保它包含我们每个 Java 组件的最新版本。#$NL " + “使用 Aspose.Total 为 Java 开发人员可以创建各种各样的应用程序。#$NL #$NL”））
Table table = new Table();
table.ColumnWidths = "33% 33% 34%";
table.DefaultCellPadding = new MarginInfo();
table.DefaultCellPadding.Top = 10;
table.DefaultCellPadding.Bottom = 10;
//在所需部分的段落集合中添加表格
page.Paragraphs.Add(table);
//使用 BorderInfo 对象设置默认单元格边框
table.DefaultCellBorder = new BorderInfo(BorderSide.All, 0.1f);
//使用另一个自定义的 BorderInfo 对象设置表格边框
table.Border = new BorderInfo(BorderSide.All, 1f);
table.RepeatingRowsCount = 1;
//在表格中创建行，然后在行中创建单元格
Row row1 = table.Rows.Add();
row1.Cells.Add("col1");
row1.Cells.Add("col2");
row1.Cells.Add("col3");
const string CRLF = "\r\n";
for (int i = 0; i <= 10; i++)
{
	Row row = table.Rows.Add();
	row.IsRowBroken = true;
	for (int c = 0; c <= 2; c++)
	{
		Cell c1;
		if (c == 2)
			c1 = row.Cells.Add("Aspose.Total for Java is a compilation of every Java component offered by Aspose. It is compiled on a" + CRLF + "daily basis to ensure it contains the most up to date versions of each of our Java components. " + CRLF + "daily basis to ensure it contains the most up to date versions of each of our Java components. " + CRLF + "Using Aspose.Total for Java developers can create a wide range of applications.");
		else
			c1 = row.Cells.Add("item1" + c);
		c1.Margin = new MarginInfo();
		c1.Margin.Left = 30;
		c1.Margin.Top = 10;
		c1.Margin.Bottom = 10;
	}
}
dataDir = dataDir + "ReplaceableSymbolsInHeaderFooter_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nSymbols replaced successfully in header and footer.\nFile saved at " + dataDir);
```

## 结论

在本教程中，您学习了如何使用 .NET 的 Aspose.PDF 库在 PDF 文档的页眉和页脚中使用可替换符号。通过遵循分步指南并执行提供的 C# 代码，您可以创建 PDF、设置边距、添加带有可替换符号的页眉和页脚，并保存 PDF。

### 常见问题解答

#### 问：《页眉页脚中的可替换符号》教程的目的是什么？

答：“页眉页脚中的可替换符号”教程旨在指导您完成使用 .NET 的 Aspose.PDF 库向 PDF 文档的页眉和页脚添加可替换符号的过程。可替换符号允许您在生成 PDF 时动态地用实际值替换特定占位符。

#### 问：PDF 页眉和页脚中的可替换符号是什么？

答：可替换符号是可以插入 PDF 文档页眉和页脚的占位符。这些符号可用作可在运行时填写的值的动态占位符，例如页码、日期和自定义信息。

#### 问：为什么我要在 PDF 页眉和页脚中使用可替换符号？

答：当您想要在 PDF 文档中包含动态信息（例如页码、日期或在生成文档时可能会发生变化的其他变量数据）时，页眉和页脚中的可替换符号很有用。

#### 问：如何设置 PDF 页面的页边距？

答：您可以使用`MarginInfo`并将其分配给`Margin`的财产`PageInfo`页面的边距。根据需要调整边距值。

#### 问：如何在页眉和页脚中添加可替换的符号？

答：您可以通过创建`HeaderFooter`对象作为页面的页眉和页脚。然后，您可以添加`TextFragment`带有所需文本（包括可替换符号）的对象`Paragraphs`收集`HeaderFooter`目的。

#### 问：我可以自定义可替换符号的外观吗？

答：是的，您可以通过修改可替换符号的属性来自定义可替换符号的外观。`TextFragment`包含符号的对象。您可以设置字体、字体大小、颜色、对齐方式和行距等属性。

#### 问：我可以使用哪种可替换符号？

答：您可以使用多种可替换的符号，例如：

- `$p`：当前页码。
- `$P`：总页数。
- `$d`：当前日期。
- `$t`：当前时间。
- 您定义的自定义占位符。

#### 问：我可以在可替换符号周围添加其他文本和格式吗？

答：是的，您可以在可替换符号周围添加其他文本和格式`TextFragment`对象。这允许您创建包含动态和静态内容的更复杂的页眉和页脚。

#### 问：如何保存生成的PDF文档？

答：要保存生成的 PDF 文档，您可以使用`Save`方法`Document`类。提供所需的输出文件路径和名称作为参数。

#### 问：本教程是否需要有效的 Aspose 许可证？

答：是的，需要有效的 Aspose 许可证才能成功执行本教程中的代码。您可以从 Aspose 网站获取完整许可证或 30 天临时许可证。