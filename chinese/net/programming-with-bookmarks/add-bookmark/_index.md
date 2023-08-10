---
title: 在 PDF 文件中添加书签
linktitle: 在 PDF 文件中添加书签
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 在 PDF 文件中轻松添加书签以改进导航。
type: docs
weight: 10
url: /zh/net/programming-with-bookmarks/add-bookmark/
---
在 PDF 文件中添加书签可以轻松快速地进行导航。使用Aspose.PDF for .NET，您可以通过以下源代码轻松地在PDF文件中添加书签：

## 第1步：导入所需的库

在开始之前，您需要为 C# 项目导入必要的库。这是必要的导入指令：

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

## 步骤 2：设置文档文件夹路径

在此步骤中，您需要指定包含要添加书签的 PDF 文件的文件夹的路径。代替`"YOUR DOCUMENT DIRECTORY"`在以下代码中使用文档文件夹的实际路径：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 步骤 3：打开 PDF 文档

现在我们将使用以下代码打开要添加书签的 PDF 文档：

```csharp
Document pdfDocument = new Document(dataDir + "AddBookmark.pdf");
```

## 第四步：创建书签对象

在此步骤中，我们将使用创建一个书签对象`OutlineItemCollection`类并设置其属性，例如标题、斜体属性、粗体属性和单击时要执行的操作。这是相应的代码：

```csharp
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Test Outline";
pdfOutline. Italic = true;
pdfOutline. Bold = true;
pdfOutline.Action = new GoToAction(pdfDocument.Pages[1]);
```

## 步骤 5：向文档添加书签

最后，我们使用以下命令将创建的书签添加到文档的书签集合中`Add`的方法`Outlines`财产。这是相应的代码：

```csharp
pdfDocument.Outlines.Add(pdfOutline);
```

### 使用 Aspose.PDF for .NET 添加书签的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//打开文档
Document pdfDocument = new Document(dataDir + "AddBookmark.pdf");
//创建书签对象
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Test Outline";
pdfOutline.Italic = true;
pdfOutline.Bold = true;
//设置目标页码
pdfOutline.Action = new GoToAction(pdfDocument.Pages[1]);
//在文档的大纲集合中添加书签。
pdfDocument.Outlines.Add(pdfOutline);
dataDir = dataDir + "AddBookmark_out.pdf";
//保存输出
pdfDocument.Save(dataDir);
Console.WriteLine("\nBookmark added successfully.\nFile saved at " + dataDir);
```

## 结论

恭喜！现在您有了使用 Aspose.PDF for .NET 添加书签的分步指南。您可以使用此代码通过添加自定义书签来改进 PDF 文档中的导航。

请务必查看官方 Aspose.PDF 文档，以获取有关高级书签操作功能的更多信息。


### 在 PDF 文件中添加书签的常见问题解答

#### 问：PDF 文件中的书签是什么？

答：书签，也称为大纲，是在 PDF 文档中提供导航和结构的交互式元素。它们允许用户快速跳转到特定部分或页面。

#### 问：为什么需要向 PDF 文件添加书签？

答：向 PDF 文件添加书签可改善用户体验，并使读者更轻松地浏览文档内容。书签可以用作目录或提供对重要部分的快速访问。

#### 问：如何导入 C# 项目所需的库？

答：要导入 C# 项目所需的库，请包含以下导入指令：

```csharp
using Aspose.Pdf;
using Aspose.Pdf.InteractiveFeatures;
```

这些指令使您能够访问处理 PDF 文档和书签所需的类和方法。

#### 问：如何指定文档文件夹的路径？

答：更换`"YOUR DOCUMENT DIRECTORY"`在提供的源代码中包含要添加书签的 PDF 文件的文件夹的实际路径。

#### 问：如何打开PDF文档添加书签？

A：要打开PDF文档添加书签，请使用以下代码：

```csharp
Document pdfDocument = new Document(dataDir + "AddBookmark.pdf");
```

代替`"AddBookmark.pdf"`与实际的文件名。

#### 问：如何创建书签对象？

 A：要创建书签对象，请使用`OutlineItemCollection`班级。自定义其属性，例如标题、斜体样式、粗体样式以及单击时要执行的操作。

```csharp
OutlineItemCollection pdfOutline = new OutlineItemCollection(pdfDocument.Outlines);
pdfOutline.Title = "Test Outline";
pdfOutline.Italic = true;
pdfOutline.Bold = true;
pdfOutline.Action = new GoToAction(pdfDocument.Pages[1]);
```

#### 问：这样做的目的是什么`Action` property in a bookmark?

答： 的`Action`属性指定单击书签时要执行的操作。在这个例子中，我们使用`GoToAction`导航到特定页面（本例中为第 2 页）的类。

#### 问：如何为文档添加书签？

答：使用`Add`的方法`Outlines`属性将创建的书签添加到文档的书签集合中。

```csharp
pdfDocument.Outlines.Add(pdfOutline);
```

#### 问：我可以使用此方法添加多个书签吗？

答：是的，您可以重复步骤 4 至 8，为文档添加多个书签。根据需要自定义每个书签的属性和操作。

#### 问：如何保存更新后的 PDF 文件？

答：使用以下命令保存更新的 PDF 文件`Save`的方法`pdfDocument`目的：

```csharp
dataDir = dataDir + "AddBookmark_out.pdf";
pdfDocument.Save(dataDir);
```

#### 问：如何确认书签已添加？

A：打开生成的PDF文件，验证指定的书签是否已添加到文档中。

#### 问：我可以添加的书签数量有限制吗？

答：通常对可以添加的书签数量没有严格限制，但请考虑文档的大小和复杂性以获得最佳性能。

#### 问：我可以自定义书签的外观吗？

答：是的，您可以使用 Aspose.PDF 功能进一步自定义书签外观、颜色、样式和其他属性。