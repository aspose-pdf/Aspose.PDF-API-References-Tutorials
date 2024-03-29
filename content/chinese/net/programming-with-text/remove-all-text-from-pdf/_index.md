---
title: 删除 PDF 中的所有文本
linktitle: 删除 PDF 中的所有文本
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 从 PDF 文档中删除所有文本。
type: docs
weight: 290
url: /zh/net/programming-with-text/remove-all-text-from-pdf/
---
在本教程中，我们将解释如何使用 .NET 的 Aspose.PDF 库从 PDF 文档中删除所有文本。我们将逐步完成使用 PDF 打开 PDF 的过程`TextFragmentAbsorber`删除所有文本，并使用提供的 C# 源代码保存修改后的 PDF。

## 要求

在开始之前，请确保您具备以下条件：

- 安装了 Aspose.PDF for .NET 库。
- 对 C# 编程有基本了解。

## 第 1 步：设置文档目录

首先，您需要设置 PDF 文件所在目录的路径。代替`"YOUR DOCUMENT DIRECTORY"`在里面`dataDir`变量包含 PDF 文件的路径。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第 2 步：打开 PDF 文档

接下来，我们使用以下命令打开 PDF 文档`Document`来自 Aspose.PDF 库的类。

```csharp
Document pdfDocument = new Document(dataDir + "RemoveAllText.pdf");
```

## 第 3 步：删除所有文本

我们初始化一个`TextFragmentAbsorber`对象并使用它从 PDF 文档中删除所有吸收的文本。

```csharp
TextFragmentAbsorber absorb = new TextFragmentAbsorber();
absorb. RemoveAllText(pdfDocument);
```

## 第4步：保存修改后的PDF

最后，我们将修改后的PDF文档保存到指定的输出文件中。

```csharp
pdfDocument.Save(dataDir + "RemoveAllText_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

### 使用 Aspose.PDF for .NET 从 PDF 中删除所有文本的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//打开文档
Document pdfDocument = new Document(dataDir + "RemoveAllText.pdf");
//启动 TextFragmentAbsorber
TextFragmentAbsorber absorber = new TextFragmentAbsorber();
//删除所有吸收的文本
absorber.RemoveAllText(pdfDocument);
//保存文档
pdfDocument.Save(dataDir + "RemoveAllText_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

## 结论

在本教程中，您学习了如何使用 .NET 的 Aspose.PDF 库从 PDF 文档中删除所有文本。通过遵循分步指南并执行提供的 C# 代码，您可以打开 PDF，使用`TextFragmentAbsorber`，并保存修改后的PDF。

### 常见问题解答

#### 问：“删除 PDF 中的所有文本”教程的目的是什么？

答：“从 PDF 中删除所有文本”教程提供了有关如何使用 .NET 的 Aspose.PDF 库从 PDF 文档中删除所有文本的说明。本教程将指导您完成打开 PDF 的过程，使用`TextFragmentAbsorber`删除所有文本，并保存修改后的 PDF。

#### 问：为什么我要删除 PDF 文档中的所有文本？

答：在您需要创建不包含任何文本内容的文档版本的情况下，从 PDF 文档中删除所有文本非常有用。这对于隐私原因或生成文档布局的视觉表示而不显示其文本信息可能很有帮助。

#### 问：如何设置文档目录？

A：设置文档目录：

1. 代替`"YOUR DOCUMENT DIRECTORY"`在里面`dataDir`变量包含 PDF 文件所在目录的路径。

#### 问：如何使用 Aspose.PDF 库删除 PDF 文档中的所有文本？

答：本教程将逐步指导您完成整个过程：

1. 使用以下命令打开 PDF 文档`Document`班级。
2. 初始化一个`TextFragmentAbsorber`目的。
3. 使用吸收器删除 PDF 文档中所有吸收的文本。
4. 保存修改后的PDF文档。

#### 问：我可以有选择地删除文档特定区域的文本吗？

答：本教程的重点是从整个 PDF 文档中删除所有文本。如果您想有选择地从特定区域删除文本，则需要修改方法并使用更复杂的逻辑来识别和删除特定的文本片段。

#### 问：如何`TextFragmentAbsorber` work to remove text?

答： 的`TextFragmentAbsorber`是Aspose.PDF库提供的一个类，可以从PDF文档中吸收文本片段。通过使用`RemoveAllText`的方法`TextFragmentAbsorber`类，您可以从文档中删除所有吸收的文本片段。

#### 问：执行所提供的代码的预期结果是什么？

答：通过遵循教程并运行提供的 C# 代码，您将从输入 PDF 文档中删除所有文本，并将修改后的版本保存为输出 PDF 文件。

#### 问：我可以修改代码以仅删除特定页面或区域中的文本吗？

答：是的，您可以修改代码来实现这一点。对于选择性文本删除，您需要调整代码以定位 PDF 文档中的特定页面或区域。

#### 问：本教程需要有效的 Aspose 许可证吗？

答：是的，需要有效的 Aspose 许可证才能成功执行本教程中的代码。您可以从 Aspose 网站获取完整许可证或 30 天临时许可证。