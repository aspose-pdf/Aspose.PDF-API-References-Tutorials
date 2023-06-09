---
title: 从区域获取字段
linktitle: 从区域获取字段
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 轻松地将特定区域的字段添加到您的 PDF 文档中。
type: docs
weight: 130
url: /zh/net/programming-with-forms/get-fields-from-region/
---

在本教程中，我们将向您展示如何使用 Aspose.PDF for .NET 获取 PDF 文档中特定区域的字段。我们将逐步解释 C# 源代码，以指导您完成此过程。

## 第一步：准备

确保您已导入必要的库并设置文档目录的路径：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第 2 步：打开 PDF 文件

打开 PDF 文件：

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document(dataDir + "GetFieldsFromRegion.pdf");
```

## 第 3 步：创建一个矩形对象来绑定区域

创建一个矩形对象来绑定要获取字段的区域：

```csharp
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(35, 30, 500, 500);
```

## 第四步：获取PDF表格

获取文档的PDF格式：

```csharp
Aspose.Pdf.Forms.Form form = doc.Form;
```

## 第五步：获取矩形区域的字段

获取位于指定矩形区域的字段：

```csharp
Aspose.Pdf.Forms.Field[] fields = form.GetFieldsInRect(rectangle);
```

## 步骤 6：显示字段名称和值

遍历结果字段并显示它们的名称和值：

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
//创建矩形对象以获取该区域中的字段
Aspose.Pdf.Rectangle rectangle = new Aspose.Pdf.Rectangle(35, 30, 500, 500);
//获取 PDF 表格
Aspose.Pdf.Forms.Form form = doc.Form;
//获取矩形区域中的字段
Aspose.Pdf.Forms.Field[] fields = form.GetFieldsInRect(rectangle);
//显示字段名称和值
foreach (Field field in fields)
{
	//显示所有展示位置的图片展示位置属性
	Console.Out.WriteLine("Field Name: " + field.FullName + "-" + "Field Value: " + field.Value);
}
```

## 结论

在本教程中，我们学习了如何使用 Aspose.PDF for .NET 获取 PDF 文档中特定区域的字段。按照这些步骤，您可以使用 Aspose.PDF 轻松提取位于 PDF 文档给定矩形区域中的字段。