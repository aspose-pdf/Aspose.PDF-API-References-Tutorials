---
title: 将 Java 脚本添加到页面
linktitle: 将 Java 脚本添加到页面
second_title: Aspose.PDF for .NET API 参考
description: 了解如何使用 Aspose.PDF for .NET 将 JavaScript 添加到 PDF 文件。带有文档和页面级脚本编写代码教程的分步指南。
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

//将 JavascriptAction 对象分配给所需的文档操作
doc.OpenAction = javaScript;
```

在本教程中，我们将添加一个 JavaScript 语句，该语句将在打开文档时使用指定的选项打印 PDF 文件。

## 第 3 步：在页面级别添加 JavaScript

要在页面级别添加 JavaScript，我们将使用`JavascriptAction`类和`Actions`Aspose.PDF for .NET 提供的属性。此属性允许您指定将在打开或关闭页面时执行的 JavaScript 语句。

```csharp
//在页面级别添加 JavaScript
doc.Pages[2].Actions.OnOpen = new JavascriptAction("app.alert('page 1 opened')");
doc.Pages[2].Actions.OnClose = new JavascriptAction("app.alert('page 1 closed')");
```

在本教程中，我们将添加 JavaScript 语句，这些语句将在页面打开或关闭时显示警告消息。

## 第 4 步：保存 PDF 文件

将 JavaScript 添加到 PDF 文件后，您需要保存修改后的文件。您可以使用`Save`提供的方法`Document`班级。

```csharp
dataDir = dataDir + "JavaScript-Added_out.pdf";
//保存 PDF 文档
doc.Save(dataDir);

Console.WriteLine("\nJavascript added successfully to a page.\nFile saved at " + dataDir);
```

此代码会将修改后的 PDF 文件保存到指定目录。

### 使用 Aspose.PDF for .NET 将 Java 脚本添加到页面的示例源代码

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//加载现有的 PDF 文件

```csharp
            
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//加载现有的 PDF 文件
Document doc = new Document(dataDir + "input.pdf");

//在文档级别添加 JavaScript
//使用所需的 JavaScript 语句实例化 JavascriptAction
JavascriptAction javaScript = new JavascriptAction("this.print({bUI:true,bSilent:false,bShrinkToFit:true});");

//将 JavascriptAction 对象分配给所需的文档操作
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

在本文中，我们解释了如何使用 Aspose.PDF for .NET 在文档级别和页面级别将 JavaScript 添加到 PDF 文件。我们提供了分步说明，并包含每个示例的完整源代码。有了这些知识，您就可以将 JavaScript 添加到您的 PDF 文件中，并根据您的需要自定义它们的行为。


