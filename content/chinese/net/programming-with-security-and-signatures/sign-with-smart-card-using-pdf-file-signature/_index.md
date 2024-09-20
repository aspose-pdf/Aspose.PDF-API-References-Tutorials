---
title: 使用 PDF 文件签名通过智能卡进行签名
linktitle: 使用 PDF 文件签名通过智能卡进行签名
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 的智能卡对 PDF 文件进行签名。按照此分步指南进行安全数字签名。
type: docs
weight: 110
url: /zh/net/programming-with-security-and-signatures/sign-with-smart-card-using-pdf-file-signature/
---
## 介绍

在数字时代，保护文档比以往任何时候都更加重要。无论是合同、协议还是任何敏感信息，确保文档真实且未被篡改都至关重要。数字签名来了！今天，我们将深入研究如何使用 Aspose.PDF for .NET 使用智能卡签署 PDF 文件。这个功能强大的库允许开发人员高效地操作和创建 PDF 文档，包括添加安全的数字签名。所以，拿起你的智能卡，让我们开始吧！

## 先决条件

在我们深入了解签署 PDF 文件的细节之前，让我们确保您已准备好所有需要的东西。以下是一份可帮助您做好准备的清单：

1.  Aspose.PDF for .NET：确保已安装 Aspose.PDF 库。您可以从[地点](https://releases.aspose.com/pdf/net/).
2. Visual Studio：您可以在其中编写和运行 .NET 代码的开发环境。
3. 智能卡：您需要一张安装了有效数字证书的智能卡。
4. 对 C# 的基本了解：熟悉 C# 编程将会很有益，因为我们将用这种语言编写代码片段。
5. PDF 文档：示例 PDF 文件（如`blank.pdf`来测试我们的签名流程。

有了这些先决条件，您就可以开始深入研究代码了！

## 导入包

首先，让我们导入必要的包。您需要在项目中添加对 Aspose.PDF 库的引用。操作方法如下：

1. 打开 Visual Studio。
2. 创建新项目或打开现有项目。
3. 在解决方案资源管理器中右键单击您的项目，然后选择`Manage NuGet Packages`.
4. 搜索`Aspose.PDF`并安装最新版本。

```csharp
using System;
using System.Collections.Generic;
using System.Linq;
using System.Text;
```

现在我们已经导入了必要的包，让我们逐步分解代码。

## 步骤 1：设置文档

我们流程的第一步是设置我们要签名的 PDF 文档。具体操作如下：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "blank.pdf");
```
在此代码片段中，我们定义了文档目录的路径，并创建了`Document`使用名为`blank.pdf` 确保更换`"YOUR DOCUMENTS DIRECTORY"`与您的 PDF 所在的实际路径。

## 步骤 2：初始化 PdfFileSignature

接下来，我们将初始化`PdfFileSignature`类，负责处理签名过程。

```csharp
using (Facades.PdfFileSignature pdfSign = new Facades.PdfFileSignature())
{
    pdfSign.BindPdf(doc);
```
在这里，我们创建一个实例`PdfFileSignature`并将其绑定到我们的 PDF 文档。这将为文档的签名做好准备。

## 步骤 3：访问智能卡证书

现在到了关键部分——访问存储在智能卡上的数字证书。我们可以这样做：

### 打开证书存储

```csharp
System.Security.Cryptography.X509Certificates.X509Store store = new System.Security.Cryptography.X509Certificates.X509Store(System.Security.Cryptography.X509Certificates.StoreLocation.CurrentUser);
store.Open(System.Security.Cryptography.X509Certificates.OpenFlags.ReadOnly);
```
我们打开位于当前用户配置文件中的证书存储区。这使我们能够访问安装在您机器上的证书，包括智能卡上的证书。

### 选择证书

```csharp
System.Security.Cryptography.X509Certificates.X509Certificate2Collection sel =
    System.Security.Cryptography.X509Certificates.X509Certificate2UI.SelectFromCollection(
        store.Certificates, null, null, System.Security.Cryptography.X509Certificates.X509SelectionFlag.SingleSelection);
```
此代码提示用户从集合中选择一个证书。用户界面将显示所有可用的证书，允许您选择与您的智能卡关联的证书。

## 步骤 4：创建外部签名

选择证书后，下一步是使用所选证书创建外部签名。

```csharp
Aspose.Pdf.Forms.ExternalSignature externalSignature = new Aspose.Pdf.Forms.ExternalSignature(sel[0]);
```
在这里，我们创建一个实例`ExternalSignature`使用选定的证书。此对象将用于签署 PDF 文档。

## 步骤 5：设置签名外观

现在，让我们设置签名的外观。在这里，您可以自定义您的签名在文档上的外观。

```csharp
pdfSign.SignatureAppearance = dataDir + "demo.png";
```
在此代码片段中，我们通过提供图像文件（如徽标或签名图形）的路径来指定签名的外观。确保替换`"demo.png"`与您想要使用的实际图像。

## 步骤 6：签署 PDF

一切设置完毕后，就可以签署 PDF 文档了！

```csharp
pdfSign.Sign(1, "Reason", "Contact", "Location", true, new System.Drawing.Rectangle(100, 100, 200, 200), externalSignature);
pdfSign.Save(dataDir + "externalSignature2.pdf");
```
在此步骤中，我们称`Sign`方法`pdfSign`对象。每个参数的含义如下：
- `1`：签名出现的页码。
- `"Reason"`：签署该文件的原因。
- `"Contact"`：签名者的联系信息。
- `"Location"`：签名者的所在地。
- `true`：表示是否创建可见签名。
- `new System.Drawing.Rectangle(100, 100, 200, 200)`：签名在PDF上的位置和大小。
- `externalSignature`：我们之前创建的签名对象。

最后，我们将签名的文档保存为`externalSignature2.pdf`.

## 步骤 7：验证签名

签署文件后，必须验证签名是否有效。具体操作如下：

### 初始化验证流程

```csharp
using (Facades.PdfFileSignature pdfSign = new Facades.PdfFileSignature(new Document(dataDir + "externalSignature2.pdf")))
{
    IList<string> sigNames = pdfSign.GetSignNames();
```
我们创建一个新的实例`PdfFileSignature`已签名文档。然后，我们检索文档中所有签名的名称。

### 检查签名有效性

```csharp
for (int index = 0; index <= sigNames.Count - 1; index++)
{
    if (!pdfSign.VerifySigned(sigNames[index]) || !pdfSign.VerifySignature(sigNames[index]))
    {
        throw new ApplicationException("Not verified");
    }
}
```
我们循环遍历每个签名名称并验证其有效性。如果任何签名验证失败，则抛出异常，表明该签名无效。

## 结论

就这样！您已成功使用 Aspose.PDF for .NET 的智能卡签署 PDF 文档。此过程不仅可以保护您的文档，还可以增加一层真实性，这在当今的数字世界中至关重要。无论您处理的是合同、法律文件还是任何敏感信息，了解如何实施数字签名都是一项宝贵的技能。 

## 常见问题解答

### 什么是 Aspose.PDF for .NET？
Aspose.PDF for .NET 是一个功能强大的库，允许开发人员在 .NET 应用程序内创建、操作和转换 PDF 文档。

### 我需要智能卡来签署 PDF 吗？
虽然智能卡不是强制性的，但强烈建议使用智能卡进行安全数字签名，因为它提供了额外的安全性。

### 我可以使用任何 PDF 文件进行签名吗？
是的，您可以使用任何 PDF 文件，但请确保它没有密码保护。如果有，您需要先解锁它。

### 如果我没有数字证书该怎么办？
您可以从受信任的证书颁发机构 (CA) 获取数字证书，或者使用自签名证书进行测试目的。

### 有 Aspose.PDF 的试用版吗？
是的，你可以从[Aspose 网站](https://releases.aspose.com/).