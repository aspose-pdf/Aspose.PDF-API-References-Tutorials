---
title: Hämta Resource Of Annotation
linktitle: Hämta Resource Of Annotation
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du hämtar resursen för en anteckning med Aspose.PDF för .NET med denna steg-för-steg-guide.
type: docs
weight: 90
url: /sv/net/annotations/getresourceofannotation/
---

Exemplet visar hur man skaffar anteckningsresurs med Aspose.PDF för .NET. För att få tillgång till en anteckning med Aspose.PDF för .NET, följ dessa steg:

## Steg 1: Ställ in sökvägen till katalogen där dokumentet finns.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 2: Öppna PDF-dokumentet som innehåller anteckningen vars resurs du vill hämta.

```csharp
Document doc = new Document(dataDir + "AddAnnotation.pdf");
```

## Steg 3: Skapa en anteckning.

```csharp
ScreenAnnotation sa = new ScreenAnnotation(doc.Pages[1], new Rectangle(100, 400, 300, 600), dataDir + "AddSwfFileAsAnnotation.swf");
```

## Steg 4: Lägg till anteckningen på en sida i dokumentet.

```csharp
doc.Pages[1].Annotations.Add(sa);
```

## Steg 5: Spara dokumentet.

```csharp
doc.Save(dataDir + "GetResourceOfAnnotation_Out.pdf");
```

## Steg 6: Öppna det ändrade dokumentet.

```csharp
Document doc1 = new Document(dataDir + "GetResourceOfAnnotation_Out.pdf");
```

## Steg 7: Få handlingen för annoteringen.

```csharp
RenditionAction action = (doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction;
```

## Steg 7: Hämta återgivningen av handlingen.

```csharp
Rendition rendition = ((doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction).Rendition;
```

## Steg 8: Hämta mediaklippet.

```csharp
MediaClip clip = (rendition as MediaRendition).MediaClip;
```

## Steg 9: Hämta filspecifikationen.

```csharp
FileSpecification data = (clip as MediaClipData).Data;
```

## Steg 10: Läs medias data.

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

## Steg 11: Skriv ut namnet på återgivningen och återgivningsoperationen.

```csharp
Console.WriteLine(rendition.Name);
Console.WriteLine(action.RenditionOperation);
```

Genom att följa dessa steg kan du enkelt få tillgång till en anteckning i ett PDF-dokument med Aspose.PDF för .NET.

### Exempel på källkod för Get Resource Of Annotation med Aspose.PDF för .NET:

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Öppna dokumentet
Document doc = new Document(dataDir + "AddAnnotation.pdf");
//Skapa anteckning
ScreenAnnotation sa = new ScreenAnnotation(doc.Pages[1], new Rectangle(100, 400, 300, 600), dataDir + "AddSwfFileAsAnnotation.swf");
doc.Pages[1].Annotations.Add(sa);
// Spara dokument
doc.Save(dataDir + "GetResourceOfAnnotation_Out.pdf");
// Öppna dokumentet
Document doc1 = new Document(dataDir + "GetResourceOfAnnotation_Out.pdf");
//Få handling av annoteringen
RenditionAction action = (doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction;
//Hämta återgivning av återgivningsåtgärden
Rendition rendition = ((doc.Pages[1].Annotations[1] as ScreenAnnotation).Action as RenditionAction).Rendition;
// Mediaklipp
MediaClip clip = (rendition as MediaRendition).MediaClip;
FileSpecification data = (clip as MediaClipData).Data;
MemoryStream ms = new MemoryStream();
byte[] buffer = new byte[1024];
int read = 0;
//Data för media är tillgängliga i FileSpecification.Contents
Stream source = data.Contents;
while ((read = source.Read(buffer, 0, buffer.Length)) > 0)
{
ms.Write(buffer, 0, read);
}
Console.WriteLine(rendition.Name);
Console.WriteLine(action.RenditionOperation);
```