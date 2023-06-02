---
title: lnk 注释行宽
linktitle: lnk 注释行宽
second_title: Aspose.PDF for .NET API 参考
description: 本文提供了使用 Aspose.PDF for .NET 设置 lnk 注释线宽的分步指南。
type: docs
weight: 110
url: /zh/net/annotations/lnkannotationlinewidth/
---
Aspose.PDF 是一个功能强大且广泛使用的工具，用于在 .NET 应用程序中处理 PDF 文件。它提供了多种用于创建、编辑和操作 PDF 文件的功能，包括向页面添加注释的能力。在本教程中，我们将解释如何使用 Aspose.PDF for .NET 设置链接注释的线宽。

具备这些先决条件后，在 Visual Studio 中创建一个新的控制台应用程序项目。然后，通过在解决方案资源管理器中右键单击该项目，选择“管理 NuGet 包”并在 NuGet 包管理器中搜索“Aspose.PDF”，添加对 Aspose.PDF for .NET 库的引用。

要向 PDF 文档添加 lnk 注释，请按照下列步骤操作：

## 第 1 步：创建一个新的`Document` object.
```csharp
Document doc = new Document();
```
## 第 2 步：向文档添加新页面。
```csharp
doc.Pages.Add();
```
## 第 3 步：创建列表`Point` arrays that represent the ink gesture for the annotation.
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
## 第 6 步：将手势添加到墨迹手势列表中。
```csharp
inkList.Add(gesture);
```
## 第 7 步：创建一个新的`InkAnnotation` object that represents the link annotation.
```csharp
InkAnnotation a1 = new InkAnnotation(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 100, 300, 300), inkList);
```
## 第八步：设置批注的主题和标题。
```csharp
a1.Subject = "Test";
a1.Title = "Title";
```
## 第九步：设置注释的颜色。
```csharp
a1.Color = Aspose.Pdf.Color.FromRgb(System.Drawing.Color.Green);
```
## 第 10 步：创建一个新的`Border` object that defines the properties of the annotation's border.
```csharp
Border border = new Border(a1);
border.Width = 3;
border.Effect = BorderEffect.Cloudy;
border.Dash = new Dash(1, 1);
border.Style = BorderStyle.Solid;
```
## 第 11 步：将注释添加到页面。
```csharp
doc.Pages[1].Annotations.Add(a1);
```
## 第 12 步：将文档保存到文件中。
```csharp
//保存输出文件
doc.Save(dataDir);


```
### 该示例显示了用于 .NET 的 Aspose.PDF 的 lnk 注释线宽

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
