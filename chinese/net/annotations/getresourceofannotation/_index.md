---
title: 获取注解资源
linktitle: 获取注解资源
second_title: Aspose.PDF for .NET API 参考
description: 通过此分步指南了解如何使用 Aspose.PDF for .NET 检索注释资源。
type: docs
weight: 90
url: /zh/net/annotations/getresourceofannotation/
---

该示例显示了如何使用 Aspose.PDF for .NET 获取注释资源。要使用 Aspose.PDF for .NET 获取注释资源，请执行以下步骤：

## 第一步：设置文档所在目录的路径。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 第二步：打开包含要获取其资源的批注的PDF文档。

```csharp
Document doc = new Document(dataDir + "AddAnnotation.pdf");
```

## 第 3 步：创建注释。

```csharp
ScreenAnnotation sa = new ScreenAnnotation(doc.Pages[1], new Rectangle(100, 400, 300, 600), dataDir + "AddSwfFileAsAnnotation.swf");
```

## 第 4 步：将注释添加到文档中的页面。

```csharp
doc.Pages[1].Annotations.Add(sa);
```

## 第 5 步：保存文档。

```csharp
doc.Save(dataDir + "GetResourceOfAnnotation_Out.pdf");
```

## 第六步：打开修改后的文件。

```csharp
Document doc1 = new Document(dataDir + "GetResourceOfAnnotation_Out.pdf");
```

## 第七步：获取注解的动作。

```csharp
RenditionAction action = (doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction;
```

## 第 7 步：获取动作的再现。

```csharp
Rendition rendition = ((doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction).Rendition;
```

## 第 8 步：获取媒体剪辑。

```csharp
MediaClip clip = (rendition as MediaRendition).MediaClip;
```

## 第 9 步：获取文件规范。

```csharp
FileSpecification data = (clip as MediaClipData).Data;
```

## 第十步：读取媒体数据。

```csharp
MemoryStream ms = new MemoryStream();
byte[] buffer = new byte[1024];
int read = 0;
Stream source = data.Contents;
while ((read = source.Read(buffer, 0, buffer.Length)) > 0)
{
   ms.Write(buffer, 0, read);
}
```

## 第 11 步：打印再现的名称和再现操作。

```csharp
Console.WriteLine(rendition.Name);
Console.WriteLine(action.RenditionOperation);
```

按照这些步骤，您可以使用 Aspose.PDF for .NET 轻松获取 PDF 文档中注释的资源。

### 使用 Aspose.PDF for .NET 获取注释资源的示例源代码：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//打开文档
Document doc = new Document(dataDir + "AddAnnotation.pdf");
//创建注释
ScreenAnnotation sa = new ScreenAnnotation(doc.Pages[1], new Rectangle(100, 400, 300, 600), dataDir + "AddSwfFileAsAnnotation.swf");
doc.Pages[1].Annotations.Add(sa);
//保存文件
doc.Save(dataDir + "GetResourceOfAnnotation_Out.pdf");
//打开文档
Document doc1 = new Document(dataDir + "GetResourceOfAnnotation_Out.pdf");
//获取注解的动作
RenditionAction action = (doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction;
//获取演绎动作的演绎
Rendition rendition = ((doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction).Rendition;
//媒体剪辑
MediaClip clip = (rendition as MediaRendition).MediaClip;
FileSpecification data = (clip as MediaClipData).Data;
MemoryStream ms = new MemoryStream();
byte[] buffer = new byte[1024];
int read = 0;
//媒体数据可在 FileSpecification.Contents 中访问
Stream source = data.Contents;
while ((read = source.Read(buffer, 0, buffer.Length)) > 0)
{
ms.Write(buffer, 0, read);
}
Console.WriteLine(rendition.Name);
Console.WriteLine(action.RenditionOperation);
```