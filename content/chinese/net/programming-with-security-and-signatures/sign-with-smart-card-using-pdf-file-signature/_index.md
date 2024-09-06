---
title: 使用 PDF 文件签名通过智能卡进行签名
linktitle: 使用 PDF 文件签名通过智能卡进行签名
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 通过智能卡安全地签署您的 PDF 文件。
type: docs
weight: 110
url: /zh/net/programming-with-security-and-signatures/sign-with-smart-card-using-pdf-file-signature/
---
使用智能卡进行数字签名是签署 PDF 文件的安全方式。使用 Aspose.PDF for .NET，您可以按照以下源代码轻松使用智能卡签署 PDF 文件：

## 步骤 1：导入所需的库

开始之前，您需要导入 C# 项目所需的库。以下是必要的导入指令：

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Forms;
using System.Security.Cryptography.X509Certificates;
```

## 第 2 步：设置文档文件夹的路径

在此步骤中，您需要指定包含要签名的 PDF 文件的文件夹的路径。替换`"YOUR DOCUMENTS DIRECTORY"`在下面的代码中使用您的文档文件夹的实际路径：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 步骤 3：加载 PDF 文档

现在我们将使用以下代码加载需要签名的 PDF 文档：

```csharp
Document doc = new Document(dataDir + "blank.pdf");
```

## 步骤 4：使用智能卡进行签名

在此步骤中，我们将使用智能卡进行签名`PdfFileSignature`来自的类`Facades`库。我们从 Windows 证书存储中选择智能卡证书并指定必要的签名信息。以下是相应的代码：

```csharp
using (PdfFileSignature pdfSign = new PdfFileSignature())
{
     pdfSign.BindPdf(doc);

     //在商店中选择证书
     X509Store store = new X509Store(StoreLocation.CurrentUser);
     store.Open(OpenFlags.ReadOnly);
     X509Certificate2Collection sel = X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, X509SelectionFlag.SingleSelection);
     ExternalSignature externalSignature = new ExternalSignature(sel[0]);

     pdfSign.SignatureAppearance = dataDir + "demo.png";
     pdfSign.Sign(1, "Reason", "Contact", "Location", true, new System.Drawing.Rectangle(100, 100, 200, 200), externalSignature);
     pdfSign.Save(dataDir + "externalSignature2.pdf");
}
```

## 步骤 5：验证签名

最后，我们使用`PdfFileSignature`类，我们获取签名名称，然后逐个进行校验，如果签名校验不通过，则会抛出异常，下面是对应的代码：

```csharp
using (PdfFileSignature pdfSign = new PdfFileSignature(new Document(dataDir + "externalSignature2.pdf")))
{
     IList<string> sigNames = pdfSign. GetSignNames();
     for (int index = 0; index <= sigNames.Count - 1; index++)
     {
         if (!pdfSign.VerifySigned(sigNames[index]) || !pdfSign.VerifySignature(sigNames[index]))
         {
             throw new ApplicationException("Unverified");
         }
     }
}
```

### 使用 Aspose.PDF for .NET 的 PDF 文件签名通过智能卡签名的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "blank.pdf");
using (Facades.PdfFileSignature pdfSign = new Facades.PdfFileSignature())
{
	pdfSign.BindPdf(doc);
	//使用 Windows 证书存储区中的证书选择进行签名
	System.Security.Cryptography.X509Certificates.X509Store store = new System.Security.Cryptography.X509Certificates.X509Store(System.Security.Cryptography.X509Certificates.StoreLocation.CurrentUser);
	store.Open(System.Security.Cryptography.X509Certificates.OpenFlags.ReadOnly);
	//在商店中手动选择证书
	System.Security.Cryptography.X509Certificates.X509Certificate2Collection sel = System.Security.Cryptography.X509Certificates.X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, System.Security.Cryptography.X509Certificates.X509SelectionFlag.SingleSelection);
	Aspose.Pdf.Forms.ExternalSignature externalSignature = new Aspose.Pdf.Forms.ExternalSignature(sel[0]);
	pdfSign.SignatureAppearance = dataDir + "demo.png";
	pdfSign.Sign(1, "Reason", "Contact", "Location", true, new System.Drawing.Rectangle(100, 100, 200, 200), externalSignature);
	pdfSign.Save(dataDir + "externalSignature2.pdf");
}
using (Facades.PdfFileSignature pdfSign = new Facades.PdfFileSignature(new Document(dataDir + "externalSignature2.pdf")))
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

## 结论

恭喜！现在，您已经获得了使用 Aspose.PDF for .NET 通过智能卡签署 PDF 文件的分步指南。您可以使用此代码向您的 PDF 文档添加安全的数字签名。

请务必查看官方 Aspose.PDF 文档，以获取有关高级数字签名和证书管理功能的更多信息。

### 常见问题解答

#### 问：为什么我应该考虑用智能卡签署 PDF 文件？

答：使用智能卡对 PDF 文件进行签名可确保文档的真实性和完整性，从而增强安全性。基于智能卡的签名可提供更高级别的信任和合规性。

#### 问：基于智能卡的数字签名如何工作？

答：基于智能卡的数字签名涉及使用存储在智能卡上的加密密钥来创建唯一的数字签名。此签名附加到 PDF 文件中，使收件人可以验证文档的来源和完整性。

#### 问：Aspose.PDF for .NET 在基于智能卡的签名中起什么作用？

答：Aspose.PDF for .NET 提供了一套全面的工具和库，以促进基于智能卡的 PDF 文件数字签名。它简化了流程并确保了安全的文档签名。

#### 问：我可以选择特定的智能卡证书进行签名吗？

答：是的，您可以从 Windows 证书存储中选择一个特定的智能卡证书进行签名。Aspose.PDF for .NET 允许您将证书选择无缝集成到您的应用程序中。

#### 问：提供的源代码如何处理基于智能卡的签名？

答：源代码演示了如何绑定PDF文档、选择智能卡证书、指定签名信息、创建数字签名，以及如何验证签名的有效性。

#### 问：我可以在单个 PDF 文件中使用智能卡应用多个签名吗？

答：当然可以，您可以将多个基于智能卡的签名应用于单个 PDF 文件。每个签名都是唯一的，有助于文档的整体安全性。

#### 问：如果在验证步骤中签名验证失败怎么办？

答：如果签名验证失败，则会抛出异常，表明该签名无效。这确保只接受有效且受信任的签名。

#### 问：基于智能卡的签名是否与所有类型的 PDF 文档兼容？

答：是的，基于智能卡的签名与所有类型的 PDF 文档兼容。您可以将数字签名应用于各种类型的 PDF 文件，包括表单、报告等。

#### 问：如何才能了解有关高级数字签名和证书管理的更多信息？

答：浏览 Aspose.PDF 官方文档，详细了解高级数字签名功能、证书管理以及确保文档安全的最佳实践。

#### 问：在哪里可以找到有关实施基于智能卡的签名的进一步帮助或支持？

答：如需更多指导和支持，请访问 Aspose.PDF 社区论坛或参阅文档以获取有关基于智能卡的签名的全面信息。