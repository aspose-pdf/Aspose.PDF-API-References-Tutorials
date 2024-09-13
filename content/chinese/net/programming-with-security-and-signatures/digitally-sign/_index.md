---
title: 对 PDF 文件进行数字签名
linktitle: 对 PDF 文件进行数字签名
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 对 PDF 文件进行数字签名。分步指南可确保您的文档安全且真实。
type: docs
weight: 40
url: /zh/net/programming-with-security-and-signatures/digitally-sign/
---
## 介绍

在我们的数字世界中，保护文档的重要性怎么强调都不为过。无论您是发送合同的自由职业者、管理发票的小企业主还是大公司的一员，确保您的文档保持真实且防篡改都至关重要。实现这种安全性的一种有效方法是通过数字签名。在本文中，我们将探讨如何使用 Aspose.PDF for .NET 库对 PDF 文件进行数字签名。我们将逐步指导您完成所有操作。

## 先决条件

在深入讨论细节之前，让我们先确保您已具备开始对 PDF 文件进行数字签名所需的一切。以下是先决条件列表：

1. .NET Framework：确保您的机器上安装了 .NET Framework。Aspose.PDF for .NET 支持该框架的多个版本。
2.  Aspose.PDF 库：您需要下载并安装 Aspose.PDF 库。您可以从[发布链接](https://releases.aspose.com/pdf/net/).
3. 数字证书：要签署 PDF，您需要数字证书——`.pfx`文件通常。
4. 开发环境：使用 Visual Studio 或任何支持 C# 的 IDE。

一旦满足这些先决条件，您就可以开始签署 PDF 文档了！

## 导入包

现在您已完成所有设置，让我们导入必要的包来运行我们的项目。在 C# 类的顶部，包含相关的命名空间：

```csharp
using System.IO;
using System;
using Aspose.Pdf;
using Aspose.Pdf.Facades;
using System.Collections;
using Aspose.Pdf.Forms;
using System.Collections.Generic;
```

这些命名空间提供了使用 Aspose.PDF 操作 PDF 文件所需的基本类和方法。

## 步骤 1：设置文档路径

第一步是设置输入和输出 PDF 文件以及数字证书的路径。替换`YOUR DOCUMENTS DIRECTORY`使用您的系统上文件所在的实际路径。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string pbxFile = ""; //您的数字证书 (.pfx) 的路径
string inFile = dataDir + @"DigitallySign.pdf";
string outFile = dataDir + @"DigitallySign_out.pdf";
```
在此代码片段中，`inFile`您想要签名的原始 PDF 是`outFile`是已签名的 PDF 的保存位置。

## 第 2 步：加载 PDF 文档

接下来，我们需要加载要签名的 PDF 文档。`Document`这里使用 Aspose.PDF 中的类：

```csharp
using (Document document = new Document(inFile))
{
    //继续在此签署逻辑...
}
```

此代码打开您的 PDF 文件并准备进行进一步的操作。

## 步骤 3：初始化 PdfFileSignature 类

一旦文档加载完毕，我们就会创建一个`PdfFileSignature`类，它将允许我们使用已加载的 PDF 文档上的数字签名。

```csharp
using (PdfFileSignature signature = new PdfFileSignature(document))
{
    //准备签名流程
}
```

本课程将帮助您了解与 PDF 签名相关的所有事项！

## 步骤 4：创建数字证书实例

这里是设置用于签署 PDF 的证书的地方。您需要提供证书的路径`.pfx`文件以及与之关联的密码。

```csharp
PKCS7 pkcs = new PKCS7(pbxFile, "WebSales");
```

确保更换`"WebSales"`使用您的实际证书密码。

## 步骤 5：配置签名外观

接下来，我们定义签名在 PDF 中的显示方式。您可以使用矩形自定义签名的位置和外观。 

```csharp
System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
signature.SignatureAppearance = dataDir + @"aspose-logo.jpg";
```

在这里，我们将签名定位在坐标 (100, 100) 处，宽度为 200，高度为 100。

## 步骤 6：创建并保存签名

现在是时候实际创建签名并保存我们签名的 PDF 了。您可以描述签名的原因、您的联系方式和位置。这可以帮助以后的验证过程。

```csharp
DocMDPSignature docMdpSignature = new DocMDPSignature(pkcs, DocMDPAccessPermissions.FillingInForms);
signature.Certify(1, "Signature Reason", "Contact", "Location", true, rect, docMdpSignature);
signature.Save(outFile);
```

## 步骤 7：验证签名

保存签名的 PDF 后，最好检查签名是否已正确添加。我们可以检索签名名称并检查其是否有效。 

```csharp
using (Document document = new Document(outFile))
{
    using (PdfFileSignature signature = new PdfFileSignature(document))
    {
        IList<string> sigNames = signature.GetSignNames();
        if (sigNames.Count > 0) 
        {
            if (signature.VerifySigned(sigNames[0] as string)) 
            {
                if (signature.IsCertified) 
                {
                    if (signature.GetAccessPermissions() == DocMDPAccessPermissions.FillingInForms) 
                    {
                        //签名有效且经过认证
                    }
                }
            }
        }
    }
}
```

这部分确保您的工作得到验证；毕竟，您不想发送未签名的文件！

## 步骤 8：处理异常

将代码包装在 try-catch 块中以便妥善处理任何异常总是明智的。 

```csharp
catch (Exception ex)
{
    Console.WriteLine(ex.Message);
}
```

这样，如果发生意外情况，您就会确切地知道出了什么问题，而不会导致应用程序崩溃。

## 结论

数字签名为文档提供了必要的保障，可证明其真实性和完整性。使用 Aspose.PDF for .NET，签署 PDF 文件是一个简单的过程，可以显著增强您的文档管理工作流程。现在您已经学会了如何数字化您的签名，您可以向客户和合作伙伴保证您的专业性和安全的文档处理能力。

## 常见问题解答

### 什么是数字签名？
数字签名是手写签名的加密等效物。它可确保数据的真实性和完整性。

### 我可以在任何.NET 应用程序中使用 Aspose.PDF 签署 PDF 文件吗？
是的！Aspose.PDF for .NET 与各种.NET应用程序兼容，包括桌面、Web 和服务。

### 我可以使用哪些类型的数字证书？
您可以使用任何 PKCS#12 证书，通常保存在`.pfx`或者`.p12`文件。

### 有 Aspose.PDF 的试用版吗？
是的！您可以从[Aspose 发布页面](https://releases.aspose.com/).

### 如果我遇到问题，如何获得支持？
如需支持，您可以访问[Aspose PDF 论坛](https://forum.aspose.com/c/pdf/10).