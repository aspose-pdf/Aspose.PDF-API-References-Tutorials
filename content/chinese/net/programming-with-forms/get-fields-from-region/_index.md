---
title: 获取 PDF 文件中区域的字段
linktitle: 获取 PDF 文件中区域的字段
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 轻松获取 PDF 文件中特定区域的字段。
type: docs
weight: 130
url: /zh/net/programming-with-forms/get-fields-from-region/
---
在本教程中，我们将向您展示如何使用 Aspose.PDF for .NET 获取 PDF 文件中特定区域的字段。我们将逐步解释 C# 源代码以指导您完成此过程。

## 步骤 1：准备

确保您已导入必要的库并设置文档目录的路径：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第 2 步：打开 PDF 文件

打开 PDF 文件：

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "GetFieldsFromRegion.pdf");
```

## 步骤 3：创建一个矩形对象来限制区域

创建一个矩形对象来限制您想要获取字段的区域：

```csharp
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(35, 30, 500, 500);
```

## 步骤 4：获取 PDF 表单

获取文档的 PDF 格式：

```csharp
Aspose.Pdf.Forms.Form form = doc.Form;
```

## 步骤 5：获取矩形区域内的字段

获取位于指定矩形区域内的字段：

```csharp
Aspose.Pdf.Forms.Field[] fields = form.GetFieldsInRect(rectangle);
```

## 步骤 6：显示字段名称和值

遍历结果字段并显示其名称和值：

```csharp
foreach (Field field in fields)
{
Console.Out.WriteLine("Field name: " + field.FullName + "-" + "Field value: " + field.Value);
}
```

### 使用 Aspose.PDF for .NET 从区域获取字段的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//打开 pdf 文件
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "GetFieldsFromRegion.pdf");
//创建矩形对象以获取该区域内的字段
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(35, 30, 500, 500);
//获取 PDF 表单
Aspose.Pdf.Forms.Form form = doc.Form;
//获取矩形区域内的字段
Aspose.Pdf.Forms.Field[] fields = form.GetFieldsInRect(rectangle);
//显示字段名称和值
foreach (Field field in fields)
{
	//显示所有展示位置的图片展示位置属性
	Console.Out.WriteLine("Field Name: " + field.FullName + "-" + "Field Value: " + field.Value);
}
```

## 结论

在本教程中，我们学习了如何使用 Aspose.PDF for .NET 获取 PDF 文档中特定区域的字段。通过遵循这些步骤，您可以使用 Aspose.PDF 轻松提取位于 PDF 文档给定矩形区域中的字段。

### 常见问题解答

#### 问：我可以使用此方法获取 PDF 文档中非矩形区域的字段吗？

答：不是，提供的方法`GetFieldsInRect`专门用于检索 PDF 文档中矩形区域内的字段。如果您需要从非矩形区域中提取字段，则需要实现自定义逻辑，以根据其他条件（例如字段坐标或名称）识别和提取字段。

#### 问：如何修改矩形的大小或位置以获取来自不同区域的字段？

答：要获取不同区域的字段，您可以修改`Aspose.Pdf.Rectangle`对象的参数用于定义边界矩形。`Rectangle`构造函数有四个参数：`x`, `y`, `width`， 和`height`，代表矩形的左上角坐标和尺寸。调整这些参数将改变提取字段的区域。

#### 问：如果指定的矩形区域内没有田地怎么办？

答：如果指定的矩形区域内没有字段，则`GetFieldsInRect`方法将返回一个空数组。您可以检查数组的长度来确定区域内是否有任何字段。

#### 问：我可以从 PDF 文档中的重叠区域获取字段吗？

答：是的，您可以通过创建多个`Aspose.Pdf.Rectangle`对象并调用`GetFieldsInRect`方法。重叠区域将被单独处理，您将收到每个区域的单独字段数组。

#### 问：是否可以从 PDF 文档中的特定页面或多个页面获取字段？

答：是的，您可以从 PDF 文档中的特定页面或多个页面获取字段。为此，您可以加载 PDF 文档，使用`doc.Pages`集合，然后应用`GetFieldsInRect`方法到每个页面的特定区域。