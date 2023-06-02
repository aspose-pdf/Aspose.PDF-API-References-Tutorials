---
title: 获取缩放因子
linktitle: 获取缩放因子
second_title: Aspose.PDF for .NET API 参考
description: 通过此分步指南了解如何使用 Aspose.PDF for .NET 获取 PDF 文件的缩放系数。
type: docs
weight: 210
url: /zh/net/programming-with-document/getzoomfactor/
---
Aspose.PDF for .NET 是一个 PDF 操作库，它提供了许多功能来对 PDF 文档执行各种操作。这些功能之一是能够获取 PDF 文件的缩放系数。在本教程中，我们将解释如何使用 C# 源代码使用 Aspose.PDF for .NET 获取 PDF 文件的缩放因子。


## 第 1 步：实例化新的 Document 对象

使用 Aspose.PDF for .NET 获取 PDF 文件缩放因子的第一步是实例化一个新的`Document`目的。这`Document`对象表示可以从文件或流中加载的 PDF 文档。

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//实例化新的文档对象
Document doc = new Document(dataDir + "Zoomed_pdf.pdf");
```

在上面的代码中，我们创建了一个`Document`通过将 PDF 文件的路径传递给`Document`班级。您需要将“您的文档目录”替换为您的 PDF 文件所在目录的实际路径。

## 第 2 步：创建 GoToAction 对象

下一步是创建一个`GoToAction`目的。 A`GoToAction`对象表示转到 PDF 文档中特定目标的操作。在我们的例子中，我们想要获得 PDF 文件的缩放系数，所以我们将使用`OpenAction`的财产`Document`对象得到`GoToAction`目的。

```csharp
//创建 GoToAction 对象
GoToAction action = doc.OpenAction as GoToAction;
```

在上面的代码中，我们创建了一个`GoToAction`通过铸造对象`OpenAction`的财产`Document`反对`GoToAction`.

## 第 3 步：获取 PDF 文件的缩放系数

第三步是获取PDF文件的缩放因子。我们可以通过访问获取PDF文件的缩放因子`Destination`的财产`GoToAction`对象，然后将其投射到`XYZExplicitDestination`.这`XYZExplicitDestination`类表示 PDF 文档中的目标，指定要到达的坐标和缩放系数。

```csharp
//获取 PDF 文件的缩放因子
System.Console.WriteLine((action.Destination as XYZExplicitDestination).Zoom); //文档缩放值；
```

在上面的代码中，我们访问了`Destination`的财产`GoToAction`对象，然后将其投射到`XYZExplicitDestination`.之后，我们访问了`Zoom`的财产`XYZExplicitDestination`对象获取 PDF 文件的缩放系数。

## 第 4 步：输出缩放因子

最后一步是输出 PDF 文件的缩放系数。我们可以使用`System.Console.WriteLine`

```csharp
//获取 PDF 文件的缩放因子
System.Console.WriteLine((action.Destination as XYZExplicitDestination).Zoom); //文档缩放值；
```        

### 使用 Aspose.PDF for .NET 获取缩放因子的示例源代码

下面是使用 Aspose.PDF for .NET 获取缩放因子的完整示例源代码：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//实例化新的文档对象
Document doc = new Document(dataDir + "Zoomed_pdf.pdf");

//创建 GoToAction 对象
GoToAction action = doc.OpenAction as GoToAction;

//获取 PDF 文件的缩放因子
System.Console.WriteLine((action.Destination as XYZExplicitDestination).Zoom); //文档缩放值；
```
