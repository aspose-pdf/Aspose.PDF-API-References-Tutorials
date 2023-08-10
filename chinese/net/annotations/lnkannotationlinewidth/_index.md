---
title: lnk 注释线宽
linktitle: lnk 注释线宽
second_title: Aspose.PDF for .NET API 参考
description: 本文提供了使用 Aspose.PDF for .NET 设置 lnk 注释线宽的分步指南。
type: docs
weight: 110
url: /zh/net/annotations/lnkannotationlinewidth/
---
Aspose.PDF 是一个功能强大且广泛使用的工具，用于在 .NET 应用程序中处理 PDF 文件。它提供了用于创建、编辑和操作 PDF 文件的各种功能，包括向页面添加注释的功能。在本教程中，我们将解释如何使用 Aspose.PDF for .NET 设置链接注释的线宽。

满足这些先决条件后，请在 Visual Studio 中创建一个新的控制台应用程序项目。然后，通过右键单击解决方案资源管理器中的项目，选择“管理 NuGet 包”并在 NuGet 包管理器中搜索“Aspose.PDF”，添加对 Aspose.PDF for .NET 库的引用。

要向 PDF 文档添加 lnk 注释，请按照下列步骤操作：

## 第 1 步：创建一个新的`Document` object.
```csharp
Document doc = new Document();
```
## 步骤 2：向文档添加新页面。
```csharp
doc.Pages.Add();
```
## 第 3 步：创建一个列表`Point` arrays that represent the ink gesture for the annotation.
```csharp
IList<Point[]> inkList = new List<Point[]>();
```
## 第 4 步：创建一个新的`LineInfo` object that defines the properties of the ink gesture.
```csharp
LineInfo lineInfo = new LineInfo();
lineInfo.VerticeCoordinate = new float[] { 55, 55, 70, 70, 70, 90, 150, 60 };
lineInfo.Visibility = true;
lineInfo.LineColor = System.Drawing.Color.Red;
lineInfo.LineWidth = 2;
```
## 第 5 步：创建一个新的`Aspose.Pdf.Point` array that represents the gesture from the `LineInfo` object.
```csharp
int length = lineInfo.VerticeCoordinate.Length / 2;
Aspose.Pdf.Point[] gesture = new Aspose.Pdf.Point[length];
for (int i = 0; i < length; i++)
{
    gesture[i] = new Aspose.Pdf.Point(lineInfo.VerticeCoordinate[2 * i], lineInfo.VerticeCoordinate[2 * i + 1]);
}
```
## 步骤 6：将手势添加到墨迹手势列表中。
```csharp
inkList.Add(gesture);
```
## 第 7 步：创建一个新的`InkAnnotation` object that represents the link annotation.
```csharp
InkAnnotation a1 = new InkAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), inkList);
```
## 步骤8：设置注释的主题和标题。
```csharp
a1.Subject = "Test";
a1.Title = "Title";
```
## 步骤9：设置注释的颜色。
```csharp
a1.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
```
## 第10步：创建一个新的`Border` object that defines the properties of the annotation's border.
```csharp
Border border = new Border(a1);
border.Width = 3;
border.Effect = BorderEffect.Cloudy;
border.Dash = new Dash(1, 1);
border.Style = BorderStyle.Solid;
```
## 第11步：将注释添加到页面。
```csharp
doc.Pages[1].Annotations.Add(a1);
```
## 第 12 步：将文档保存到文件中。
```csharp
//保存输出文件
doc.Save(dataDir);


```
### 该示例显示了 Aspose.PDF for .NET 的 lnk 注释线宽

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

Document doc = new Document();
doc.Pages.Add();
IList<Point[]> inkList = new List<Point[]>();
LineInfo lineInfo = new LineInfo();
lineInfo.VerticeCoordinate = new float[] { 55, 55, 70, 70, 70, 90, 150, 60 };
lineInfo.Visibility = true;
lineInfo.LineColor = System.Drawing.Color.Red;
lineInfo.LineWidth = 2;
int length = lineInfo.VerticeCoordinate.Length / 2;
Aspose.Pdf.Point[] gesture = new Aspose.Pdf.Point[length];
for (int i = 0; i < length; i++)
{
gesture[i] = new Aspose.Pdf.Point(lineInfo.VerticeCoordinate[2 * i], lineInfo.VerticeCoordinate[2 * i + 1]);
}

inkList.Add(gesture);
InkAnnotation a1 = new InkAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), inkList);
a1.Subject = "Test";
a1.Title = "Title";
a1.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
Border border = new Border(a1);
border.Width = 3;
border.Effect = BorderEffect.Cloudy;
border.Dash = new Dash(1, 1);
border.Style = BorderStyle.Solid;
doc.Pages[1].Annotations.Add(a1);

dataDir = dataDir + "lnkAnnotationLineWidth_out.pdf";
//保存输出文件
doc.Save(dataDir);
```

## 结论

在本教程中，我们学习了如何使用 Aspose.PDF for .NET 设置 PDF 文档中链接注释的线宽。 Aspose.PDF for .NET 提供了广泛的工具和功能来处理 PDF 文档，包括创建和自定义链接注释的能力。通过遵循分步指南并使用提供的 C# 源代码，开发人员可以轻松地向 PDF 文档添加交互式链接，从而增强应用程序的用户体验和交互性。 Aspose.PDF for .NET 是一个多功能库，使 .NET 开发人员能够高效且有效地处理 PDF 文件。

### 常见问题解答

#### 问：什么是PDF文档中的链接注释？

答：PDF 文档中的链接注释是一种交互式元素，允许您创建超链接或操作，将用户引导至同一文档中的另一个位置、外部网站或不同的 PDF 文档。

#### 问：如何使用 Aspose.PDF for .NET 设置链接注释的线宽？

答：要使用 Aspose.PDF for .NET 设置链接注释的线宽，您可以创建一个`InkAnnotation`对象并指定线宽属性。

#### 问：可以为 Aspose.PDF for .NET 中的链接注释自定义哪些属性？

答：您可以在 Aspose.PDF for .NET 中自定义链接注释的各种属性，例如其位置、大小、颜色、边框属性（宽度、样式、虚线图案和效果）、主题、标题和可见性。

#### 问：我可以创建包含多个墨迹手势的链接注释吗？

答：是的，您可以通过添加多个来创建包含多个墨迹手势的链接注释`Point`数组到`InkAnnotation`目的。

#### 问：如何为PDF文档的特定页面添加链接注释？

 A：要为PDF文档的特定页面添加链接注释，需要在创建PDF文档时指定页码`InkAnnotation`目的。例如，`new InkAnnotation(doc.Pages[1], ...)`将链接注释添加到第一页。