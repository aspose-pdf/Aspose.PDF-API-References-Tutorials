---
title: 在 PDF 文件中使用时间戳进行数字签名
linktitle: 在 PDF 文件中使用时间戳进行数字签名
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 在 PDF 文件中执行带有时间戳的数字签名。
type: docs
weight: 50
url: /zh/net/programming-with-security-and-signatures/digitally-sign-with-time-stamp/
---
在本教程中，我们将引导您完成使用 Aspose.PDF for .NET 在 PDF 文件中使用时间戳进行数字签名的过程。带有时间戳的数字签名通过添加带有时间戳的电子指纹来保证文档的真实性和完整性。

## 步骤 1：先决条件

开始之前，请确保您满足以下先决条件：

- 具备 C# 编程语言的基础知识
- 在你的机器上安装 Visual Studio
- 已安装适用于 .NET 的 Aspose.PDF 库

## 第 2 步：环境设置

首先，请按照以下步骤设置你的开发环境：

1. 打开 Visual Studio 并创建一个新的 C# 项目。
2. 将所需的命名空间导入到代码文件中：

```csharp
using Aspose.Pdf;
using Aspose.Pdf.Forms;
```

## 步骤 3：带时间戳的数字签名

第一步是对 PDF 文件执行带时间戳的数字签名。提供的代码展示了如何使用 Aspose.PDF for .NET 实现此签名。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string pfxFile = "";
using (Document document = new Document(dataDir + @"DigitallySign.pdf"))
{
     using (PdfFileSignature signature = new PdfFileSignature(document))
     {
         PKCS7 pkcs = new PKCS7(pfxFile, "pfx_password");
         TimestampSettings timestampSettings = new TimestampSettings("https:\\your_timestamp_settings", "user:password");
         pkcs. TimestampSettings = timestampSettings;
         System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
         signature.Sign(1, "Reason for signing", "Contact", "Location", true, rect, pkcs);
         signature.Save(dataDir + "DigitallySignWithTimeStamp_out.pdf");
     }
}
```

此代码加载 PDF 文件，使用 PFX 文件（私钥）和指定的时间戳参数创建带时间戳的数字签名。然后，将签名添加到 PDF 文件中，并以后缀“_出去”。

### 使用 Aspose.PDF for .NET 进行带时间戳的数字签名的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
string pfxFile = "";
using (Document document = new Document(dataDir + @"DigitallySign.pdf"))
{
	using (PdfFileSignature signature = new PdfFileSignature(document))
	{
		PKCS7 pkcs = new PKCS7(pfxFile, "pfx_password");
		TimestampSettings timestampSettings = new TimestampSettings("https:\\your_timestamp_settings", "user:password"); //可以省略用户/密码
		pkcs.TimestampSettings = timestampSettings;
		System.Drawing.Rectangle rect = new System.Drawing.Rectangle(100, 100, 200, 100);
		//创建三种签名类型中的任意一种
		signature.Sign(1, "Signature Reason", "Contact", "Location", true, rect, pkcs);
		//保存输出 PDF 文件
		signature.Save(dataDir + "DigitallySignWithTimeStamp_out.pdf");
	}
}
```

## 结论

恭喜！您已成功使用 Aspose.PDF for .NET 在 PDF 文件上执行了带时间戳的数字签名。本教程介绍了从创建签名到保存更新的 PDF 文件的分步过程。您现在可以使用此功能将带时间戳的数字签名添加到您的 PDF 文件中。

### PDF 文件中带时间戳的数字签名常见问题解答

#### 问：使用时间戳进行数字签名的目的是什么？

答：带时间戳的数字签名会为 PDF 文件添加带有时间戳的电子指纹，确保文档在特定时间点的真实性和完整性。

#### 问：开始本教程需要哪些先决条件？

答：开始之前，请确保您对 C# 编程语言有基本的了解，安装了 Visual Studio，并安装了适用于 .NET 的 Aspose.PDF 库。

#### 问：如何设置我的开发环境？

答：按照提供的步骤设置您的开发环境，包括在 Visual Studio 中创建一个新的 C# 项目并导入必要的命名空间。

#### 问：如何在 PDF 中添加带有时间戳的数字签名？

答：提供的示例代码演示了如何加载 PDF 文件、使用 PFX 文件（私钥）和指定的时间戳设置创建带有时间戳的数字签名、将签名添加到 PDF 文件以及保存更新的文件。

#### 问：什么是 PFX 文件，为什么在示例中使用它？

答：PFX（个人交换格式）文件包含私钥和证书。它在这里用于为数字签名提供加密功能。请确保用您的 PFX 文件和密码替换占位符。

#### 问：什么是 TimestampSettings？

答：TimestampSettings 定义用于将电子时间戳添加到签名的时间戳服务器的设置。它包括时间戳服务器 URL 和可选的用户凭据。

#### 问：我可以使用示例中的时间戳服务器以外的其他时间戳服务器吗？
答：是的，您可以使用任何兼容的时间戳服务器。替换 URL，并在需要时提供适当的用户凭据`TimestampSettings`目的。

#### 问：指定签名矩形的目的是什么？

答：签名矩形定义了数字签名在 PDF 页面上的位置和尺寸。调整这些值以根据需要定位签名。

#### 问：如果签名期间时间戳服务器不可用，会发生什么情况？

答：如果在签名期间时间戳服务器不可用，则签名过程可能会失败或耗时更长。请确保您的时间戳服务器可靠且可访问。

#### 问：如何验证签名的 PDF 中是否存在时间戳？

答：您可以使用提供的示例代码检查已签名的 PDF。`TimestampSettings`您在签名时使用的信息应在签名详细信息中可用。

#### 问：带有时间戳的数字签名具有法律约束力吗？

答：带时间戳的数字签名在许多司法管辖区都具有法律效力，通常被认为比简单的数字签名更可靠。请咨询您所在司法管辖区的法律专家以了解具体规定。

#### 问：我可以向 PDF 添加多个带有时间戳的数字签名吗？

答：是的，您可以通过多次调用签名创建过程向 PDF 文件添加多个带时间戳的数字签名。每个签名都有自己的时间戳。