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

## Slutsats

I den här handledningen undersökte vi hur man hämtar resursen för en viss anteckning från ett PDF-dokument med Aspose.PDF för .NET. Genom att följa steg-för-steg-guiden och använda den medföljande C#-källkoden kan utvecklare enkelt komma åt och hantera kommentarer, inklusive återgivningskommentarer, i sina PDF-dokument.

### FAQ's

#### F: Vad är en återgivning i samband med PDF-kommentarer?

S: I samband med PDF-kommentarer är en återgivning en presentation av multimediainnehåll. Det gör det möjligt att bädda in multimedia, såsom ljud eller video, i PDF-dokumentet. Återgivningskommentaren anger media som ska presenteras och hur det ska spelas.

#### F: Kan jag få namnet på mediafilen som är kopplad till en återgivningskommentar?

S: Ja, du kan få namnet på mediafilen som är associerad med en återgivningskommentar med Aspose.PDF för .NET. Mediafilens namn kan nås via`FileSpecification` av`MediaClip` objekt.

#### F: Kan Aspose.PDF för .NET extrahera mediefiler från en återgivningskommentar?

S: Ja, Aspose.PDF för .NET kan extrahera mediadata från en återgivningskommentar, som inkluderar ljud- eller videoinnehåll, och spara den som en separat fil.

#### F: Hur får jag åtkomst till mediadata för en återgivningskommentar?

 S: Mediedata för en återgivningskommentar kan nås via`FileSpecification.Contents` egendom av`MediaClipData` objekt.

#### F: Kan jag modifiera media som är kopplade till en återgivningsanteckning med Aspose.PDF för .NET?

S: Aspose.PDF för .NET tillhandahåller metoder för att komma åt och ändra mediadata som är associerade med en återgivningskommentar. Du kan uppdatera eller ersätta mediafilen som används av en återgivningskommentar.