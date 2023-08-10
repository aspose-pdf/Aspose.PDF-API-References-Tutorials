---
title: 在 PDF 文件中设置标注属性
linktitle: 在 PDF 文件中设置标注属性
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 文件中设置标注属性。使用标注线、文本颜色和结束样式自定义注释。
type: docs
weight: 130
url: /zh/net/annotations/setcalloutproperty/
---
 Aspose.PDF for .NET 是一个功能强大的库，用于在 C# 中创建、操作和转换 PDF 文档。该库提供的功能之一是能够为 PDF 文档中的自由文本注释设置标注属性。这可以使用以下方法完成`FreeTextAnnotation`类，它允许您使用标注创建注释。

在本教程中，我们将指导您完成在 C# 中使用 Aspose.PDF for .NET 设置自由文本注释标注属性的过程。请按照以下步骤开始。

## 安装 Aspose.PDF for .NET

如果您还没有这样做，您将需要[下载](https://releases.aspose.com/pdf/net/)并从 Aspose 版本或通过 NuGet 包管理器安装 Aspose.PDF for .NET。

## 第 1 步：创建一个新的 PDF 文档

使用以下命令创建新的 PDF 文档`Document`Aspose.PDF for .NET 提供的类。

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document();
```

## 步骤 2：向文档添加新页面

使用以下命令向文档添加新页面`Pages`的集合`Document`班级。

```csharp
Page page = doc.Pages.Add();
```

## 第 3 步：设置默认外观

通过创建新的文本注释来设置自由文本注释的默认外观`DefaultAppearance`对象并设置其属性，例如`TextColor`和`FontSize`.

```csharp
DefaultAppearance da = new DefaultAppearance();
da.TextColor = System.Drawing.Color.Red;
da.FontSize = 10;
```

## 步骤 4：创建带有标注的自由文本注释

使用标注创建新的自由文本注释`FreeTextAnnotation`班级。设置`Intent`财产给`FreeTextIntent.FreeTextCallout`指定这是一个标注注释。设置`EndingStyle`财产给`LineEnding.OpenArrow`指定标注末尾的箭头样式。设置`Callout`属性到数组`Point`表示页面上应绘制标注线的点的对象。

```csharp
FreeTextAnnotation fta = new FreeTextAnnotation(page, new Rectangle(422.25, 645.75, 583.5, 702.75), da);
fta.Intent = FreeTextIntent.FreeTextCallout;
fta.EndingStyle = LineEnding.OpenArrow;
fta.Callout = new Point[]
{
    new Point(428.25,651.75), new Point(462.75,681.375), new Point(474,681.375)
};
```

## 步骤 5：向页面添加自由文本注释

使用以下命令将自由文本注释添加到页面`Annotations`的集合`Page`班级。

```csharp
page.Annotations.Add(fta);
```

## 第 6 步：向注释添加文本

通过设置将文本添加到注释`RichText`属性为格式化 XML 字符串。在本教程中，我们将文本颜色设置为红色，并将字体大小设置为 9。

```csharp
fta.RichText = "<body xmlns=\"http://www.w3.org/1999/xhtml\" xmlns:xfa=\"http://www.xfa.org/schema/xfa-data/1.0/\" xfa:APIVersion=\"Acrobat:11.0.23\" xfa:spec=\"2.0.2\" 样式=\"颜色:#FF
```

## 第7步：保存文档

现在使用以下代码保存文档：

```csharp
doc.Save(dataDir + "SetCalloutProperty.pdf")
```

### 使用 Aspose.PDF for .NET 设置标注属性的示例源代码

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
Page page = doc.Pages.Add();
DefaultAppearance da = new DefaultAppearance();
da.TextColor = System.Drawing.Color.Red;
da.FontSize = 10;
FreeTextAnnotation fta = new FreeTextAnnotation(page, new Rectangle(422.25, 645.75, 583.5, 702.75), da);
fta.Intent = FreeTextIntent.FreeTextCallout;
fta.EndingStyle = LineEnding.OpenArrow;
fta.Callout = new Point[]
{
	new Point(428.25,651.75), new Point(462.75,681.375), new Point(474,681.375)
};
page.Annotations.Add(fta);
fta.RichText = "<body xmlns=\"http://www.w3.org/1999/xhtml\" xmlns:xfa=\"http://www.xfa.org/schema/xfa-data/1.0/\" xfa:APIVersion=\"Acrobat:11.0.23\" xfa:spec=\"2.0.2\" style=\"color:#FF0000;font-weight:normal;font-style:normal;font-stretch:normal\"><p dir=\"ltr\"> <span style=\"font-size:9.0pt;font-family:Helvetica\">这是一个示例</span></p></body>";
doc.Save(dataDir + "SetCalloutProperty.pdf");
```

## 结论

在本教程中，我们探讨了如何使用 Aspose.PDF for .NET 在 PDF 文档中设置自由文本注释的标注属性。标注注释可用于提供与文档中特定区域相关的附加信息或解释。 Aspose.PDF for .NET 提供了广泛的处理 PDF 文件的特性和功能，包括创建和自定义注释，例如标注。通过遵循分步指南并使用提供的 C# 源代码，开发人员可以轻松在 PDF 文档中实现标注注释，从而增强文档的可用性和清晰度。 Aspose.PDF for .NET 是一个多功能且可靠的库，用于 .NET 应用程序中的 PDF 操作，提供强大的工具来高效处理各种 PDF 相关任务。

### 在 PDF 文件中设置标注属性的常见问题解答

#### 问：什么是 PDF 文档中的标注注释？

答：PDF 文档中的标注注释是一种注释类型，允许您创建带有指向文档中特定区域的引出线的文本框。它通常用于提供与文档中特定部分或元素相关的附加信息或注释。

#### 问：我可以使用 Aspose.PDF for .NET 自定义标注注释的外观吗？

答：是的，您可以自定义标注注释的各种属性，例如颜色、字体大小、文本对齐方式、线条样式、箭头样式等。

#### 问：如何向标注注释添加文本？

 A：要在标注注释中添加文本，您可以设置`RichText`的财产`FreeTextAnnotation`目的。这`RichText`属性采用格式化 XML 字符串，表示要在标注注释中显示的文本。

#### 问：我可以使用 Aspose.PDF for .NET 将多个标注注释添加到 PDF 文档吗？

答：是的，您可以通过创建多个标注实例来在 PDF 文档中创建多个标注注释。`FreeTextAnnotation`对象并将它们添加到文档中的不同页面或位置。