---
title: PDF 文件中的页码标记
linktitle: PDF 文件中的页码标记
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 文件中添加页码戳记。
type: docs
weight: 160
url: /zh/net/programming-with-stamps-and-watermarks/page-number-stamps/
---
在本教程中，我们将逐步指导您如何使用 Aspose.PDF for .NET 在 PDF 文件中添加页码戳记。我们将使用提供的 C# 源代码打开现有 PDF 文档、创建页码戳、设置其属性并将其添加到 PDF 文件中的特定页面。

## 第一步：搭建环境

在开始之前，请确保您具备以下条件：

- 已安装的 .NET 开发环境。
- 下载用于 .NET 的 Aspose.PDF 库并在您的项目中引用。

## 第 2 步：加载现有 PDF 文档

第一步是将现有的 PDF 文档加载到您的项目中。就是这样：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//打开现有的 PDF 文档
Document pdfDocument = new Document(dataDir + "PageNumberStamp.pdf");
```

请务必将“您的文档目录”替换为 PDF 文档所在目录的实际路径。

## 步骤 3：创建并配置页码标记

现在 PDF 文档已加载，我们可以创建页码缓冲区并根据需要进行配置。就是这样：

```csharp
//创建页码缓冲区
PageNumberStamp pageNumberStamp = new PageNumberStamp();

//定义缓冲区是否在后台
pageNumberStamp.Background = false;

//页编号缓冲区的格式
pageNumberStamp.Format = "Page # of " + pdfDocument.Pages.Count;

//页码缓冲区的下边距
pageNumberStamp.BottomMargin = 10;

//页码缓冲区的水平对齐
pageNumberStamp.HorizontalAlignment = HorizontalAlignment.Center;

//页码起始编号
pageNumberStamp.StartingNumber = 1;

//设置页码缓冲区文本属性
pageNumberStamp.TextState.Font = FontRepository.FindFont("Arial");
pageNumberStamp.TextState.FontSize = 14.0F;
pageNumberStamp.TextState.FontStyle = FontStyles.Bold;
pageNumberStamp.TextState.FontStyle = FontStyles.Italic;
pageNumberStamp.TextState.ForegroundColor = Color.Aqua;
```

上面的代码创建了一个页码标记，其属性包括页码格式、下边距、水平对齐方式、起始编号和文本属性。

## 步骤 4：将页码标记添加到特定页面

配置页码标记后，我们可以将其添加到 PDF 文档的特定页面。就是这样：

```csharp
//将页码缓冲区添加到特定页面
pdfDocument.Pages[1].AddStamp(pageNumberStamp);
```

上面的代码将页码标记添加到 PDF 文档的第一页。您可以根据需要更改页码。

## 步骤5：保存修改后的PDF文档

一旦页码标记添加到PDF文档中，我们就可以保存修改后的PDF文档。就是这样：

```csharp
//保存修改后的PDF文档
pdfDocument.Save(dataDir + "PageNumberStamp_out.pdf");
```

请务必将“您的文档目录”替换为您要保存编辑后的 PDF 文档的目录的实际路径。

### 使用 Aspose.PDF for .NET 的页码图章示例源代码 
```csharp

//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//打开文档
Document pdfDocument = new Document(dataDir+ "PageNumberStamp.pdf");

//创建页码印记
PageNumberStamp pageNumberStamp = new PageNumberStamp();

//印章是否为背景
pageNumberStamp.Background = false;
pageNumberStamp.Format = "Page # of " + pdfDocument.Pages.Count;
pageNumberStamp.BottomMargin = 10;
pageNumberStamp.HorizontalAlignment = HorizontalAlignment.Center;
pageNumberStamp.StartingNumber = 1;

//设置文本属性
pageNumberStamp.TextState.Font = FontRepository.FindFont("Arial");
pageNumberStamp.TextState.FontSize = 14.0F;
pageNumberStamp.TextState.FontStyle = FontStyles.Bold;
pageNumberStamp.TextState.FontStyle = FontStyles.Italic;
pageNumberStamp.TextState.ForegroundColor = Color.Aqua;

//添加图章到特定页面
pdfDocument.Pages[1].AddStamp(pageNumberStamp);
dataDir = dataDir + "PageNumberStamp_out.pdf";

//保存输出文档
pdfDocument.Save(dataDir);
Console.WriteLine("\nPage number stamp added successfully.\nFile saved at " + dataDir);

```

## 结论

恭喜！您已了解如何使用 Aspose.PDF for .NET 将页码标记添加到 PDF 文档。现在，您可以通过添加清晰且信息丰富的页码来个性化您的 PDF 文档。

### PDF 文件中页码标记的常见问题解答

#### 问：什么是页码标记，如何使用它向 PDF 文件添加页码？

答：页码标记是 Aspose.PDF 中的一项功能，允许您将动态页码添加到 PDF 文档的特定页面。在本教程中，它是通过创建 PageNumberStamp 对象、配置其属性并将其添加到指定页面来实现的。

#### 问：提供的 C# 源代码如何完成向 PDF 文件添加页码戳记？

答：代码演示了如何加载现有的 PDF 文档，创建 PageNumberStamp，设置各种属性（如格式、字体、对齐方式等），然后将图章添加到特定页面。邮票自动计算总页数并插入正确的页码。

#### 问：我可以自定义页码的外观，例如字体样式、颜色和大小吗？

答：当然，您可以通过调整字体、字体大小、字体样式（粗体、斜体等）和文本颜色等属性来自定义页码标记的外观。

#### 问：是否可以在 PDF 文档的多个页面上添加页码标记？

答：是的，您可以通过创建多个 PageNumberStamp 对象并将每个对象添加到所需页面来将页码标记添加到多个页面。

#### 问：我可以选择页码标记是作为页面内容的一部分还是作为背景元素显示？

答：是的，您可以通过设置页码标记来控制页码标记是作为页面内容的一部分还是作为背景元素显示。`Background` PageNumberStamp 的属性。

#### 问：如何指定页码的格式，包括总页数？

答：该代码使用`Format`PageNumberStamp 属性指定页码的格式。宏“# of”用于表示总页数。

#### 问：如果我在多个页面上添加相同的页码戳记，会发生什么情况？

答：将相同的 PageNumberStamp 实例添加到多个页面将显示每个页面的正确页码。印章会自动调整页码和总页数。

#### 问：我可以将页码标记添加到 PDF 文档的页眉或页脚部分吗？

答：虽然 PageNumberStamp 通常直接添加到页面内容中，但您可以使用 FloatingBox 或其他技术将它们放置在页眉或页脚部分中。

#### 问：如何指定页码标记在页面上的位置？

答： 的`BottomMargin`和`HorizontalAlignment` PageNumberStamp 的属性允许您控制图章在页面中的位置。

#### 问：如果我想从不同的数字而不是 1 开始页码，该怎么办？

答：您可以设置`StartingNumber`PageNumberStamp 属性来指定起始页码。