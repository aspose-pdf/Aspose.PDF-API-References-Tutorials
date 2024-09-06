---
title: 移除打开的动作
linktitle: 移除打开的动作
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 从 PDF 中删除打开操作。
type: docs
weight: 80
url: /zh/net/programming-with-links-and-actions/remove-open-action/
---
通过本分步指南了解如何使用 Aspose.PDF for .NET 从 PDF 文件中删除打开操作。

## 步骤 1：设置环境

确保您已经使用 C# 项目和适当的 Aspose.PDF 参考设置了开发环境。

## 步骤 2：加载 PDF 文件

设置文档的目录路径并使用以下代码上传 PDF 文件：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENTS DIRECTORY";
//打开文档
Document document = new Document(dataDir + "RemoveOpenAction.pdf");
```

## 步骤 3：删除打开的动作

通过设置`OpenAction`属性设置为空：

```csharp
document. OpenAction = null;
```

## 步骤 4：保存更新的文档

使用保存更新的文档`Save`方法：

```csharp
dataDir = dataDir + "RemoveOpenAction_out.pdf";
document. Save(dataDir);
```

## 步骤 5：显示结果

显示一条消息表明打开操作已成功删除，并指定保存文件的位置：

```csharp
Console.WriteLine("\nOpen action deleted successfully.\nFile saved to location: " + dataDir);
```

### 使用 Aspose.PDF for .NET 删除打开操作的示例源代码 
```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";
//打开文档
Document document = new Document(dataDir + "RemoveOpenAction.pdf");
//删除文档打开动作
document.OpenAction = null;
dataDir = dataDir + "RemoveOpenAction_out.pdf";
//保存更新的文档
document.Save(dataDir);
Console.WriteLine("\nOpen action removed successfully.\nFile saved at " + dataDir); 
```

## 结论

恭喜！现在您知道如何使用 Aspose.PDF for .NET 从 PDF 中删除打开操作。使用这些知识来自定义项目中 PDF 文件的属性和行为。

现在您已经完成本指南，您可以将这些概念应用到您自己的项目中，并进一步探索 Aspose.PDF for .NET 提供的功能。

### 常见问题解答 

#### 问：PDF 文件中的“打开动作”是什么？

答：PDF 文件中的“打开操作”是指定打开 PDF 时应发生什么的指令。它可以包括导航到文档中的特定页面或位置、启动外部应用程序或显示特定视图等操作。

#### 问：为什么我要从 PDF 文件中删除打开操作？

答：删除打开操作可以增强安全性、用户体验以及对打开 PDF 时呈现方式的控制。例如，您可能希望阻止自动导航或在打开文档时禁用某些操作。

#### 问：Aspose.PDF for .NET 如何帮助删除打开操作？

答：Aspose.PDF for .NET 提供了 API 来操作 PDF 文件的各个方面。本教程演示如何使用 C# 代码删除打开操作。

#### 问：取消开放式动作时是否存在任何潜在风险或注意事项？

答：删除打开操作可能会改变 PDF 的默认行为，因此请确保它符合预期的用户体验。彻底测试修改后的 PDF，以确认删除操作不会影响其他功能。

#### 问：我可以自定义打开动作来执行其他操作吗？

答：是的，Aspose.PDF for .NET 允许您通过将其设置为各种类型的操作来定制打开操作，例如导航到特定页面或执行 JavaScript。

#### 问：我可以从受密码保护的 PDF 中删除打开的操作吗？
答：是的，只要您提供适当的凭据来访问和修改文档，您就可以从受密码保护的 PDF 中删除打开的操作。

#### 问：打开动作的移除是可逆的吗？

答：不可以，一旦删除打开动作并保存 PDF，则无法从修改后的 PDF 中恢复原始的打开动作。

#### 问：如何验证打开操作是否已成功删除？

答：使用提供的代码删除打开动作后，打开修改后的 PDF 并确认打开时没有发生任何特定动作。

#### 问：我可以同时从多个 PDF 文件中删除打开的操作吗？

答：是的，您可以使用相同的方法在批处理场景中删除多个 PDF 文件的打开操作。