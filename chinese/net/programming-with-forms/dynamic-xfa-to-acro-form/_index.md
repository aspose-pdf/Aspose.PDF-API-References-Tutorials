---
title: 动态 XFA 到 Acro 形式
linktitle: 动态 XFA 到 Acro 形式
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 轻松将动态 XFA To 表单转换为标准 AcroForm 表单。
type: docs
weight: 70
url: /zh/net/programming-with-forms/dynamic-xfa-to-acro-form/
---

在本教程中，我们将向您展示如何使用 Aspose.PDF for .NET 将 XFA 动态表单转换为 AcroForm。我们将逐步解释 C# 源代码，以指导您完成此过程。

## 第一步：准备

首先，确保您已导入必要的库并设置文档目录的路径：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：加载动态 XFA 表单

加载动态 XFA 表单：

```csharp
Document document = new Document(dataDir + "DynamicXFAToAcroForm.pdf");
```

## 第 3 步：将表单类型设置为标准 AcroForm

将表单类型设置为标准 AcroForm：

```csharp
document.Form.Type = FormType.Standard;
```

## 第 4 步：保存生成的 PDF

保存生成的 PDF：

```csharp
dataDir = dataDir + "Standard_AcroForm_out.pdf";
document. Save(dataDir);
```

### 使用 Aspose.PDF for .NET 的动态 XFA 到 Acro 表单的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//加载动态 XFA 表单
Document document = new Document(dataDir + "DynamicXFAToAcroForm.pdf");
//将表单字段类型设置为标准 AcroForm
document.Form.Type = FormType.Standard;
dataDir = dataDir + "Standard_AcroForm_out.pdf";
//保存生成的 PDF
document.Save(dataDir);
Console.WriteLine("\nDynamic XFA form converted to standard AcroForm successfully.\nFile saved at " + dataDir);
```

## 结论

在本教程中，我们学习了如何使用 Aspose.PDF for .NET 将 XFA To 动态表单转换为标准的 AcroForm 表单。通过执行这些步骤，您可以轻松地将动态 XFATo 表单转换为 AcroForms 以供更常见的使用。