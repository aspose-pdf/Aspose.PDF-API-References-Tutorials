---
title: 添加目录时自定义页码
linktitle: 添加目录时自定义页码
second_title: Aspose.PDF for .NET API 参考
description: 通过此分步指南和代码示例，了解如何使用 Aspose.PDF for .NET 在添加目录 (TOC) 时自定义页码。
type: docs
weight: 100
url: /zh/net/programming-with-document/customizepagenumbeswhileaddingtoc/
---

在本教程中，我们将探讨如何使用 Aspose.PDF for .NET 在添加目录 (TOC) 时自定义页码。我们将提供分步指导以及代码示例，以帮助您实现这一目标。

## 第 1 步：加载现有的 PDF 文件

首先，我们需要加载一个现有的 PDF 文件。对于本教程，我们将使用位于“您的文档目录”目录中的文件“42824.pdf”。将此目录路径替换为文档目录的实际路径。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
string inFile = dataDir + "42824.pdf";
string outFile = dataDir + "42824_out.pdf";
Document doc = new Document(inFile);
```

## 第 2 步：添加目录页面

接下来，我们需要在文档的开头添加一个新页面作为目录页面。我们可以通过使用`Insert()`的方法`Pages`的集合`Document`目的。

```csharp
Aspose.Pdf.Page tocPage = doc.Pages.Insert(1);
```

## 第 3 步：创建目录对象

要创建 TOC 对象，我们首先需要创建一个`TocInfo`对象并设置其属性。在本教程中，我们将目录的标题设置为“目录”，将页码前缀设置为“P”。

```csharp
TocInfo tocInfo = new TocInfo();
TextFragment title = new TextFragment("Table Of Contents");
title.TextState.FontSize = 20;
title.TextState.FontStyle = FontStyles.Bold;
tocInfo.Title = title;
tocInfo.PageNumbersPrefix = "P";
tocPage.TocInfo = tocInfo;
```

## 第 4 步：创建 TOC 条目

要创建 TOC 条目，我们需要遍历文档的所有页面（TOC 页面除外），并为每个页面创建一个标题对象。然后我们可以将标题对象添加到 TOC 页面并指定其目标页面。

```csharp
for (int i = 1; i < doc.Pages.Count; i++)
{
    //创建标题对象
    Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
    TextSegment segment2 = new TextSegment();
    heading2.TocPage = tocPage;
    heading2.Segments.Add(segment2);
    //指定标题对象的目标页面
    heading2.DestinationPage = doc.Pages[i + 1];
    //目标页面
    heading2.Top = doc.Pages[i + 1].Rect.Height;
    //目的地坐标
    segment2.Text = "Page " + i.ToString();
    //将标题添加到包含目录的页面
    tocPage.Paragraphs.Add(heading2);
}
```

## 第 5 步：保存更新后的文档

最后，我们需要将更新后的文档保存到一个新文件中。我们可以通过使用`Save()`的方法`Document`目的。

```csharp
doc.Save(outFile);
```

### 使用 Aspose.PDF for .NET 添加 TOC 时自定义页码的示例源代码

```csharp

            
			string dataDir = "YOUR DOCUMENT DIRECTORY";
            string inFile = dataDir + "42824.pdf";
            string outFile = dataDir + "42824_out.pdf";
            //加载现有的 PDF 文件
            Document doc = new Document(inFile);
            //访问 PDF 文件的第一页
            Aspose.Pdf.Page tocPage = doc.Pages.Insert(1);
            //创建对象来表示 TOC 信息
            TocInfo tocInfo = new TocInfo();
            TextFragment title = new TextFragment("Table Of Contents");
            title.TextState.FontSize = 20;
            title.TextState.FontStyle = FontStyles.Bold;
            //为目录设置标题
            tocInfo.Title = title;
            tocInfo.PageNumbersPrefix = "P";
            tocPage.TocInfo = tocInfo;
            for (int i = 1; i<doc.Pages.Count; i++)
            {
                //创建标题对象
                Aspose.Pdf.Heading heading2 = new Aspose.Pdf.Heading(1);
                TextSegment segment2 = new TextSegment();
                heading2.TocPage = tocPage;
                heading2.Segments.Add(segment2);
                //指定标题对象的目标页面
                heading2.DestinationPage = doc.Pages[i + 1];
                //目标页面
                heading2.Top = doc.Pages[i + 1].Rect.Height;
                //目的地坐标
                segment2.Text = "Page " + i.ToString();
                //将标题添加到包含目录的页面
                tocPage.Paragraphs.Add(heading2);
            }

            //保存更新的文档
            doc.Save(outFile);
            
        
```

## 结论

在本教程中，我们提供了有关如何在使用 Aspose.PDF for .NET 添加 TOC 时自定义页码的分步指导。我们还提供了一个代码示例，您可以在您的应用程序中实现此功能时作为参考

