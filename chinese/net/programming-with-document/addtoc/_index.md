---
title: 添加目录到 PDF 文件
linktitle: 添加目录到 PDF 文件
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 将目录添加到 PDF 文件。带有示例源代码的分步指南。增强文档导航！
type: docs
weight: 40
url: /zh/net/programming-with-document/addtoc/
---
在本教程中，我们将探讨如何使用 Aspose.PDF for .NET 的“将 TOC（目录）添加到 PDF 文件”功能将目录添加到 PDF 文档。我们将提供分步指南并解释实现此目的所需的 C# 源代码。在本教程结束时，您将能够使用 Aspose.PDF for .NET 生成带有目录的 PDF 文档。


## 第 1 步：加载现有 PDF 文件

首先，我们需要加载现有的 PDF 文件。代替`"YOUR DOCUMENT DIRECTORY"`在以下代码中添加 PDF 文件的实际路径：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "AddTOC.pdf");
```

## 步骤 2：为目录创建一个新页面

我们将创建一个新页面来保存目录。以下代码在索引 1 处插入一个新页面：

```csharp
Page tocPage = doc.Pages.Insert(1);
```

## 步骤 3：定义目录信息

接下来，我们需要定义目录信息。我们将设置目录的标题和其他属性。添加以下代码：

```csharp
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;

tocInfo.Title = title;
tocPage.TocInfo = tocInfo;
```

## 第 4 步：创建目录元素

现在，我们将创建目录的元素。在本教程中，我们将创建对应于不同页面的四个目录元素。根据您的要求修改以下代码：

```csharp
string[] titles = new string[4];
titles[0] = "First page";
titles[1] = "Second page";
titles[2] = "Third page";
titles[3] = "Fourth page";

for (int i = 0; i < 2; i++)
{
    Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
    TextSegment segment2 = new TextSegment();
    heading2.TocPage = tocPage;
    heading2.Segments.Add(segment2);

    heading2.DestinationPage = doc.Pages[i + 2];
    heading2.Top = doc.Pages[i + 2].Rect.Height;

    segment2.Text = titles[i];
    tocPage.Paragraphs.Add(heading2);
}
```

## 步骤 5：保存更新后的文档

最后，我们需要将修改后的文档与目录一起保存。代替`"YOUR DOCUMENT DIRECTORY"`在下面的代码中使用所需的输出文件路径：

```csharp
dataDir = dataDir + "TOC_out.pdf";
doc.Save(dataDir);
Console.WriteLine("\nTOC added successfully to an existing PDF.\nFile saved at " + dataDir);
```

### 使用 Aspose.PDF for .NET 将 TOC 添加到 PDF 文档的示例源代码

```csharp

//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//加载现有的 PDF 文件
Document doc = new Document(dataDir + "AddTOC.pdf");

//访问 PDF 文件的第一页
Page tocPage = doc.Pages.Insert(1);

//创建对象来表示 TOC 信息
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;

//设置目录标题
tocInfo.Title = title;
tocPage.TocInfo = tocInfo;

//创建将用作目录元素的字符串对象
string[] titles = new string[4];
titles[0] = "First page";
titles[1] = "Second page";
titles[2] = "Third page";
titles[3] = "Fourth page";
for (int i = 0; i < 2; i++)
{
	//创建标题对象
	Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
	TextSegment segment2 = new TextSegment();
	heading2.TocPage = tocPage;
	heading2.Segments.Add(segment2);

	//指定标题对象的目标页面
	heading2.DestinationPage = doc.Pages[i + 2];

	//目的地页面
	heading2.Top = doc.Pages[i + 2].Rect.Height;

	//目的地坐标
	segment2.Text = titles[i];

	//将标题添加到包含目录的页面
	tocPage.Paragraphs.Add(heading2);
}
dataDir = dataDir + "TOC_out.pdf";
//保存更新后的文档
doc.Save(dataDir);

Console.WriteLine("\nTOC added successfully to an existing PDF.\nFile saved at " + dataDir);
```

## 结论

在本教程中，我们探讨了如何使用 Aspose.PDF for .NET 将目录 (TOC) 添加到 PDF 文档。通过遵循分步指南并利用提供的 C# 源代码，您可以轻松生成带有目录的 PDF 文档。 TOC 增强了文档的可用性，允许用户更有效地导航到特定部分或页面。 Aspose.PDF for .NET 提供了一个强大且用户友好的解决方案，用于在 .NET 应用程序中处理 PDF 文件，使您能够轻松创建动态和交互式 PDF 文档。

### 将目录添加到 PDF 文件的常见问题解答

#### 问：什么是 Aspose.PDF for .NET？

答：Aspose.PDF for .NET 是一个功能强大的库，允许开发人员在 .NET 应用程序中有效地处理 PDF 文件。它提供了广泛的功能，用于以编程方式创建、操作和管理 PDF 文档。

#### 问：向 PDF 文档添加目录 (TOC) 的目的是什么？

答：目录 (TOC) 为用户提供导航帮助，使他们能够快速跳转到 PDF 文档中的特定部分或页面。它提高了文档的可用性和用户体验。

#### 问：如何使用 Aspose.PDF for .NET 将目录添加到 PDF 文档？

答：要使用 Aspose.PDF for .NET 将目录添加到 PDF 文档中，您需要创建一个新页面来保存 TOC，定义目录信息，然后创建与特定页面或对应的 TOC 元素文档中的部分。

#### 问：我可以自定义目录的外观吗？

答：是的，您可以通过设置目录元素的各种属性（例如字体大小、字体样式和对齐方式）来自定义目录的外观。 Aspose.PDF for .NET 提供了设计目录的灵活性，以匹配您所需的外观和感觉。

#### 问：Aspose.PDF for .NET 是否适合向 PDF 文档添加高级功能？

答：当然，Aspose.PDF for .NET 是一个功能丰富的库，允许您向 PDF 文档添加高级功能，包括交互元素、表单字段、数字签名等。