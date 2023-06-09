---
title: 设置权限
linktitle: 设置权限
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 轻松设置 PDF 文件的访问权限。
type: docs
weight: 100
url: /zh/net/programming-with-security-and-signatures/set-privileges/
---

通常需要为 PDF 文件设置特定的访问权限。使用 Aspose.PDF for .NET，您可以使用以下源代码轻松设置访问权限：

## 第 1 步：导入所需的库

在开始之前，您需要为您的 C# 项目导入必要的库。以下是必要的导入指令：

```csharp
using Aspose.Pdf;
```

## 第 2 步：设置文档文件夹的路径

在此步骤中，您需要指定包含要编辑的 PDF 文件的文件夹的路径。代替`"YOUR DOCUMENTS DIRECTORY"`在以下代码中使用文档文件夹的实际路径：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第 3 步：加载源 PDF 文件

现在我们将使用以下代码加载源 PDF 文件：

```csharp
using (Document document = new Document(dataDir + "input.pdf"))
```

## 第 4 步：设置访问权限

在这一步中，我们将实例化`DocumentPrivilege`对象来设置所需的访问权限。您可以使用对所有权限应用限制`DocumentPrivilege.ForbidAll`.例如，如果你想只允许屏幕阅读，你可以设置`AllowScreenReaders`到`true`.下面是相应的代码：

```csharp
DocumentPrivilege documentPrivilege = DocumentPrivilege.ForbidAll;
documentPrivilege.AllowScreenReaders = true;
```

## 第 5 步：加密并保存文档

最后，我们可以使用用户和所有者密码加密 PDF 文档`Encrypt`并指定所需的加密算法。然后我们保存更新的文档。下面是相应的代码：

```csharp
document.Encrypt("user", "owner", documentPrivilege, CryptoAlgorithm.AESx128, false);
document.Save(dataDir + "SetPrivileges_out.pdf");
```

### 使用 Aspose.PDF for .NET 设置权限的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
//加载源 PDF 文件
using (Document document = new Document(dataDir + "input.pdf"))
{
	//实例化文档权限对象
	//对所有权限应用限制
	DocumentPrivilege documentPrivilege = DocumentPrivilege.ForbidAll;
	//只允许屏幕阅读
	documentPrivilege.AllowScreenReaders = true;
	//使用用户和所有者密码加密文件。
	//需要设置密码，这样一旦用户查看有用户密码的文件，
	//仅启用屏幕阅读选项
	document.Encrypt("user", "owner", documentPrivilege, CryptoAlgorithm.AESx128, false);
	//保存更新的文档
	document.Save(dataDir + "SetPrivileges_out.pdf");
}
```

## 结论

恭喜！现在，您有了使用 Aspose.PDF for .NET 设置 PDF 文档访问权限的分步指南。您可以使用此代码应用特定限制并根据需要保护您的 PDF 文件。

请务必查看官方 Aspose.PDF 文档，了解有关高级 PDF 文档安全和访问权限管理功能的更多信息。