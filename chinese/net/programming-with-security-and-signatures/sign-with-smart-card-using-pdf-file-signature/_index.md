---
title: 使用 PDF 文件签名通过智能卡进行签名
linktitle: 使用 PDF 文件签名通过智能卡进行签名
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 通过智能卡安全地签署您的 PDF 文件。
type: docs
weight: 110
url: /zh/net/programming-with-security-and-signatures/sign-with-smart-card-using-pdf-file-signature/
---
使用智能卡进行数字签名是签署 PDF 文件的安全方式。借助 Aspose.PDF for .NET，您可以按照以下源代码轻松使用智能卡对 PDF 文件进行签名：

## 第1步：导入所需的库

在开始之前，您需要为 C# 项目导入必要的库。以下是必要的导入指令：

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Facades;
using Aspose.Pdf.Forms;
using System.Security.Cryptography.X509Certificates;
```

## 步骤 2：设置文档文件夹路径

在此步骤中，您需要指定包含要签名的 PDF 文件的文件夹的路径。代替`"YOUR DOCUMENTS DIRECTORY"`在以下代码中使用文档文件夹的实际路径：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第 3 步：加载 PDF 文档

现在我们将使用以下代码加载要签名的 PDF 文档：

```csharp
Document doc = new Document(dataDir + "blank.pdf");
```

## 步骤4：使用智能卡进行签名

在此步骤中，我们将使用智能卡执行签名`PdfFileSignature`类来自`Facades`图书馆。我们从 Windows 证书存储中选择智能卡证书并指定必要的签名信息。这是相应的代码：

```csharp
using (PdfFileSignature pdfSign = new PdfFileSignature())
{
     pdfSign.BindPdf(doc);

     //选择商店中的证书
     X509Store store = new X509Store(StoreLocation.CurrentUser);
     store.Open(OpenFlags.ReadOnly);
     X509Certificate2Collection sel = X509Certificate2UI.SelectFromCollection(store.Certificates, null, null, X509SelectionFlag.SingleSelection);
     ExternalSignature externalSignature = new ExternalSignature(sel[0]);

     pdfSign.SignatureAppearance = dataDir + "demo.png";
     pdfSign.Sign(1, "Reason", "Contact", "Location", true, new System.Drawing.Rectangle(100, 100, 200, 200), externalSignature);
     pdfSign.Save(dataDir + "externalSignature2.pdf");
}
```

## 第 5 步：验证签名

最后，我们使用以下命令验证已签名 PDF 文件的签名：`PdfFileSignature`班级。我们拿到签名名字，一一核对。如果签名验证失败，则会抛出异常。这是相应的代码：

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

### 使用 Aspose.PDF for .NET 使用 Pdf 文件签名通过智能卡进行签名的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
Document doc = new Document(dataDir + "blank.pdf");
using (Facades.PdfFileSignature pdfSign = new Facades.PdfFileSignature())
{
	pdfSign.BindPdf(doc);
	//使用 Windows 证书存储中的证书选择进行签名
	System.Security.Cryptography.X509Certificates.X509Store store = new System.Security.Cryptography.X509Certificates.X509Store(System.Security.Cryptography.X509Certificates.StoreLocation.CurrentUser);
	store.Open(System.Security.Cryptography.X509Certificates.OpenFlags.ReadOnly);
	//手动选择商店中的证书
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

恭喜！现在，您已获得使用 Aspose.PDF for .NET 通过智能卡对 PDF 文件进行签名的分步指南。您可以使用此代码向 PDF 文档添加安全数字签名。

请务必查看官方 Aspose.PDF 文档，以获取有关高级数字签名和证书管理功能的更多信息。

### 常见问题解答

#### 问：为什么我应该考虑使用智能卡签署 PDF 文件？

答：使用智能卡签署 PDF 文件可以确保文档的真实性和完整性，从而增强安全性。基于智能卡的签名提供了更高级别的信任和合规性。

#### 问：基于智能卡的数字签名如何工作？

答：基于智能卡的数字签名涉及使用存储在智能卡上的加密密钥来创建唯一的数字签名。此签名附加到 PDF 文件中，允许收件人验证文档的来源和完整性。

#### 问：Aspose.PDF for .NET 在基于智能卡的签名中的作用是什么？

答：Aspose.PDF for .NET 提供了一套全面的工具和库，以促进 PDF 文件基于智能卡的数字签名。它简化了流程并确保安全的文档签名。

#### 问：我可以选择特定的智能卡证书进行签名吗？

答：是的，您可以从 Windows 证书存储区中选择特定的智能卡证书进行签名。 Aspose.PDF for .NET 允许您将证书选择无缝集成到您的应用程序中。

#### 问：所提供的源代码如何处理基于智能卡的签名？

答：源代码演示了如何绑定PDF文档、选择智能卡证书、指定签名信息以及创建数字签名。它还展示了如何验证签名的有效性。

#### 问：我可以使用智能卡在单个 PDF 文件中应用多个签名吗？

答：当然，您可以将多个基于智能卡的签名应用于单个 PDF 文件。每个签名都是唯一的，有助于提高文档的整体安全性。

#### 问：如果签名在验证过程中验证失败怎么办？

答：如果签名验证失败，会抛出异常，表明签名无效。这确保了仅接受有效且可信的签名。

#### 问：基于智能卡的签名是否与所有类型的 PDF 文档兼容？

答：是的，基于智能卡的签名与所有类型的 PDF 文档兼容。您可以将数字签名应用于各种类型的 PDF 文件，包括表单、报告等。

#### 问：如何了解有关高级数字签名和证书管理的更多信息？

答：浏览 Aspose.PDF 官方文档，详细了解高级数字签名功能、证书管理和确保文档安全的最佳实践。

#### 问：在哪里可以找到实施基于智能卡的签名的进一步帮助或支持？

答：如需更多指导和支持，请访问 Aspose.PDF 社区论坛或参阅文档以获取有关基于智能卡的签名的全面信息。