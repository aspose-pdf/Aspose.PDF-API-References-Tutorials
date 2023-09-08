---
title: 将 Java 脚本添加到 PDF 文件
linktitle: 添加 Java 脚本 PDF 文件
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 将 JavaScript 添加到 PDF 文件。包含文档和页面级脚本编写代码教程的分步指南。
type: docs
weight: 10
url: /zh/net/programming-with-document/addjavascripttopage/
---
要将 JavaScript 添加到 PDF 文件，我们将使用 Aspose.PDF for .NET。该库提供了一种在 .NET 应用程序中处理 PDF 文件的简单而有效的方法。以下步骤将指导您完成使用 Aspose.PDF for .NET 将 JavaScript 添加到 PDF 文件的过程。

## 第 1 步：加载 PDF 文件

第一步是加载要添加 JavaScript 的 PDF 文件。您可以使用`Document`Aspose.PDF for .NET 提供的类。这`Document`类提供加载、保存和操作 PDF 文件的方法。

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//加载现有的 PDF 文件
Document doc = new Document(dataDir + "input.pdf");
```

## 第 2 步：在文档级别添加 JavaScript

要在文档级别添加 JavaScript，我们将使用`JavascriptAction`Aspose.PDF for .NET 提供的类。此类允许您指定要添加到 PDF 文件的 JavaScript 语句。

```csharp
//在文档级别添加 JavaScript
//使用所需的 JavaScript 语句实例化 JavascriptAction
JavascriptAction javaScript = new JavascriptAction("this.print({bUI:true,bSilent:false,bShrinkToFit:true});");

//将 JavascriptAction 对象分配给文档所需的操作
doc.OpenAction = javaScript;
```

在本教程中，我们将添加一条 JavaScript 语句，该语句将在打开文档时使用指定选项打印 PDF 文件。

## 第 3 步：在页面级别添加 JavaScript

要在页面级别添加 JavaScript，我们将使用`JavascriptAction`类和`Actions`由 Aspose.PDF for .NET 提供的属性。此属性允许您指定打开或关闭页面时将执行的 JavaScript 语句。

```csharp
//在页面级别添加 JavaScript
doc.Pages[2].Actions.OnOpen = new JavascriptAction("app.alert('page 1 opened')");
doc.Pages[2].Actions.OnClose = new JavascriptAction("app.alert('page 1 closed')");
```

在本教程中，我们将添加 JavaScript 语句，以便在打开或关闭页面时显示警报消息。

## 步骤 4：保存 PDF 文件

将 JavaScript 添加到 PDF 文件后，您需要保存修改后的文件。您可以使用`Save`提供的方法`Document`班级。

```csharp
dataDir = dataDir + "JavaScript-Added_out.pdf";
//保存 PDF 文档
doc.Save(dataDir);

Console.WriteLine("\nJavascript added successfully to a page.\nFile saved at " + dataDir);
```

此代码将修改后的PDF文件保存到指定目录。

### 使用 Aspose.PDF for .NET 添加 Java 脚本到页面的示例源代码

```csharp
            
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//加载现有的 PDF 文件
Document doc = new Document(dataDir + "input.pdf");

//在文档级别添加 JavaScript
//使用所需的 JavaScript 语句实例化 JavascriptAction
JavascriptAction javaScript = new JavascriptAction("this.print({bUI:true,bSilent:false,bShrinkToFit:true});");

//将 JavascriptAction 对象分配给文档所需的操作
doc.OpenAction = javaScript;

//在页面级别添加 JavaScript
doc.Pages[2].Actions.OnOpen = new JavascriptAction("app.alert('page 1 opened')");
doc.Pages[2].Actions.OnClose = new JavascriptAction("app.alert('page 1 closed')");

dataDir = dataDir + "JavaScript-Added_out.pdf";
//保存 PDF 文档
doc.Save(dataDir);

Console.WriteLine("\nJavascript added successfully to a page.\nFile saved at " + dataDir);     
```

## 结论

在本文中，我们解释了如何使用 Aspose.PDF for .NET 在文档级别和页面级别将 JavaScript 添加到 PDF 文件。我们提供了分步说明，并包含每个示例的完整源代码。有了这些知识，您就可以将 JavaScript 添加到 PDF 文件中，并根据您的需要自定义其行为。


### 将 Java 脚本添加到 PDF 文件的常见问题解答

#### 问：什么是 Aspose.PDF for .NET？

答：Aspose.PDF for .NET 是一个功能强大的库，使开发人员能够在 .NET 应用程序中处理 PDF 文件。它提供了用于创建、修改和操作 PDF 文档的广泛功能。

#### 问：我可以使用 Aspose.PDF for .NET 将 JavaScript 添加到 PDF 文档吗？

答：是的，Aspose.PDF for .NET 允许您将 JavaScript 添加到 PDF 文件的文档级别和页面级别，从而使您能够创建动态和交互式 PDF 文档。

#### 问：如何使用 Aspose.PDF for .NET 加载现有 PDF 文件？

答：您可以使用以下命令加载现有的 PDF 文件`Document`类及其方法，如分步指南中所示。

#### 问：我可以向 PDF 文档添加哪些类型的 JavaScript 操作？

答：使用 Aspose.PDF for .NET，您可以添加各种 JavaScript 操作，例如打印、警报消息、表单字段操作等。

#### 问：Aspose.PDF for .NET 适合商业项目吗？

答：是的，Aspose.PDF for .NET 是一个可靠且强大的库，通常用于商业项目中的 PDF 操作和生成任务。

