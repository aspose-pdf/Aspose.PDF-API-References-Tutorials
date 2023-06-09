---
title: 是否受密码保护
linktitle: 是否受密码保护
second_title: Aspose.PDF for .NET API 参考
description: 使用 Aspose.PDF for .NET 轻松检查 PDF 文档是否受密码保护。
type: docs
weight: 90
url: /zh/net/programming-with-security-and-signatures/is-password-protected/
---

在处理 PDF 文档之前了解它是否受密码保护通常很重要。使用 Aspose.PDF for .NET，您可以使用以下源代码轻松检查 PDF 文档是否受到保护：

## 第 1 步：导入所需的库

在开始之前，您需要为您的 C# 项目导入必要的库。以下是必要的导入指令：

```csharp
using Aspose.Pdf;
```

## 第 2 步：设置文档文件夹的路径

在此步骤中，您需要指定包含要检查的 PDF 文件的文件夹的路径。代替`"YOUR DOCUMENTS DIRECTORY"`在以下代码中使用文档文件夹的实际路径：

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## 第 3 步：加载源 PDF 文档

现在我们将加载源 PDF 文档并使用以下代码检查它是否受密码保护：

```csharp
PdfFileInfo fileInfo = new PdfFileInfo(dataDir + @"IsPasswordProtected.pdf");
```

## 第 4 步：检查 PDF 是否受保护

在此步骤中，我们将确定 PDF 文档是否使用密码保护`IsEncrypted`的方法`PdfFileInfo`目的。下面是相应的代码：

```csharp
bool encrypted = fileInfo.IsEncrypted;
```

## 第五步：查看加密状态

最后，我们可以使用`Console.WriteLine`方法。下面是相应的代码：

```csharp
Console.WriteLine(encrypted.ToString());
```

显示的消息将指示 PDF 文档是否受密码保护。

### Is Password Protected using Aspose.PDF for .NET 的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
//加载源 PDF 文档
PdfFileInfo fileInfo = new PdfFileInfo(dataDir+ @"IsPasswordProtected.pdf");
//确定源 PDF 文件已使用密码加密
bool encrypted = fileInfo.IsEncrypted;
//MessageBox 显示与 PDf 加密相关的当前状态
Console.WriteLine(encrypted.ToString());
```

## 结论

恭喜！现在您有了一个分步指南，可以使用 Aspose.PDF for .NET 检查 PDF 文档是否受密码保护。您可以将此代码集成到您自己的项目中，以根据 PDF 的保护状态执行特定的操作。

请务必查看官方 Aspose.PDF 文档，了解有关高级 PDF 文档安全和密码管理功能的更多信息。