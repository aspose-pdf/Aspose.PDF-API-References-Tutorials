---
title: 确定 PDF 文件中的正确密码
linktitle: 确定 PDF 文件中的正确密码
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 确定 PDF 文件中的正确密码。
type: docs
weight: 30
url: /zh/net/programming-with-security-and-signatures/determine-correct-password/
---
在本教程中，我们将引导您完成使用 Aspose.PDF for .NET 确定 PDF 文件中正确密码的过程。此功能允许您检查 PDF 文件是否受密码保护，并从预定义列表中找到正确的密码。

## 第 1 步：先决条件

在开始之前，请确保您具备以下先决条件：

- C# 编程语言的基础知识
- 在您的计算机上安装 Visual Studio
- 已安装适用于 .NET 的 Aspose.PDF 库

## 第2步：环境设置

首先，请按照以下步骤设置您的开发环境：

1. 打开 Visual Studio 并创建一个新的 C# 项目。
2. 将所需的命名空间导入到您的代码文件中：

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

## 步骤 4：确定源 PDF 加密

上传源 PDF 文件后，您可以使用以下命令确定它是否已加密`IsEncrypted`的方法`PdfFileInfo`目的。

```csharp
Console.WriteLine("The file is password protected: " + info.IsEncrypted);
```

此语句显示 PDF 文件是否受密码保护。

## 第五步：找到正确的密码

接下来，我们将使用预定义的密码列表搜索正确的密码。我们检查列表中的每个密码，并尝试使用该密码加载 PDF 文档。

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

此循环测试列表中传递的每个单词。如果密码正确，则会显示文档的页数。否则，会提示密码不正确。


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

恭喜！您已使用 Aspose.PDF for .NET 成功确定了 PDF 文件的正确密码。本教程介绍了从验证文件加密到从预定义列表中查找正确密码的分步过程。现在您可以使用此功能来检查并查找 PDF 文件的正确密码。

### 确定 PDF 文件中正确密码的常见问题解答

#### 问：本教程的目的是什么？

答：本教程旨在指导您完成使用 Aspose.PDF for .NET 确定 PDF 文件的正确密码的过程。此功能允许您检查 PDF 文件是否受密码保护，并尝试从预定义列表中查找正确的密码。

#### 问：开始之前需要什么先决条件？

答：开始之前，请确保您对 C# 编程语言有基本的了解，在您的计算机上安装了 Visual Studio，并且安装了适用于 .NET 的 Aspose.PDF 库。

#### 问：如何搭建开发环境？

答：按照提供的步骤设置开发环境，包括在 Visual Studio 中创建新的 C# 项目，并导入所需的命名空间。

#### 问：如何判断PDF文件是否加密？

答：使用`PdfFileInfo`类来绑定源 PDF 文件。然后，使用`IsEncrypted`属性来确定 PDF 文件是否受密码保护。

#### 问：如何找到 PDF 文件的正确密码？

答：确定 PDF 文件已加密后，您可以尝试使用预定义的密码列表来查找正确的密码。提供的示例代码演示了如何循环遍历列表、尝试每个密码并确定密码是否正确。

#### 问：如果找到正确的密码会怎样？

A：如果找到正确的密码，示例代码将显示PDF文档的页数。

#### 问：如果密码不正确怎么办？

 A：如果密码不正确，示例代码将捕获`InvalidPasswordException`并显示密码不正确的信息。

#### 问：我可以使用不同的密码列表吗？

答：是的，您可以修改`passwords`示例代码中的数组以包含您要测试的密码。

#### 问：如何知道密码已成功确定？

A：如果示例代码成功加载带密码的PDF文档并显示页数，则说明已确定正确的密码。

#### 问：测试时如何保证密码安全？

答：使用预定义的密码列表时要小心，并避免使用敏感或机密密码进行测试。此外，在部署应用程序之前删除或修改测试代码。