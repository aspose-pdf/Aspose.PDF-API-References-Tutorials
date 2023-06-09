---
title: 删除打开操作
linktitle: 删除打开操作
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 从 PDF 中删除打开操作。
type: docs
weight: 80
url: /zh/net/programming-with-links-and-actions/remove-open-action/
---

通过此分步指南了解如何使用 Aspose.PDF for .NET 从 PDF 文件中删除打开操作。

## 第 1 步：设置环境

确保您已经使用 C# 项目和适当的 Aspose.PDF 参考设置了您的开发环境。

## 第 2 步：加载 PDF 文件

使用以下代码设置文档的目录路径并上传 PDF 文件：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
//打开文档
Document document = new Document(dataDir + "RemoveOpenAction.pdf");
```

## 第 3 步：删除打开操作

通过设置`OpenAction`属性为空：

```csharp
document. OpenAction = null;
```

## 第 4 步：保存更新后的文档

使用`Save`方法：

```csharp
dataDir = dataDir + "RemoveOpenAction_out.pdf";
document. Save(dataDir);
```

## 第 5 步：显示结果

显示一条消息，表明已成功删除打开操作并指定保存文件的位置：

```csharp
Console.WriteLine("\nOpen action deleted successfully.\nFile saved to location: " + dataDir);
```

### 使用 Aspose.PDF for .NET 的 Remove Open Action 示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//打开文档
Document document = new Document(dataDir + "RemoveOpenAction.pdf");
//删除文档打开操作
document.OpenAction = null;
dataDir = dataDir + "RemoveOpenAction_out.pdf";
//保存更新的文档
document.Save(dataDir);
Console.WriteLine("\nOpen action removed successfully.\nFile saved at " + dataDir); 
```

## 结论

恭喜！现在您知道了如何使用 Aspose.PDF for .NET 从 PDF 中删除打开操作。使用这些知识在您的项目中自定义 PDF 文件的属性和行为。

现在您已经完成了本指南，您可以将这些概念应用到您自己的项目中并进一步探索 Aspose.PDF for .NET 提供的功能。