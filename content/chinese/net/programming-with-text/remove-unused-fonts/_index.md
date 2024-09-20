---
title: 删除 PDF 文件中未使用的字体
linktitle: 删除 PDF 文件中未使用的字体
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 轻松从 PDF 文件中删除未使用的字体。提高性能并减小文件大小。
type: docs
weight: 300
url: /zh/net/programming-with-text/remove-unused-fonts/
---
## 介绍

嗨！您是否厌倦了充斥着字体的臃肿 PDF 文件，这些字体占用了不必要的空间？您并不孤单！管理 PDF 中的字体使用可能很麻烦，尤其是当您希望文档干净高效时。好消息是，使用 Aspose.PDF for .NET，您可以轻松地从 PDF 文件中删除未使用的字体，从而提高性能并减小文件大小。在本教程中，我们将逐步介绍该过程，以便您简化 PDF 文件管理。

## 先决条件

在开始之前，请确保您已完成以下设置，以充分利用本教程：

1. 已安装 Visual Studio：您需要一个开发环境来运行 .NET 代码。Visual Studio（任何版本）都是不错的选择。
2.  Aspose.PDF for .NET：请确保您已安装此库。您可以下载它[这里](https://releases.aspose.com/pdf/net/).
3. 对 C# 的基本了解：由于我们将在本示例中使用 C#，因此熟悉该语言将会很有用。
4. PDF 文件：准备好一个示例 PDF 文件。您可以创建自己的 PDF 文件或使用任何现有的 PDF。只需确保它被命名为`ReplaceTextPage.pdf`并存储在您的文档目录中。
5. 有效许可证：虽然您可以使用免费试用版，但建议使用有效许可证才能获得完整功能。如果您需要临时许可证，可以获取[这里](https://purchase.aspose.com/temporary-license/).

## 导入包

现在我们已经满足了先决条件，让我们将必要的包导入到我们的 C# 项目中。以下是您需要的内容：

Aspose.PDF 命名空间：它提供了处理 PDF 文件的所有基本功能。

```csharp
using System.IO;
using Aspose.Pdf;
using Aspose.Pdf.Text;
using System;
```

要导入这些，请在 C# 文件的顶部添加上述行。这将授予您访问我们用于操作 PDF 文档的类和方法的权限。

## 步骤 1：设置项目环境

首先！您需要在 Visual Studio 中创建一个新的控制台应用程序。请按照以下步骤操作：

- 打开 Visual Studio。
- 单击文件 > 新建 > 项目。
- 选择控制台应用程序（.NET Framework）并为其命名（例如，`PdfFontCleaner`）。
- 单击“创建”。

现在您有一个全新的项目可以开始了！

## 第 2 步：添加 Aspose.PDF 库

接下来，您将把 Aspose.PDF 库添加到您的项目中。您可以通过 NuGet 执行此操作：

1. 在解决方案资源管理器中，右键单击您的项目。
2. 选择管理 NuGet 包。
3. 搜索`Aspose.PDF`并安装它。

## 步骤 3：加载 PDF 文档

让我们加载要处理的文档。操作方法如下：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY/"; //将其更新到您的路径
//加载源 PDF 文件
Document doc = new Document(dataDir + "ReplaceTextPage.pdf");
```

代替`"YOUR DOCUMENT DIRECTORY/"`替换为 PDF 文件存储的实际路径。此步骤至关重要，因为它允许 Aspose 访问您的 PDF 文档。 

## 步骤 4：设置文本片段吸收器

接下来，我们将设置一个处理器，帮助我们识别并删除 PDF 中未使用的字体。以下是执行此操作的代码：

```csharp
TextFragmentAbsorber absorber = new TextFragmentAbsorber(new TextEditOptions(TextEditOptions.FontReplace.RemoveUnusedFonts));
doc.Pages.Accept(absorber);
```

这行代码创建一个`TextFragmentAbsorber`配置为删除未使用的字体的对象。通过调用`doc.Pages.Accept(absorber)`，我们告诉 Aspose 浏览文档中的所有页面并识别文本片段。

## 步骤 5：遍历文本片段并替换字体

识别文本片段后，就该遍历它们并替换任何未使用的字体了。添加以下代码：

```csharp
//遍历所有 TextFragments
foreach (TextFragment textFragment in absorber.TextFragments)
{
    textFragment.TextState.Font = FontRepository.FindFont("Arial, Bold");
}
```

在此循环中，你将更改每个`TextFragment`改为“Arial，Bold”。您可以选择任何适合您需要的字体。这才是真正的魔力所在，因为它可以确保 PDF 保留干净、清晰的字体。

## 步骤 6：保存更新后的文档

现在我们已经完成了必要的更改，让我们保存更新的 PDF！添加以下代码：

```csharp
dataDir = dataDir + "RemoveUnusedFonts_out.pdf";
//保存更新的文档
doc.Save(dataDir);
Console.WriteLine("\nUnused fonts removed successfully from pdf document.\nFile saved at " + dataDir);
```

在这里我们创建一个名为`RemoveUnusedFonts_out.pdf`在同一目录中。这样可以备份原始 PDF，同时仍提供精简版本。

## 步骤 7：处理异常

最后，建立错误处理始终是一个好主意。这里有一个简单的 try-catch 块来包装你的代码：

```csharp
try
{
    // ...（前一个代码）
}
catch (Exception ex)
{
    Console.WriteLine(ex.Message + "\nThis example will only work if you apply a valid Aspose License. You can purchase full license or get 30-day temporary license from https://购买.aspose.com”。）
}
```

这将捕获过程中发生的任何异常并提供用户友好的错误消息。告知用户相关要求（例如需要有效的 Aspose 许可证）至关重要。

## 结论

恭喜！您已成功学会如何使用 Aspose.PDF for .NET 从 PDF 文件中删除未使用的字体。按照上面概述的步骤，您可以使您的 PDF 文件更精简、更整洁，确保它们更高效、更用户友好。不要忘记探索 Aspose.PDF 的其他功能，以进一步增强您的文档处理能力！

## 常见问题解答

### 我可以使用 Aspose.PDF 的免费版本来完成这项任务吗？
是的，您可以使用免费试用版，但为了获得最佳性能，建议使用完整许可证。

### 如果没有可用的替代品，字体会怎么样？
如果找不到替换字体，文本可能无法正确显示，因此请务必选择常用的字体。

### 如何取得临时执照？
您可以从申请临时许可证[这里](https://purchase.aspose.com/temporary-license/).

### 删除未使用的字体会影响文档的外观吗？
这取决于删除了哪些字体以及如何替换文本片段；鼓励进行测试。

### 是否有其他方法可以删除未使用的字体？
尽管其他库或工具可能提供类似的功能，但 Aspose.PDF for .NET 在这方面非常高效。