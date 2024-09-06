---
title: PDF 文档中的圆角表格
linktitle: PDF 文档中的圆角表格
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 文档中创建圆角表格。
type: docs
weight: 190
url: /zh/net/programming-with-tables/rounded-corner-table/
---
在本教程中，我们将逐步指导您使用 Aspose.PDF for .NET 在 PDF 文档中创建圆角表格。我们将解释提供的 C# 源代码并向您展示如何实现它。

## 步骤 1：创建表
首先，我们将使用以下代码创建表：

```csharp
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();
```

## 步骤 2：圆角样式设置
接下来我们来配置表格的圆角样式：

```csharp
tab1.CornerStyle = Aspose.Pdf.BorderCornerStyle.Round;
```

## 步骤 3：表格边框设置
为了给表格添加圆角边框，我们需要创建一个 BorderInfo 对象并使用适当的参数进行配置：

```csharp
//创建 GraphInfo 对象来设置边框颜色
GraphInfo graph = new GraphInfo();
graph.Color = Aspose.Pdf.Color.Red;

//创建一个空的 BorderInfo 对象
BorderInfo bInfo = new BorderInfo(BorderSide.All, graph);

//将圆角边框的半径设置为 15
bInfo.RoundedBorderRadius = 15;

//将边框信息应用于表格
tab1.Border = bInfo;
```

### 使用 Aspose.PDF for .NET 的圆角表示例源代码

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
Aspose.Pdf.Table tab1 = new Aspose.Pdf.Table();

GraphInfo graph = new GraphInfo();
graph.Color = Aspose.Pdf.Color.Red;
//创建空白的 BorderInfo 对象
BorderInfo bInfo = new BorderInfo(BorderSide.All, graph);
//将边框设置为圆角边框，圆角半径为 15
bInfo.RoundedBorderRadius = 15;
//将表格角样式设置为圆形。
tab1.CornerStyle = Aspose.Pdf.BorderCornerStyle.Round;
//设置表格边框信息
tab1.Border = bInfo;
```

## 结论
恭喜！您现在已经学会了如何使用 Aspose.PDF for .NET 在 PDF 文档中创建圆角表格。本分步指南向您展示了如何设置圆角样式和表格边框。现在您可以将这些知识应用到您自己的项目中。

### PDF 文档中圆角表格的常见问题解答

#### 问：我可以自定义表格圆角半径吗？

答：是的，您可以通过修改`bInfo.RoundedBorderRadius`提供的 C# 源代码中的属性。只需设置所需的半径值（以点为单位）即可实现所需的圆角外观。

#### 问：我可以为表格中的单个单元格应用圆角吗？

答：不，圆角样式会应用于整个表格。Aspose.PDF for .NET 目前不提供对表格中单个单元格应用圆角的内置支持。

#### 问：我可以改变圆角边框的颜色吗？

答：是的，你可以通过修改`graph.Color`属性。只需提供所需的颜色，例如`Aspose.Pdf.Color.Red`或任何其他有效的颜色表示。

#### 问：是否可以对同一 PDF 文档内的不同表格应用不同的角落样式（例如方形和圆形）？

答：是的，可以对同一 PDF 文档中的不同表格应用不同的角样式。您可以创建多个表格并根据您的需求分别配置其角样式。

#### 问：我可以调整圆角边框的粗细吗？

答：是的，您可以通过修改`BorderInfo`在 C# 源代码中设置对象的属性。例如，您可以设置`bInfo.Width`属性来调整边框的粗细。