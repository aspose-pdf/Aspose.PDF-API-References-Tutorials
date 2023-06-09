---
title: 确定正确的密码
linktitle: 确定正确的密码
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 确定 PDF 文件的正确密码。
type: docs
weight: 30
url: /zh/net/programming-with-security-and-signatures/determine-correct-password/
---

在本教程中，我们将引导您完成使用 Aspose.PDF for .NET 确定 PDF 文件正确密码的过程。此功能允许您检查 PDF 文件是否受密码保护，并从预定义列表中找到正确的密码。

## 第 1 步：先决条件

在开始之前，请确保您具备以下先决条件：

- C#编程语言的基础知识
- 在您的计算机上安装 Visual Studio
- 已安装用于 .NET 的 Aspose.PDF 库

## 第二步：环境搭建

首先，请按照以下步骤设置您的开发环境：

1. 打开 Visual Studio 并创建一个新的 C# 项目。
2. 将所需的命名空间导入您的代码文件：

```csharp
using Aspose.Pdf;
```

## 第 3 步：加载源 PDF 文件

第一步是上传您要验证的源 PDF 文件。在此示例中，我们假设您在指定目录中有一个名为“IsPasswordProtected.pdf”的 PDF 文件。

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
PdfFileInfo info = new PdfFileInfo();
info.BindPdf(dataDir + "IsPasswordProtected.pdf");
```

请务必将占位符替换为 PDF 文件的实际位置。

## 第 4 步：确定源 PDF 加密

上传源 PDF 文件后，您可以使用`IsEncrypted`的方法`PdfFileInfo`目的。

```csharp
Console.WriteLine("The file is password protected: " + info.IsEncrypted);
```

此语句显示 PDF 文件是否受密码保护。

## 第 5 步：找到正确的密码

接下来，我们将使用预定义的密码列表搜索正确的密码。我们检查列表中的每个密码并尝试使用该密码加载 PDF 文档。

```csharp
String[] passwords = new String[5] { "test", "test1", "test2", "test3", "sample" };
for (int passwordcount = 0; passwordcount < passwords.Length; passwordcount++)
{
try
{
Document doc = new Document(dataDir + "IsPasswordProtected.pdf", passwords[passwordcount]);
if (doc.Pages.Count > 0)
Console.WriteLine("The document contains " + doc.Pages.Count + " pages.");
}
catch (InvalidPasswordException)
{
Console.WriteLine("The password " + passwords[passwordcount] + " is not correct.");
}
}
```

此循环测试列表中 pass 的每个单词。如果密码正确，则显示文档的页数。否则提示密码不正确。


### 使用 Aspose.PDF for .NET 确定正确密码的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";            
//加载源 PDF 文件
PdfFileInfo info = new PdfFileInfo();
info.BindPdf(dataDir + "IsPasswordProtected.pdf");
//确定源 PDF 是否已加密
Console.WriteLine("File is password protected " + info.IsEncrypted);
String[] passwords = new String[5] { "test", "test1", "test2", "test3", "sample" };
for (int passwordcount = 0; passwordcount < passwords.Length; passwordcount++)
{
	try
	{
		Document doc = new Document(dataDir + "IsPasswordProtected.pdf", passwords[passwordcount]);
		if (doc.Pages.Count > 0)
			Console.WriteLine("Number of Page in document are = " + doc.Pages.Count);
	}
	catch (InvalidPasswordException)
	{
		Console.WriteLine("Password = " + passwords[passwordcount] + "  is not correct");
	}
}
```

## 结论

恭喜！您已经使用 Aspose.PDF for .NET 成功确定了 PDF 文件的正确密码。本教程涵盖了从验证文件加密到从预定义列表中找到正确密码的分步过程。现在您可以使用此功能来检查并找到您的 PDF 文件的正确密码。