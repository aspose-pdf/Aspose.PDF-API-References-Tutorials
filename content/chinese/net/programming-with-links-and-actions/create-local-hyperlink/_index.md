---
title: 在 PDF 文件中创建本地超链接
linktitle: 在 PDF 文件中创建本地超链接
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 在 PDF 文件中轻松创建本地超链接。
type: docs
weight: 40
url: /zh/net/programming-with-links-and-actions/create-local-hyperlink/
---
在 PDF 文件中创建本地超链接可让您创建可单击的链接，将用户带到同一 PDF 文档中的其他页面。使用 Aspose.PDF for .NET，您可以按照以下源代码轻松创建此类链接：

## 第 1 步：导入所需的库

在开始之前，您需要为 C# 项目导入必要的库。这是必要的导入指令：

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Text;
using Aspose.Pdf.InteractiveFeatures;
```

## 步骤 2：设置文档文件夹路径

在此步骤中，您需要指定要保存生成的 PDF 文件的文件夹的路径。代替`"YOUR DOCUMENT DIRECTORY"`在以下代码中使用文档文件夹的实际路径：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 步骤 3：创建 Document 实例

我们将创建一个实例`Document`类来表示我们的 PDF 文档。这是相应的代码：

```csharp
Document doc = new Document();
```

## 步骤 4：添加带有超链接的页面和文本

在此步骤中，我们将向 PDF 文档添加页面并添加一些包含本地超链接的文本。我们将为每个链接定义目标页面。这是相应的代码：

```csharp
Page page = doc.Pages.Add();

TextFragment text = new TextFragment("Link to page 7");
LocalHyperlink link = new LocalHyperlink();
link.TargetPageNumber = 7;
text. Hyperlink = link;
page.Paragraphs.Add(text);

text = new TextFragment("Link to page 1");
text. IsInNewPage = true;
link = new LocalHyperlink();
link.TargetPageNumber = 1;
text. Hyperlink = link;
page.Paragraphs.Add(text);
```

## 步骤 5：保存更新后的文档

现在让我们使用以下命令保存更新后的 PDF 文件`Save`的方法`doc`目的。这是相应的代码：

```csharp
dataDir = dataDir + "CreateLocalHyperlink_out.pdf";
doc.Save(dataDir);
```

### 使用 Aspose.PDF for .NET 创建本地超链接的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//创建文档实例
Document doc = new Document();
//将页面添加到 PDF 文件的页面集合
Page page = doc.Pages.Add();
//创建文本片段实例
Aspose.Pdf.Text.TextFragment text = new Aspose.Pdf.Text.TextFragment("link page number test to page 7");
//创建本地超链接实例
Aspose.Pdf.LocalHyperlink link = new Aspose.Pdf.LocalHyperlink();
//设置链接实例的目标页面
link.TargetPageNumber = 7;
//设置 TextFragment 超链接
text.Hyperlink = link;
//将文本添加到页面的段落集合中
page.Paragraphs.Add(text);
//创建新的 TextFragment 实例
text = new TextFragment("link page number test to page 1");
//TextFragment 应添加到新页面上
text.IsInNewPage = true;
//创建另一个本地超链接实例
link = new LocalHyperlink();
//设置第二个超链接的目标页面
link.TargetPageNumber = 1;
//设置第二个 TextFragment 的链接
text.Hyperlink = link;
//将文本添加到页面对象的段落集合中
page.Paragraphs.Add(text);    
dataDir = dataDir + "CreateLocalHyperlink_out.pdf";
//保存更新的文档
doc.Save(dataDir);
Console.WriteLine("\nLocal hyperlink created successfully.\nFile saved at " + dataDir);            
```

## 结论

恭喜！现在您有了使用 Aspose.PDF for .NET 在 PDF 中创建本地超链接的分步指南。您可以使用此代码创建可单击的链接，将用户带到同一文档中的其他页面。

请务必查看官方 Aspose.PDF 文档，以获取有关高级超链接功能的更多信息。

### 在 PDF 文件中创建本地超链接的常见问题解答

#### 问：什么是 PDF 文件中的本地超链接？

答：PDF 文件中的本地超链接是可单击的链接，可将用户导航到同一文档中的不同页面。这些链接增强了导航功能，使读者能够快速访问相关部分。

#### 问：本地超链接对我的 PDF 文档有何好处？

答：本地超链接提供了一种有效的方式来连接同一 PDF 文档中的相关内容。它们使读者能够快速跳转到特定部分，而无需滚动浏览整个文档，从而改善用户体验。

#### 问：Aspose.PDF for .NET 如何支持本地超链接的创建？
答：Aspose.PDF for .NET 为创建本地超链接提供全面支持。本指南中提供的分步教程演示了如何使用 C# 将本地超链接添加到 PDF 文档。

#### 问：我可以自定义本地超链接的外观吗？

答：是的，您可以自定义本地超链接的外观，包括文本颜色和样式，以确保它们符合文档的设计并提供一致的视觉体验。

#### 问：是否可以在单个 PDF 页面中创建多个本地超链接？

答：当然！您可以在单个 PDF 页面中创建多个本地超链接，允许读者根据需要跳转到各个部分或页面。每个本地超链接都可以根据其各自的目标进行定制。

#### 问：我可以使用本地超链接链接到页面的特定部分吗？

答：虽然本地超链接通常导航到整个页面，但您可以在 PDF 文档中创建锚点或书签以实现有针对性的链接。 Aspose.PDF for .NET 支持各种超链接选项。

#### 问：如何验证本地超链接是否正常工作？

答：按照提供的教程和示例代码，您可以自信地创建功能性本地超链接。您可以通过打开生成的 PDF 文档并单击超链接文本来测试链接。

#### 问：使用本地超链接有什么限制吗？

答：本地超链接是增强文档导航的有效方法，但确保文档结构保持清晰直观也很重要。正确标记的超链接和锚点有助于提供积极的用户体验。

#### 问：我可以在表格或图像中创建本地超链接吗？

答：是的，您可以在 PDF 文档的各种元素（包括表格、图像和文本）中创建本地超链接。 Aspose.PDF for .NET 可以灵活地向不同类型的内容添加超链接。