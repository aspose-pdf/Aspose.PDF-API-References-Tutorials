---
title: 获取 PDF 文件中的缩放系数
linktitle: 获取 PDF 文件中的缩放系数
second_title: Aspose.PDF for .NET API 参考
description: 通过本分步指南了解如何使用 Aspose.PDF for .NET 获取 PDF 文件中的缩放系数。
type: docs
weight: 210
url: /zh/net/programming-with-document/getzoomfactor/
---
Aspose.PDF for .NET 是一个 PDF 操作库，它提供了许多功能来对 PDF 文档执行各种操作。这些功能之一是能够获取 PDF 文件中的缩放系数。在本教程中，我们将解释如何使用 Aspose.PDF for .NET 使用 C# 源代码获取 PDF 文件中的缩放系数。


## 步骤 1：实例化新的 Document 对象

使用 Aspose.PDF for .NET 获取 PDF 文件的缩放系数的第一步是实例化一个新的`Document`对象。`Document`对象表示可以从文件或流加载的 PDF 文档。

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//实例化新的 Document 对象
Document doc = new Document(dataDir + "Zoomed_pdf.pdf");
```

在上面的代码中，我们创建了一个`Document`通过将 PDF 文件的路径传递给`Document`类。您需要将“YOUR DOCUMENT DIRECTORY”替换为您的 PDF 文件所在目录的实际路径。

## 步骤 2：创建 GoToAction 对象

下一步是创建一个`GoToAction`对象。一个`GoToAction`对象表示转到 PDF 文档中的特定目标的操作。在我们的例子中，我们想要获取 PDF 文件的缩放系数，因此我们将使用`OpenAction`的财产`Document`对象来获取`GoToAction`目的。

```csharp
//创建 GoToAction 对象
GoToAction action = doc.OpenAction as GoToAction;
```

在上面的代码中，我们创建了一个`GoToAction`通过投射对象`OpenAction`的财产`Document`反对`GoToAction`.

## 步骤 3：获取 PDF 文件的缩放比例

第三步是获取 PDF 文件的缩放比例。我们可以通过访问`Destination`的财产`GoToAction`对象然后将其转换为`XYZExplicitDestination` 。 这`XYZExplicitDestination`该类代表 PDF 文档中的目标位置，指定要到达的坐标和缩放比例。

```csharp
//获取 PDF 文件的缩放比例
System.Console.WriteLine((action.Destination as XYZExplicitDestination).Zoom); //文档缩放值；
```

在上面的代码中，我们访问了`Destination`的财产`GoToAction`对象然后将其转换为`XYZExplicitDestination`之后，我们访问了`Zoom`的财产`XYZExplicitDestination`对象来获取 PDF 文件的缩放系数。

## 步骤 4：输出缩放系数

最后一步是输出 PDF 文件的缩放比例。我们可以使用`System.Console.WriteLine`

```csharp
//获取 PDF 文件的缩放比例
System.Console.WriteLine((action.Destination as XYZExplicitDestination).Zoom); //文档缩放值；
```        

### 使用 Aspose.PDF for .NET 获取缩放系数的示例源代码

以下是使用 Aspose.PDF for .NET 获取缩放系数的完整示例源代码：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//实例化新的 Document 对象
Document doc = new Document(dataDir + "Zoomed_pdf.pdf");

//创建 GoToAction 对象
GoToAction action = doc.OpenAction as GoToAction;

//获取 PDF 文件的缩放比例
System.Console.WriteLine((action.Destination as XYZExplicitDestination).Zoom); //文档缩放值；
```

## 结论

在本教程中，我们探讨了如何使用 Aspose.PDF for .NET 获取 PDF 文件的缩放系数。缩放系数是 PDF 文档的一个重要方面，因为它决定了在查看器中打开时的初始显示大小。通过访问和利用缩放系数，开发人员可以为最终用户定制查看体验。Aspose.PDF for .NET 提供了一个简单有效的 API 来从 PDF 文档中检索缩放系数和其他导航相关信息，使开发人员能够构建功能丰富且交互式的 PDF 应用程序。

### 获取 PDF 文件中缩放比例的常见问题解答

#### 问：PDF 文件的缩放比例是多少？

答：PDF 文件中的缩放系数是指查看文档时应用的放大倍数。它决定了 PDF 文件在屏幕上的初始显示大小。缩放系数 1.0 表示实际大小（100% 缩放），缩放系数大于 1.0 表示放大，缩放系数小于 1.0 表示缩小。

#### 问：如何在我的应用程序中使用缩放系数信息？

答：您可以使用缩放比例信息来自定义 PDF 文档在查看器中打开时的初始显示大小。例如，您可以设置特定的缩放比例以确保 PDF 以特定大小显示或使整个页面适合查看器的窗口。

#### 问：我可以使用 Aspose.PDF for .NET 以编程方式修改 PDF 文档的缩放比例吗？

答：是的，您可以使用 Aspose.PDF for .NET 以编程方式修改 PDF 文档的缩放比例。您可以为特定操作设置缩放比例，例如`GoToAction`或者`GoToRemoteAction`，控制用户与链接或书签交互时文档的显示方式。

#### 问：还有其他方法可以使用 Aspose.PDF for .NET 导航到 PDF 文档中的特定位置吗？

答：是的，Aspose.PDF for .NET 提供了各种功能来导航到 PDF 文档中的特定位置。除了使用`GoToAction`，您可以使用其他操作，例如`GoToURIAction`打开 URL，`GoToEmbeddedAction`导航至嵌入文件，以及`GoToNamedAction`前往 PDF 文档内的指定目的地。