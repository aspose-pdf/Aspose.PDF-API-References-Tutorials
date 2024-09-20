---
title: 在 PDF 文档中添加重复列
linktitle: 在 PDF 文档中添加重复列
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 向 PDF 文档添加重复列。带有示例和代码的分步指南。非常适合开发人员。
type: docs
weight: 20
url: /zh/net/programming-with-tables/add-repeating-column/
---
## 介绍

如果您正在处理 PDF 文档并需要添加重复列，那么您来对地方了！使用 Aspose.PDF for .NET，您可以轻松管理 PDF 中的表格和内容。无论您是构建动态报告、发票还是任何其他结构化文档，重复列都可以改变数据组织方式。让我们深入了解如何向 PDF 文档添加重复列的分步指南。

## 先决条件

在我们进入代码之前，让我们确保所有设置都已完成：

- Aspose.PDF for .NET：您需要在项目中安装 Aspose.PDF for .NET 库。
- [下载 Aspose.PDF for .NET](https://releases.aspose.com/pdf/net/)
- [免费试用](https://releases.aspose.com/)
- 开发环境：确保您安装了与 .NET 兼容的 IDE，例如 Visual Studio。
- 对 C# 的基本了解：虽然我们会将所有内容分解，但对 C# 的基本了解将帮助您顺利跟上。
  
如果你还没有 Aspose.PDF for .NET，你可以获取[临时执照](https://purchase.aspose.com/temporary-license/)开始探索其功能。

## 导入包

首先，您需要从 Aspose.PDF for .NET 导入必要的命名空间。操作方法如下：

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
```

这些包提供了处理 PDF 文档和操作表格所需的基本类和方法。

现在，让我们将流程分解为多个步骤，以将重复列添加到 PDF 文档。继续！

## 步骤 1：设置文档目录的路径

在创建或操作任何文件之前，我们需要定义生成的 PDF 的保存路径。在您的 C# 项目中，将目录路径设置为文件所在的位置：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string outFile = dataDir + "AddRepeatingColumn_out.pdf";
```

此路径指向将保存输出 PDF 的目录。替换`"YOUR DOCUMENT DIRECTORY"`与您的机器上的实际路径。

## 步骤 2：创建新的 PDF 文档

首先，实例化一个新的`Document`对象。这将作为 PDF 中所有页面和内容的容器。

```csharp
Document doc = new Document();
Aspose.Pdf.Page page = doc.Pages.Add();
```

在这里，我们创建了一个新的 PDF 文档，并向其中添加了一个空白页。`doc.Pages.Add()`方法将新页面插入到文档中。

## 步骤 3：实例化外表

接下来，我们创建一个外部表格。此表格将横跨整个页面宽度，并充当其他表格（包括包含重复列的表格）的容器。

```csharp
Aspose.Pdf.Table outerTable = new Aspose.Pdf.Table();
outerTable.ColumnWidths = "100%";
outerTable.HorizontalAlignment = HorizontalAlignment.Left;
```

我们已经设定了`ColumnWidths`属性为“100%”，表示表格将延伸至整个页面宽度。

## 步骤 4：创建内部表

现在，让我们创建内部表，它将具有重复列。这里的关键属性是`Broken`，允许表格延续到同一页，并且`ColumnAdjustment`，它会自动调整列宽以适合内容。

```csharp
Aspose.Pdf.Table mytable = new Aspose.Pdf.Table();
mytable.Broken = TableBroken.VerticalInSamePage;
mytable.ColumnAdjustment = ColumnAdjustment.AutoFitToContent;
```

该内表将嵌套在外表内。

## 步骤 5：向页面添加表格

现在我们已经准备好了外部表格和内部表格，让我们将它们添加到页面中。此步骤可确保表格包含在文档的结构中。

```csharp
page.Paragraphs.Add(outerTable);
var bodyRow = outerTable.Rows.Add();
var bodyCell = bodyRow.Cells.Add();
bodyCell.Paragraphs.Add(mytable);
mytable.RepeatingColumnsCount = 5;
```

在这里，我们添加了`outerTable`到页面，然后在外部表格中，我们嵌套了`mytable`。此外，我们设定`RepeatingColumnsCount`到 5，指定添加数据时应重复多少列。

## 步骤 6：添加标题行

现在是时候将标题添加到表格中了。标题行提供了数据的背景并有助于构建列。 

```csharp
Aspose.Pdf.Row row = mytable.Rows.Add();
row.Cells.Add("header 1");
row.Cells.Add("header 2");
row.Cells.Add("header 3");
row.Cells.Add("header 4");
row.Cells.Add("header 5");
row.Cells.Add("header 6");
row.Cells.Add("header 7");
row.Cells.Add("header 11");
row.Cells.Add("header 12");
row.Cells.Add("header 13");
row.Cells.Add("header 14");
row.Cells.Add("header 15");
row.Cells.Add("header 16");
row.Cells.Add("header 17");
```

此代码片段添加第一行（我们将其用作标题），并用包含“标题 1”，“标题 2”等文本的单元格填充它。

## 步骤 7：添加数据行

最后，我们可以向表中添加一些数据。此循环动态创建行并用内容填充单元格：

```csharp
for (int RowCounter = 0; RowCounter <= 5; RowCounter++)
{
    Aspose.Pdf.Row row1 = mytable.Rows.Add();
    row1.Cells.Add("col " + RowCounter.ToString() + ", 1");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 2");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 3");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 4");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 5");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 6");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 7");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 11");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 12");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 13");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 14");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 15");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 16");
    row1.Cells.Add("col " + RowCounter.ToString() + ", 17");
}
```

循环迭代六次，添加行并用相应的列数据填充每个单元格（例如“col 1, 1”，“col 2, 2”等）。

## 步骤 8：保存文档

添加完所有行和列后，最后一步是将文档保存到指定的文件路径。

```csharp
doc.Save(outFile);
```

您的文档现在已保存重复列！

## 结论

就是这样！通过这些简单的步骤，您可以使用 Aspose.PDF for .NET 创建具有重复列的 PDF 文档。通过利用嵌套表的灵活性，您可以实现复杂的布局，使您的 PDF 看起来专业且井井有条。在您的下一个项目中尝试一下，并探索 Aspose.PDF 满足您的 PDF 生成需求的全部潜力。

## 常见问题解答

### 什么是 Aspose.PDF for .NET？
Aspose.PDF for .NET 是一个功能强大的库，允许开发人员以编程方式创建、编辑和管理 PDF 文档。

### 我可以动态调整重复列的数量吗？
是的，您可以通过修改`RepeatingColumnsCount`财产。

### 如何向 Aspose.PDF for .NET 申请许可证？
您可以按照以下步骤从文件或流中应用许可证[文档](https://reference.aspose.com/pdf/net/).

### 是否可以向表格单元格添加图像？
是的，Aspose.PDF for .NET 支持向表格单元格添加各种类型的内容，包括图像。

### 我可以进一步自定义表格布局吗？
当然！Aspose.PDF 提供了丰富的自定义表格样式功能，包括边框、填充、对齐等。