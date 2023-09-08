---
title: 获取注释资源
linktitle: 获取注释资源
second_title: Aspose.PDF for .NET API 参考
description: 通过此分步指南，了解如何使用 Aspose.PDF for .NET 检索注释资源。
type: docs
weight: 90
url: /zh/net/annotations/getresourceofannotation/
---
该示例展示了如何使用 Aspose.PDF for .NET 获取注释资源。要使用 Aspose.PDF for .NET 获取注释资源，请按照下列步骤操作：

## 第一步：设置文档所在目录的路径。

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## 步骤2：打开包含您要获取其资源的注释的PDF文档。

```csharp
Document doc = new Document(dataDir + "AddAnnotation.pdf");
```

## 步骤 3：创建注释。

```csharp
ScreenAnnotation sa = new ScreenAnnotation(doc.Pages[1], new Rectangle(100, 400, 300, 600), dataDir + "AddSwfFileAsAnnotation.swf");
```

## 步骤 4：将注释添加到文档中的页面。

```csharp
doc.Pages[1].Annotations.Add(sa);
```

## 步骤5：保存文档。

```csharp
doc.Save(dataDir + "GetResourceOfAnnotation_Out.pdf");
```

## 第六步：打开修改后的文档。

```csharp
Document doc1 = new Document(dataDir + "GetResourceOfAnnotation_Out.pdf");
```

## 步骤7：获取注解的action。

```csharp
RenditionAction action = (doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction;
```

## 第7步：获取动作的再现。

```csharp
Rendition rendition = ((doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction).Rendition;
```

## 第8步：获取媒体剪辑。

```csharp
MediaClip clip = (rendition as MediaRendition).MediaClip;
```

## 步骤9：获取文件规范。

```csharp
FileSpecification data = (clip as MediaClipData).Data;
```

## 步骤10：读取媒体数据。

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

## 第11步：打印再现的名称和再现操作。

```csharp
Console.WriteLine(rendition.Name);
Console.WriteLine(action.RenditionOperation);
```

通过执行以下步骤，您可以使用 Aspose.PDF for .NET 轻松获取 PDF 文档中的注释资源。

### 使用 Aspose.PDF for .NET 获取注释资源的示例源代码：

```csharp
//文档目录的路径。
string dataDir = "YOUR DOCUMENT DIRECTORY";

//打开文档
Document doc = new Document(dataDir + "AddAnnotation.pdf");
//创建注释
ScreenAnnotation sa = new ScreenAnnotation(doc.Pages[1], new Rectangle(100, 400, 300, 600), dataDir + "AddSwfFileAsAnnotation.swf");
doc.Pages[1].Annotations.Add(sa);
//保存文档
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

## 结论

在本教程中，我们探讨了如何使用 Aspose.PDF for .NET 从 PDF 文档获取特定注释的资源。通过遵循分步指南并使用提供的 C# 源代码，开发人员可以轻松访问和管理 PDF 文档中的注释，包括再现注释。

### 常见问题解答

#### 问：什么是 PDF 注释上下文中的再现？

答：在 PDF 注释的上下文中，再现是多媒体内容演示。它允许在 PDF 文档中嵌入多媒体，例如音频或视频。再现注释指定要呈现的媒体及其播放方式。

#### 问：我可以获得与演绎注释关联的媒体文件的名称吗？

答：是的，您可以使用 Aspose.PDF for .NET 获取与再现注释关联的媒体文件的名称。媒体文件名可以通过以下方式访问`FileSpecification`的`MediaClip`目的。

#### 问：Aspose.PDF for .NET 能否从再现注释中提取媒体文件？

答：是的，Aspose.PDF for .NET 可以从再现注释中提取媒体数据（包括音频或视频内容），并将其保存为单独的文件。

#### 问：如何访问再现注释的媒体数据？

 A：可以通过以下方式访问再现注释的媒体数据：`FileSpecification.Contents`的财产`MediaClipData`目的。

#### 问：我可以使用 Aspose.PDF for .NET 修改与再现注释关联的媒体吗？

答：Aspose.PDF for .NET 提供了访问和修改与再现注释关联的媒体数据的方法。您可以更新或替换再现注释所使用的媒体文件。