---
title: 动态 XFA 到 Acro 表单
linktitle: 动态 XFA 到 Acro 表单
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 轻松将动态 XFA To 表单转换为标准 AcroForm 表单。
type: docs
weight: 70
url: /zh/net/programming-with-forms/dynamic-xfa-to-acro-form/
---
在本教程中，我们将向您展示如何使用 Aspose.PDF for .NET 将 XFA To 动态表单转换为 AcroForm。我们将逐步解释 C# 源代码，以指导您完成此过程。

## 第 1 步：准备

首先，确保您已导入必要的库并设置文档目录的路径：

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：加载动态 XFA 表单

加载动态XFA表单：

```csharp
Document document = new Document(dataDir + "DynamicXFAToAcroForm.pdf");
```

## 步骤 3：将表单类型设置为 Standard AcroForm

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

### 使用 Aspose.PDF for .NET 的 Dynamic XFA To Acro Form 的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//加载动态XFA表单
Document document = new Document(dataDir + "DynamicXFAToAcroForm.pdf");
//将表单字段类型设置为标准 AcroForm
document.Form.Type = FormType.Standard;
dataDir = dataDir + "Standard_AcroForm_out.pdf";
//保存生成的 PDF
document.Save(dataDir);
Console.WriteLine("\nDynamic XFA form converted to standard AcroForm successfully.\nFile saved at " + dataDir);
```

## 结论

在本教程中，我们学习了如何使用 Aspose.PDF for .NET 将 XFA To 动态表单转换为标准 AcroForm 表单。通过执行这些步骤，您可以轻松地将动态 XFATo 表单转换为 AcroForms 以供更常见的使用。

### 常见问题解答

#### 问：动态 XFA 表单和标准 AcroForm 有什么区别？

答：动态 XFA（XML 表单架构）表单是一种 PDF 表单，它使用基于 XML 的数据来定义其布局和行为。 XFA 表单通常用于交互式和数据密集型表单。另一方面，标准 AcroForm 是一种更传统的 PDF 表单类型，它使用 PDF 格式本身来定义其结构和外观。 AcroForms 受到 PDF 查看器的广泛支持，并且可以与各种应用程序更加兼容。

#### 问：为什么我要将动态 XFA 表单转换为标准 AcroForm？

答：在不完全支持 XFA 表单的情况下，或者当您想要实现与不同 PDF 查看器和应用程序的更大兼容性时，将动态 XFA 表单转换为标准 AcroForm 非常有用。标准 AcroForms 通常在不同平台和设备上得到更广泛的支持。

#### 问：将动态 XFA 表单转换为标准 AcroForm 后可以修改表单字段吗？

答：是的，将动态 XFA 表单转换为标准 AcroForm 后，您可以使用 Aspose.PDF for .NET 根据需要修改表单字段。您可以添加新字段、更改其属性、设置字段值以及执行其他与表单相关的操作。

#### 问：将动态 XFA 表单转换为标准 AcroForms 时是否有任何限制或注意事项？

答：是的，将动态 XFA 表单转换为标准 AcroForms 时需要考虑一些限制。 XFA 表单可以具有复杂且动态的布局，包括动态表格、重复部分和表单计算等功能，这些功能在转换过程中可能无法完全保留。此外，XFA 表单独有的某些特定表单字段属性可能不适用于 AcroForms。

#### 问：我可以使用 Aspose.PDF for .NET 将标准 AcroForm 转换为动态 XFA 表单吗？

答：Aspose.PDF for .NET 目前支持将动态 XFA 表单转换为标准 AcroForms，但不支持将标准 AcroForms 转换为动态 XFA 表单的反向操作。将标准 AcroForms 转换为动态 XFA 表单涉及更复杂的转换，并且可能无法在所有场景中得到完全支持。