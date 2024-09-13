---
title: 使用签名字段通过智能卡签名
linktitle: 使用签名字段通过智能卡签名
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 的智能卡安全地签署 PDF。按照我们的分步指南轻松实施。
type: docs
weight: 120
url: /zh/net/programming-with-security-and-signatures/sign-with-smart-card-using-signature-field/
---
## 介绍

在当今的数字世界中，保护文档比以往任何时候都更加重要。无论您是开发人员、企业主还是只是处理敏感信息的人，了解如何以电子方式签署 PDF 都可以节省您的时间并确保您的文档经过验证。在本指南中，我们将引导您完成使用智能卡和 Aspose.PDF for .NET 签名字段签署 PDF 的过程。 

## 先决条件

在我们深入了解签署流程的细节之前，让我们先确保您已准备好开始签署所需的一切。以下是先决条件清单：

1. Aspose.PDF for .NET：确保您已在 .NET 环境中安装了 Aspose.PDF 库。您可以从[地点](https://releases.aspose.com/pdf/net/).

2. Visual Studio：您需要一个 IDE 来编写和运行 .NET 代码。Visual Studio 社区版是一个很棒的免费选择。

3. 智能卡：这是签署 PDF 所必需的。确保您的机器上安装了智能卡读卡器和必要的证书。

4. 基本 C# 知识：熟悉 C# 编程将帮助您理解我们将使用的代码片段。

5. 示例 PDF 文档：准备一个示例 PDF 文档以供测试。您可以创建一个空白 PDF 或使用现有的 PDF。

## 导入包

在开始编码之前，让我们导入必要的包。您需要在 C# 文件中包括以下命名空间：

```csharp
using Aspose.Pdf.Facades;
using Aspose.Pdf.Forms;
using System;
using System.Collections.Generic;
using System.IO;
using System.Linq;
using System.Text;
```

这些命名空间将使您能够访问处理 PDF 和数字签名所需的类和方法。

## 使用智能卡签署 PDF 的分步指南

现在我们已经了解了先决条件，让我们将签名过程分解为可管理的步骤。我们将详细介绍每个步骤，确保您了解幕后发生的事情。

### 步骤 1：设置文档目录

要做什么：定义文档目录的路径。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

解释：替换`"YOUR DOCUMENTS DIRECTORY"`替换为 PDF 文件所在的实际路径。我们将在此处读取空白 PDF 并保存已签名的文档。

### 第 2 步：复制空白 PDF

操作方法：创建一份空白 PDF 副本以供使用。

```csharp
File.Copy(dataDir + "blank.pdf", dataDir + "externalSignature1.pdf", true);
```

解释：此行复制`blank.pdf`文件到名为`externalSignature1.pdf` 。 这`true`如果文件已经存在，参数允许覆盖。

### 步骤 3：打开 PDF 文档

操作方法：打开复制的 PDF 进行阅读和书写。

```csharp
using (FileStream fs = new FileStream(dataDir + "externalSignature1.pdf", FileMode.Open, FileAccess.ReadWrite))
{
    using (Document doc = new Document(fs))
    {
        //后续步骤将在此处进行
    }
}
```

解释：我们使用`FileStream`打开我们的 PDF 文件。`Document` Aspose.PDF 中的类允许我们操作 PDF 内容。

### 步骤 4：创建签名字段

操作方法：在 PDF 中定义一个用于放置签名的签名字段。

```csharp
SignatureField field1 = new SignatureField(doc.Pages[1], new Rectangle(100, 400, 10, 10));
```

解释：在这里，我们创建一个`SignatureField`在 PDF 的第二页（页面索引从 1 开始）。`Rectangle`定义签名字段的位置和大小。

### 步骤 5：访问智能卡证书存储

操作方法：打开证书存储区以选择您的智能卡证书。

```csharp
X509Store store = new X509Store(StoreLocation.CurrentUser);
store.Open(OpenFlags.ReadOnly);
```

解释：我们访问当前用户的证书存储区。这是存储您的智能卡证书的地方。

### 步骤 6：选择证书

要做什么：提示用户从商店中选择一个证书。

```csharp
X509Certificate2Collection sel = X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, X509SelectionFlag.SingleSelection);
```

解释：此行将打开一个对话框供您选择证书。您可以选择与您的智能卡关联的证书。

### 步骤 7：创建外部签名

要做什么：创建一个实例`ExternalSignature`使用选定的证书。

```csharp
Aspose.Pdf.Forms.ExternalSignature externalSignature = new Aspose.Pdf.Forms.ExternalSignature(sel[0])
{
    Authority = "Me",
    Reason = "Reason",
    ContactInfo = "Contact"
};
```

解释：我们初始化`ExternalSignature`使用所选证书进行签名。您还可以设置授权机构、签名原因和联系信息。

### 步骤 8：将签名字段添加到文档

操作方法：将签名字段添加到文档中。

```csharp
field1.PartialName = "sig1";
doc.Form.Add(field1, 1);
```

解释：我们给签名字段命名，并将其添加到文档的第一页。这为 PDF 签名做好了准备。

### 第 9 步：签署文件

操作方法：使用外部签名对 PDF 进行签名。

```csharp
field1.Sign(externalSignature);
doc.Save();
```

说明：此行使用外部签名对文档进行签名，并将更改保存到 PDF。您的文档现已签名！

### 步骤 10：验证签名

要做什么：检查签名是否有效。

```csharp
using (PdfFileSignature pdfSign = new PdfFileSignature(new Document(dataDir + "externalSignature1.pdf")))
{
    IList<string> sigNames = pdfSign.GetSignNames();
    for (int index = 0; index <= sigNames.Count - 1; index++)
    {
        if (!pdfSign.VerifySigned(sigNames[index]) || !pdfSign.VerifySignature(sigNames[index]))
        {
            throw new ApplicationException("Not verified");
        }
    }
}
```

解释：我们创建一个`PdfFileSignature`验证文档中的签名。如果签名无效，则会引发异常。

## 结论

恭喜！您刚刚学习了如何使用智能卡和 Aspose.PDF for .NET 签名字段签署 PDF 文档。此过程不仅可以保护您的文档，还可以确保真实性，使其成为当今数字环境中的一项必备技能。无论您签署的是合同、发票还是任何其他重要文件，了解如何实施数字签名都可以节省您的时间并让您高枕无忧。

## 常见问题解答

### 什么是 Aspose.PDF for .NET？
Aspose.PDF for .NET 是一个功能强大的库，允许开发人员在 .NET 应用程序中创建、操作和转换 PDF 文档。

### 我需要智能卡来签署 PDF 吗？
是的，需要智能卡才能使用数字证书安全地签署 PDF。

### 我可以免费使用 Aspose.PDF 吗？
 Aspose.PDF提供免费试用版，您可以下载[这里](https://releases.aspose.com/).

### 我如何验证已签名的 PDF？
您可以使用`PdfFileSignature` Aspose.PDF 中的类来验证 PDF 文档中的签名。

### 在哪里可以找到有关 Aspose.PDF 的更多文档？
您可以检查[Aspose.PDF 文档](https://reference.aspose.com/pdf/net/)了解更多详细信息和示例。