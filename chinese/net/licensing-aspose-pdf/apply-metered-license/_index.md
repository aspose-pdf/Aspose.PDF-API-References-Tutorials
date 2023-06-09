---
title: 配置计量许可证
linktitle: 配置计量许可证
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 设置计量许可证并从高级功能中受益的分步指南。
type: docs
weight: 10
url: /zh/net/licensing-aspose-pdf/configure-metered-license/
---

在本教程中，我们将逐步指导您如何使用 Aspose.PDF for .NET 设置计量许可证。计量许可证允许您根据您的实际消费使用 Aspose.PDF 的高级功能。

### 第 1 步：配置许可证密钥

在提供的源代码中，您必须指定计量许可证的公钥和私钥。更换 ”*****" 值与您自己的密钥。当您从 Aspose 购买计量许可证时，这些密钥将提供给您。

```csharp
Aspose.Pdf.Metered metered = new Aspose.Pdf.Metered();
metered.SetMeteredKey("PUBLIC_KEY", "PRIVATE_KEY");
```

### 第 2 步：装入文档

使用从磁盘加载 PDF 文档`Document`Aspose.PDF 类。

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

### 第 3 步：获取文档页数

使用`Count`的财产`Pages`collection 获取文档中的总页数。

```csharp
Console.WriteLine(doc.Pages.Count);
```

### 使用 Aspose.PDF for .NET 配置计量许可证的示例源代码 

```csharp

//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//设置计量公钥和私钥
Aspose.Pdf.Metered metered = new Aspose.Pdf.Metered();
//访问 setMeteredKey 属性并将公钥和私钥作为参数传递
metered.SetMeteredKey("*****", "*****");
//从磁盘加载文档。
Document doc = new Document(dataDir + "input.pdf");
//获取文档的页数
Console.WriteLine(doc.Pages.Count);

```

## 结论

在本教程中，我们解释了如何使用 Aspose.PDF for .NET 设置计量许可证。通过使用计量许可证，您可以根据实际使用情况受益于 Aspose.PDF 的高级功能。确保提供有效的许可证密钥以使用 Aspose.PDF 及其所有功能。
