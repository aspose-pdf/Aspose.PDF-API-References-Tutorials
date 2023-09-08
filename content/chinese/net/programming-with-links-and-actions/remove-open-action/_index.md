---
title: 删除打开的操作
linktitle: 删除打开的操作
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 从 PDF 中删除打开操作。
type: docs
weight: 80
url: /zh/net/programming-with-links-and-actions/remove-open-action/
---
通过此分步指南，了解如何使用 Aspose.PDF for .NET 从 PDF 文件中删除打开操作。

## 第一步：搭建环境

确保您已使用 C# 项目和适当的 Aspose.PDF 参考设置开发环境。

## 第 2 步：加载 PDF 文件

使用以下代码设置文档的目录路径并上传 PDF 文件：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
//打开文档
Document document = new Document(dataDir + "RemoveOpenAction.pdf");
```

## 第三步：删除打开的动作

通过设置从文档中删除打开操作`OpenAction`属性为空：

```csharp
document. OpenAction = null;
```

## 步骤 4：保存更新后的文档

使用保存更新的文档`Save`方法：

```csharp
dataDir = dataDir + "RemoveOpenAction_out.pdf";
document. Save(dataDir);
```

## 第5步：显示结果

显示一条消息，指示打开操作已成功删除并指定保存文件的位置：

```csharp
Console.WriteLine("\nOpen action deleted successfully.\nFile saved to location: " + dataDir);
```

### 使用 Aspose.PDF for .NET 删除打开操作的示例源代码 
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

恭喜！现在您知道如何使用 Aspose.PDF for .NET 从 PDF 中删除打开操作。使用这些知识来自定义项目中 PDF 文件的属性和行为。

现在您已经完成了本指南，您可以将这些概念应用到您自己的项目中，并进一步探索 Aspose.PDF for .NET 提供的功能。

### 常见问题解答 

#### 问：PDF 文件中的“打开操作”是什么？

答：PDF 文件中的“打开操作”是一条指令，指定打开 PDF 时会发生什么情况。它可以包括导航到文档中的特定页面或位置、启动外部应用程序或显示特定视图等操作。

#### 问：为什么我要从 PDF 文件中删除打开操作？

答：删除打开操作可以增强安全性、用户体验以及对打开 PDF 时呈现方式的控制。例如，您可能希望在打开文档时阻止自动导航或禁用某些操作。

#### 问：Aspose.PDF for .NET 如何帮助删除打开操作？

答：Aspose.PDF for .NET 提供 API 来操作 PDF 文件的各个方面。本教程演示如何使用 C# 代码删除打开操作。

#### 问：取消开放动作是否有潜在的风险或注意事项？

答：删除打开操作可能会改变 PDF 的默认行为，因此请确保它符合预期的用户体验。彻底测试修改后的 PDF，以确认删除不会影响其他功能。

#### 问：我可以自定义打开动作来执行其他操作吗？

答：是的，Aspose.PDF for .NET 允许您通过将打开操作设置为各种类型的操作来自定义打开操作，例如导航到特定页面或执行 JavaScript。

#### 问：我可以从受密码保护的 PDF 中删除打开的操作吗？
答：是的，只要您提供适当的凭据来访问和修改文档，您就可以从受密码保护的 PDF 中删除打开操作。

#### 问：打开动作移除是否可逆？

答：不可以，一旦打开操作被删除并保存 PDF，则无法从修改后的 PDF 恢复原始打开操作。

#### 问：如何验证打开操作是否已成功删除？

A：使用提供的代码去除打开操作后，打开修改后的PDF并确认打开时没有发生任何特定操作。

#### 问：我可以同时从多个 PDF 文件中删除打开的操作吗？

答：是的，您可以使用相同的方法在批处理场景中从多个 PDF 文件中删除打开的操作。