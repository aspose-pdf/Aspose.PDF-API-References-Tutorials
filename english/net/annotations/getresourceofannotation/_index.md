---
title: Get Resource Of Annotation
linktitle: Get Resource Of Annotation
second_title: Aspose.PDF for .NET API Reference
description: Learn how to retrieve the resource of an annotation using Aspose.PDF for .NET with this step-by-step guide.
type: docs
weight: 90
url: /net/annotations/getresourceofannotation/
---

The example shows how to get resource of annotation with Aspose.PDF for .NET. To get the resource of an annotation using Aspose.PDF for .NET, follow these steps:

## Step 1: Set the path of the directory where the document is located.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Step 2: Open the PDF document that contains the annotation whose resource you want to get.

```csharp
Document doc = new Document(dataDir + "AddAnnotation.pdf");
```

## Step 3: Create an annotation.

```csharp
ScreenAnnotation sa = new ScreenAnnotation(doc.Pages[1], new Rectangle(100, 400, 300, 600), dataDir + "AddSwfFileAsAnnotation.swf");
```

## Step 4: Add the annotation to a page in the document.

```csharp
doc.Pages[1].Annotations.Add(sa);
```

## Step 5: Save the document.

```csharp
doc.Save(dataDir + "GetResourceOfAnnotation_Out.pdf");
```

## Step 6: Open the modified document.

```csharp
Document doc1 = new Document(dataDir + "GetResourceOfAnnotation_Out.pdf");
```

## Step 7: Get the action of the annotation.

```csharp
RenditionAction action = (doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction;
```

## Step 7: Get the rendition of the action.

```csharp
Rendition rendition = ((doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction).Rendition;
```

## Step 8: Get the media clip.

```csharp
MediaClip clip = (rendition as MediaRendition).MediaClip;
```

## Step 9: Get the file specification.

```csharp
FileSpecification data = (clip as MediaClipData).Data;
```

## Step 10: Read the data of the media.

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

## Step 11: Print the name of the rendition and the rendition operation.

```csharp
Console.WriteLine(rendition.Name);
Console.WriteLine(action.RenditionOperation);
```

By following these steps, you can easily get the resource of an annotation in a PDF document using Aspose.PDF for .NET.

### Example source code for Get Resource Of Annotation using Aspose.PDF for .NET:

```csharp
// The path to the documents directory.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Open document
Document doc = new Document(dataDir + "AddAnnotation.pdf");
//Create annotation
ScreenAnnotation sa = new ScreenAnnotation(doc.Pages[1], new Rectangle(100, 400, 300, 600), dataDir + "AddSwfFileAsAnnotation.swf");
doc.Pages[1].Annotations.Add(sa);
// Save Doucument
doc.Save(dataDir + "GetResourceOfAnnotation_Out.pdf");
// Open document
Document doc1 = new Document(dataDir + "GetResourceOfAnnotation_Out.pdf");
//Get action of the annotation
RenditionAction action = (doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction;
//Get rendition of the rendition action
Rendition rendition = ((doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction).Rendition;
//Media Clip 
MediaClip clip = (rendition as MediaRendition).MediaClip;
FileSpecification data = (clip as MediaClipData).Data;
MemoryStream ms = new MemoryStream();
byte[] buffer = new byte[1024];
int read = 0;
//Data of media are accessible in FileSpecification.Contents
Stream source = data.Contents;
while ((read = source.Read(buffer, 0, buffer.Length)) > 0)
{
ms.Write(buffer, 0, read);
}
Console.WriteLine(rendition.Name);
Console.WriteLine(action.RenditionOperation);
```
