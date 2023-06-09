---
title: 从邮票注释中提取文本
linktitle: 从邮票注释中提取文本
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 轻松地从 PDF 文档中的图章注释中提取文本。
type: docs
weight: 80
url: /zh/net/programming-with-stamps-and-watermarks/extract-text-from-stamp-annotation/
---
在本教程中，我们将逐步介绍如何使用 Aspose.PDF for .NET 从 PDF 文档中的图章注释中提取文本。我们将向您展示如何使用提供的 C# 源代码从 PDF 文档给定页面上的特定图章注释中提取文本。

## 第 1 步：设置环境

在开始之前，请确保您具备以下条件：

- 已安装的 .NET 开发环境。
- 在您的项目中下载并引用了用于 .NET 的 Aspose.PDF 库。

## 第 2 步：加载 PDF 文档

第一步是将现有的 PDF 文档加载到您的项目中。就是这样：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";

//装入文档
Document doc = new Document(dataDir + "test.pdf");
```

请务必将“您的文档目录”替换为您的 PDF 文档所在目录的实际路径。

## 第 3 步：从图章注释中提取文本

现在您已经加载了 PDF 文档，您可以从特定的图章注释中提取文本。就是这样：

```csharp
//检索缓冲区注释
StampAnnotation annot = doc.Pages[1].Annotations[3] as StampAnnotation;

//创建文本吸收器
TextAbsorber ta = new TextAbsorber();

//访问注解的外观
XForm ap = annot. Appearance["N"];
ta.Visit(ap);

//显示提取的文本
Console.WriteLine(ta.Text);
```

上面的代码从 PDF 文档的指定页面检索图章注释，然后使用文本吸收器从注释的外观中提取文本。提取的文本随后显示在输出中。

### 使用 Aspose.PDF for .NET 从图章注释中提取文本的示例源代码 
```csharp

string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "test.pdf");
StampAnnotation annot = doc.Pages[1].Annotations[3] as StampAnnotation;
TextAbsorber ta = new TextAbsorber();
XForm ap = annot.Appearance["N"];
ta.Visit(ap);
Console.WriteLine(ta.Text);

```

## 结论

恭喜！您已经学习了如何使用 Aspose.PDF for .NET 从 PDF 文档中的图章注释中提取文本。您现在可以使用此方法从 PDF 文档中的其他注释中提取文本。
