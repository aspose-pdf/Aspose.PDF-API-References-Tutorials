---
title: 在 PDF 文件中配置计量许可证密钥
linktitle: 在 PDF 文件中配置计量许可证密钥
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 在 PDF 文件中设置计量许可证密钥并受益于高级功能的分步指南。
type: docs
weight: 10
url: /zh/net/licensing-aspose-pdf/configure-metered-license/
---
在本教程中，我们将逐步引导您了解如何使用 Aspose.PDF for .NET 在 PDF 文件中设置计量许可证密钥。计量许可证允许您根据实际用量使用 Aspose.PDF 的高级功能。

### 第 1 步：配置许可证密钥

在提供的源代码中，您必须指定计量许可证的公钥和私钥。更换 ”*****“值与您自己的密钥。当您从 Aspose 购买计量许可证时，将向您提供这些密钥。

```csharp
Aspose.Pdf.Metered metered = new Aspose.Pdf.Metered();
metered.SetMeteredKey("PUBLIC_KEY", "PRIVATE_KEY");
```

### 第 2 步：加载文档

使用以下命令从磁盘加载 PDF 文档`Document`Aspose.PDF 类。

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

### 第 3 步：获取文档页数

使用`Count`的财产`Pages`集合以获取文档中的总页数。

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

在本教程中，我们解释了如何使用 Aspose.PDF for .NET 设置计量许可证。通过使用计量许可证，您可以根据实际使用情况从 Aspose.PDF 的高级功能中受益。确保提供有效的许可证密钥以使用 Aspose.PDF 及其所有功能。

### 在 PDF 文件中配置计量许可证密钥的常见问题解答

#### 问：Aspose.PDF 中的计量许可证是什么？

答：Aspose.PDF 中的计量许可证是一种许可模式，允许您根据实际使用的功能而不是固定的许可费来付费。它使您能够使用 Aspose.PDF 的高级功能，同时只需为您使用的内容付费。

#### 问：为什么我应该使用 Aspose.PDF 的计量许可证？

答：使用计量许可证可以节省成本并提高灵活性。您只需为您使用的功能付费，使其适合具有不同需求的项目。它无需预先支付许可费用，并允许您访问高级 PDF 功能。

#### 问：如何获取计量许可证密钥？

答：当您从 Aspose 购买计量许可证时，您将收到一对公钥和私钥。这些密钥将用于验证您的 Aspose.PDF 应用程序并启用计量许可。

#### 问：如何在 Aspose.PDF for .NET 中配置计量许可证密钥？

答：要配置计量许可证密钥，请使用`SetMeteredKey`的方法`Aspose.Pdf.Metered`班级。代替`"PUBLIC_KEY"`和`"PRIVATE_KEY"`用你的实际钥匙。

```csharp
Aspose.Pdf.Metered metered = new Aspose.Pdf.Metered();
metered.SetMeteredKey("PUBLIC_KEY", "PRIVATE_KEY");
```

#### 问：如何使用 Aspose.PDF for .NET 加载 PDF 文档？

答：要从磁盘加载 PDF 文档，请使用`Document`Aspose.PDF 类并提供文件路径。

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

#### 问：如何获取 PDF 文档的总页数？

答：要获取 PDF 文档的总页数，请使用`Count`的财产`Pages`收藏。

```csharp
int pageCount = doc.Pages.Count;
Console.WriteLine("Total pages: " + pageCount);
```

#### 问：我可以对其他 Aspose 产品使用计量许可吗？

答：是的，各种 Aspose 产品均提供计量许可，允许您根据各种功能的使用情况付费。

#### 问：计量许可证是否适合所有类型的项目？

答：计量许可适用于具有不同功能使用情况的项目。对于具有一致、高功能使用的项目来说，这可能不具有成本效益。

#### 问：在哪里可以找到有关 Aspose.PDF 计量许可的更多信息？

答：有关计量许可、定价和优势的更多信息，请访问[Aspose.PDF 计量许可](https://purchase.aspose.com/pricing/pdf/net)页。

#### 问：如何确保计量许可证密钥的安全？

答：计量许可证密钥用于身份验证，属于敏感信息。确保它们保密并且不公开分享。

#### 问：我可以在传统许可和计量许可之间切换吗？

答：是的，您可以根据项目的要求在 Aspose.PDF 的传统许可和计量许可之间切换。

#### 问：在购买计量许可证之前我可以使用试用版吗？

答： 是的，你可以尝试一下[免费试用版](https://products.aspose.com/pdf/net)在购买计量许可证之前，使用 Aspose.PDF 来评估其特性和功能。

#### 问：我应该多久配置一次计量许可证密钥？

答：您只需在应用程序启动时配置一次计量许可证密钥。它允许在应用程序的整个运行时访问高级功能。

#### 问：我可以对现有应用程序应用计量许可吗？

答：是的，您可以将计量许可集成到现有的 Aspose.PDF 应用程序中，以受益于其优势。