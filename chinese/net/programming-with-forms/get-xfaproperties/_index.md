---
title: 获取 XFA 属性
linktitle: 获取 XFA 属性
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 轻松获取 PDF 文档中表单域的 XFA 属性。
type: docs
weight: 160
url: /zh/net/programming-with-forms/get-xfaproperties/
---

在本教程中，我们将向您展示如何使用 Aspose.PDF for .NET 获取 PDF 文档中表单域的 XFA 属性。我们将逐步解释 C# 源代码，以指导您完成此过程。

## 第一步：准备

确保您已导入必要的库并设置文档目录的路径：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第 2 步：加载 XFA 表单

从 PDF 文档加载 XFA 表单：

```csharp
Document doc = new Document(dataDir + "GetXFAProperties.pdf");
```

## 第 3 步：获取字段名称

获取 XFA 字段名称：

```csharp
string[] names = doc.Form.XFA.FieldNames;
```

## 第 4 步：设置字段值

为 XFA 字段设置值：

```csharp
doc.Form.XFA[names[0]] = "Field 0";
doc.Form.XFA[names[1]] = "Field 1";
```

## 第 5 步：获取字段位置

获取 XFA 字段的位置：

```csharp
Console.WriteLine(doc.Form.XFA.GetFieldTemplate(names[0]).Attributes["x"].Value);
Console.WriteLine(doc.Form.XFA.GetFieldTemplate(names[0]).Attributes["y"].Value);
```

## 第 6 步：保存更新后的文档

保存更新后的 PDF 文档：

```csharp
dataDir = dataDir + "Filled_XFA_out.pdf";
doc.Save(dataDir);
```

### 使用 Aspose.Words for .NET 获取 XFAProperties 的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//加载 XFA 表单
Document doc = new Document(dataDir + "GetXFAProperties.pdf");
string[] names = doc.Form.XFA.FieldNames;
//设置字段值
doc.Form.XFA[names[0]] = "Field 0";
doc.Form.XFA[names[1]] = "Field 1";
//获取字段位置
Console.WriteLine(doc.Form.XFA.GetFieldTemplate(names[0]).Attributes["x"].Value);
//获取字段位置
Console.WriteLine(doc.Form.XFA.GetFieldTemplate(names[0]).Attributes["y"].Value);
dataDir = dataDir + "Filled_XFA_out.pdf";
//保存更新的文档
doc.Save(dataDir);
Console.WriteLine("\nXFA fields properties retrieved successfully.\nFile saved at " + dataDir);
```

## 结论

在本教程中，我们学习了如何使用 Aspose.PDF for .NET 获取 PDF 文档中表单域的 XFA 属性。按照这些步骤，您可以使用 Aspose.PDF 轻松地从 PDF 文档中提取 XFA 字段信息，例如位置。