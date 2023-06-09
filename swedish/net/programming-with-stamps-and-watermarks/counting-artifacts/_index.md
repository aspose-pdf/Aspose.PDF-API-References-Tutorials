---
title: Räknar artefakter
linktitle: Räknar artefakter
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du enkelt räknar vattenstämplar i dina PDF-dokument med Aspose.PDF för .NET.
type: docs
weight: 60
url: /sv/net/programming-with-stamps-and-watermarks/counting-artifacts/
---

I den här handledningen tar vi dig steg för steg om hur man räknar artefakter i ett PDF-dokument med Aspose.PDF för .NET. Vi visar dig hur du använder den medföljande C#-källkoden för att räkna antalet "vattenstämpel"-artefakter på en specifik sida i PDF-dokumentet.

## Steg 1: Sätta upp miljön

Innan du börjar, se till att du har följande:

- En installerad .NET-utvecklingsmiljö.
- Aspose.PDF-biblioteket för .NET laddas ner och refereras till i ditt projekt.

## Steg 2: Laddar PDF-dokumentet

Det första steget är att ladda det befintliga PDF-dokumentet i ditt projekt. Här är hur:

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Öppna dokumentet
Document pdfDocument = new Document(dataDir + "watermark.pdf");
```

Var noga med att ersätta "DIN DOKUMENTKATOLOG" med den faktiska sökvägen till katalogen där ditt PDF-dokument finns.

## Steg 3: Räkna artefakter

Nu när du har laddat PDF-dokumentet kan du räkna artefakter av typen "vattenstämpel" på en specifik sida i dokumentet. Här är hur:

```csharp
// Initiera räknaren
int count = 0;

// Gå igenom alla artefakter på första sidan
foreach(Artifact artifact in pdfDocument.Pages[1].Artifacts)
{
     // Om artefaktens undertyp är "vattenstämpel", öka räknaren
     if (artifact.Subtype == Artifact.ArtifactSubtype.Watermark)
         count++;
}

// Visa antalet artefakter av typen "vattenstämpel".
Console.WriteLine("The page contains " + count + " watermarks");
```

Ovanstående kod går igenom alla artefakter på första sidan i PDF-dokumentet och ökar räknaren för varje artefakt av typen "vattenstämpel".

### Exempel på källkod för att räkna artefakter med Aspose.PDF för .NET 
```csharp

// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Öppna dokumentet
Document pdfDocument = new Document( dataDir +  "watermark.pdf");

int count = 0;
foreach (Artifact artifact in pdfDocument.Pages[1].Artifacts)
{
	// Om artefakttypen är vattenstämpel, öka räknaren
	if (artifact.Subtype == Artifact.ArtifactSubtype.Watermark) count++;
}
Console.WriteLine("Page contains " + count + " watermarks");

```

## Slutsats

Grattis! Du lärde dig hur man räknar "vattenstämpel"-artefakter i ett PDF-dokument med Aspose.PDF för .NET. Du kan nu använda denna kunskap för att utföra specifik analys och bearbetning av artefakter i dina PDF-dokument.
