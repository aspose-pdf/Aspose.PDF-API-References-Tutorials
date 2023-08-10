---
title: 获取 PDF 文件中的缩放系数
linktitle: 获取 PDF 文件中的缩放系数
second_title: Aspose.PDF for .NET API 参考
description: 通过此分步指南，了解如何使用 Aspose.PDF for .NET 获取 PDF 文件中的缩放系数。
type: docs
weight: 210
url: /zh/net/programming-with-document/getzoomfactor/
---
Aspose.PDF for .NET 是一个 PDF 操作库，它提供了许多功能来对 PDF 文档执行各种操作。这些功能之一是能够获取 PDF 文件中的缩放系数。在本教程中，我们将解释如何使用 Aspose.PDF for .NET 使用 C# 源代码获取 PDF 文件中的缩放系数。


## 步骤 1：实例化新的 Document 对象

使用 Aspose.PDF for .NET 获取 PDF 文件的缩放系数的第一步是实例化一个新的`Document`目的。这`Document`对象表示可以从文件或流加载的 PDF 文档。

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//实例化新的 Document 对象
Document doc = new Document(dataDir + "Zoomed_pdf.pdf");
```

在上面的代码中，我们创建了一个`Document`对象通过将 PDF 文件的路径传递给构造函数`Document`班级。您需要将“您的文档目录”替换为 PDF 文件所在目录的实际路径。

## 第2步：创建GoToAction对象

下一步是创建一个`GoToAction`目的。 A`GoToAction`对象表示前往 PDF 文档中特定目的地的操作。在我们的例子中，我们想要获取 PDF 文件的缩放系数，因此我们将使用`OpenAction`的财产`Document`对象得到`GoToAction`目的。

```csharp
//创建GoToAction对象
GoToAction action = doc.OpenAction as GoToAction;
```

在上面的代码中，我们创建了一个`GoToAction`通过投射对象`OpenAction`的财产`Document`反对`GoToAction`.

## 步骤3：获取PDF文件的缩放系数

第三步是获取PDF文件的缩放系数。我们可以通过访问来获取PDF文件的缩放系数`Destination`的财产`GoToAction`对象，然后将其投射到`XYZExplicitDestination`。这`XYZExplicitDestination`类表示 PDF 文档中的目的地，指定要转到的坐标和缩放系数。

```csharp
//获取PDF文件的缩放系数
System.Console.WriteLine((action.Destination as XYZExplicitDestination).Zoom); //文档缩放值；
```

在上面的代码中，我们访问了`Destination`的财产`GoToAction`对象，然后将其投射到`XYZExplicitDestination`。之后我们就可以访问到了`Zoom`的财产`XYZExplicitDestination`对象获取 PDF 文件的缩放系数。

## 第四步：输出缩放系数

最后一步是输出 PDF 文件的缩放系数。我们可以使用`System.Console.WriteLine`

```csharp
//获取PDF文件的缩放系数
System.Console.WriteLine((action.Destination as XYZExplicitDestination).Zoom); //文档缩放值；
```        

### 使用 Aspose.PDF for .NET 获取缩放系数的示例源代码

以下是使用 Aspose.PDF for .NET 获取缩放系数的完整示例源代码：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//实例化新的 Document 对象
Document doc = new Document(dataDir + "Zoomed_pdf.pdf");

//创建GoToAction对象
GoToAction action = doc.OpenAction as GoToAction;

//获取PDF文件的缩放系数
System.Console.WriteLine((action.Destination as XYZExplicitDestination).Zoom); //文档缩放值；
```

## 结论

在本教程中，我们探索了如何使用 Aspose.PDF for .NET 来获取 PDF 文件的缩放系数。缩放系数是 PDF 文档的一个重要方面，因为它决定了在查看器中打开时的初始显示大小。通过访问和利用缩放系数，开发人员可以为最终用户定制观看体验。 Aspose.PDF for .NET提供了一个简单而有效的API来从PDF文档中检索缩放系数和其他与导航相关的信息，使开发人员能够构建功能丰富的交互式PDF应用程序。

### 获取 PDF 文件缩放系数的常见问题解答

#### 问：PDF 文件的缩放系数是多少？

答：PDF 文件中的缩放系数是指查看文档时应用的放大级别。它决定 PDF 文件在屏幕上的初始显示大小。缩放系数为1.0表示实际尺寸（100%缩放），大于1.0表示放大，小于1.0表示缩小。

#### 问：如何在我的应用程序中使用缩放系数信息？

答：您可以使用缩放系数信息来自定义 PDF 文档在查看器中打开时的初始显示大小。例如，您可以设置特定的缩放系数以确保 PDF 以特定尺寸显示或使整个页面适合查看器的窗口。

#### 问：我可以使用 Aspose.PDF for .NET 以编程方式修改 PDF 文档的缩放系数吗？

答：是的，您可以使用 Aspose.PDF for .NET 以编程方式修改 PDF 文档的缩放系数。您可以为特定操作设置缩放系数，例如`GoToAction`或者`GoToRemoteAction`，控制当用户与链接或书签交互时文档的显示方式。

#### 问：是否有其他方法可以使用 Aspose.PDF for .NET 导航到 PDF 文档中的特定位置？

答：是的，Aspose.PDF for .NET 提供了各种功能来导航到 PDF 文档中的特定位置。除了使用`GoToAction`，您可以使用其他操作，例如`GoToURIAction`打开一个 URL，`GoToEmbeddedAction`导航到嵌入文件，以及`GoToNamedAction`转至 PDF 文档中的指定目的地。