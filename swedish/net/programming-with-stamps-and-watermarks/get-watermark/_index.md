---
title: Skaffa vattenstämpel
linktitle: Skaffa vattenstämpel
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du extraherar vattenstämplar från dina PDF-dokument med Aspose.PDF för .NET.
type: docs
weight: 100
url: /sv/net/programming-with-stamps-and-watermarks/get-watermark/
---
I den här handledningen tar vi dig steg för steg om hur du får en vattenstämpel från ett PDF-dokument med Aspose.PDF för .NET. Vi visar dig hur du använder den medföljande C#-källkoden för att iterera genom artefakterna på en specifik sida och få vattenstämpeltyp, text och plats.

## Steg 1: Sätta upp miljön

Innan du börjar, se till att du har följande:

- En installerad .NET-utvecklingsmiljö.
- Aspose.PDF-biblioteket för .NET laddas ner och refereras till i ditt projekt.

## Steg 2: Laddar PDF-dokumentet

Det första steget är att ladda det befintliga PDF-dokumentet i ditt projekt. Här är hur:

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Öppna PDF-dokumentet
Document pdfDocument = new Document(dataDir + "watermark.pdf");
```

Var noga med att ersätta "DIN DOKUMENTKATOLOG" med den faktiska sökvägen till katalogen där ditt PDF-dokument finns.

## Steg 3: Skaffa vattenstämpeln

Nu när du har laddat PDF-dokumentet kan du iterera genom de specifika sidartefakterna för att få information om vattenstämpeln. Här är hur:

```csharp
// Bläddra bland artefakter och få vattenstämpel undertyp, text och plats
foreach(Artifact artifact in pdfDocument.Pages[1].Artifacts)
{
     Console.WriteLine(artifact.Subtype + " " + artifact.Text + " " + artifact.Rectangle);
}
```

Ovanstående kod går igenom alla artefakter på första sidan i PDF-dokumentet och visar undertypen, texten och rektangeln (plats) för varje vattenstämpel som påträffas.

### Exempel på källkod för Get Watermark med Aspose.PDF för .NET 
```csharp

// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Öppna dokumentet
Document pdfDocument = new Document( dataDir +  "watermark.pdf");

// Iterera igenom och få typ av badkar, text och plats för artefakten
foreach (Artifact artifact in pdfDocument.Pages[1].Artifacts)
{
	Console.WriteLine(artifact.Subtype + " " + artifact.Text + " " + artifact.Rectangle);
}

```

## Slutsats

Grattis! Du har lärt dig hur du får vattenstämpelinformation från ett PDF-dokument med Aspose.PDF för .NET. Nu kan du använda denna kunskap för att analysera och bearbeta vattenstämplar i dina PDF-dokument.
