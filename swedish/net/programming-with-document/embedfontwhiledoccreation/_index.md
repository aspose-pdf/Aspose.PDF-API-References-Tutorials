---
title: Bädda in teckensnitt medan du skapar dokument
linktitle: Bädda in teckensnitt medan du skapar dokument
second_title: Aspose.PDF för .NET API-referens
description: Lär dig hur du bäddar in ett teckensnitt samtidigt som du skapar ett PDF-dokument med Aspose.PDF för .NET. Säkerställ korrekt visning på olika enheter.
type: docs
weight: 140
url: /sv/net/programming-with-document/embedfontwhiledoccreation/
---

den här handledningen kommer vi att diskutera hur man bäddar in ett teckensnitt samtidigt som man skapar ett PDF-dokument med Aspose.PDF för .NET. Aspose.PDF för .NET är ett kraftfullt bibliotek som låter utvecklare skapa, redigera och manipulera PDF-dokument programmatiskt. Det här biblioteket erbjuder ett brett utbud av funktioner för att arbeta med PDF-dokument, inklusive att lägga till text, bilder, tabeller och mycket mer. Att bädda in typsnitt när man skapar ett PDF-dokument är ett vanligt krav för utvecklare som vill säkerställa att PDF-dokumentet visas korrekt på olika enheter, oavsett om de nödvändiga typsnitten är installerade på dessa enheter eller inte.

## Steg 1: Skapa en ny C# Console Application
För att komma igång, skapa en ny C# Console Application i Visual Studio. Du kan namnge det vad du vill. När projektet har skapats måste du lägga till en referens till Aspose.PDF för .NET-biblioteket.

## Steg 2: Importera Aspose.PDF-namnområdet
Lägg till följande kodrad överst i din C#-fil för att importera Aspose.PDF-namnrymden:

```csharp
using Aspose.Pdf;
```

## Steg 3: Instantiera ett PDF-objekt
Instantiera ett Pdf-objekt genom att anropa dess tomma konstruktor:

```csharp
Aspose.Pdf.Document doc = new Aspose.Pdf.Document();
```

## Steg 4: Skapa ett avsnitt i Pdf-objektet
Skapa ett avsnitt i Pdf-objektet:

```csharp
Aspose.Pdf.Page page = doc.Pages.Add();
```

## Steg 5: Lägg till text i avsnittet
Lägg till text i avsnittet:

```csharp
Aspose.Pdf.Text.TextFragment fragment = new Aspose.Pdf.Text.TextFragment("");
Aspose.Pdf.Text.TextSegment segment = new Aspose.Pdf.Text.TextSegment(" This is a sample text using Custom font.");
```

## Steg 6: Ställ in typsnittet och bädda in det
Ställ in typsnittet och bädda in det:

```csharp
Aspose.Pdf.Text.TextState ts = new Aspose.Pdf.Text.TextState();
ts.Font = FontRepository.FindFont("Arial");
ts.Font.IsEmbedded = true;
segment.TextState = ts;
fragment.Segments.Add(segment);
page.Paragraphs.Add(fragment);
```

## Steg 7: Spara PDF-dokumentet
När du har bäddat in teckensnittet medan du skapar PDF-dokumentet måste du spara dokumentet:

```csharp
dataDir = dataDir + "EmbedFontWhileDocCreation_out.pdf";
// Spara PDF-dokument
doc.Save(dataDir);
```

### Exempel på källkod för Embed Font While Doc Creation med Aspose.PDF för .NET

```csharp

            
            // Sökvägen till dokumentkatalogen.
            string dataDir = "YOUR DOCUMENT DIRECTORY";

            // Instantiera Pdf-objekt genom att anropa dess tomma konstruktor
            Aspose.Pdf.Document doc = new Aspose.Pdf.Document();

            // Skapa ett avsnitt i Pdf-objektet
            Aspose.Pdf.Page page = doc.Pages.Add();

            Aspose.Pdf.Text.TextFragment fragment = new Aspose.Pdf.Text.TextFragment("");

            Aspose.Pdf.Text.TextSegment segment = new Aspose.Pdf.Text.TextSegment(" This is a sample text using Custom font.");
            Aspose.Pdf.Text.TextState ts = new Aspose.Pdf.Text.TextState();
            ts.Font = FontRepository.FindFont("Arial");
            ts.Font.IsEmbedded = true;
            segment.TextState = ts;
            fragment.Segments.Add(segment);
            page.Paragraphs.Add(fragment);

            dataDir = dataDir + "EmbedFontWhileDocCreation_out.pdf";
            // Spara PDF-dokument
            doc.Save(dataDir);
            
            
        
```

## Slutsats
I den här handledningen har vi diskuterat hur man bäddar in ett teckensnitt samtidigt som man skapar ett PDF-dokument med Aspose.PDF för .NET. Aspose.PDF för .NET tillhandahåller ett enkelt och lättanvänt API för att arbeta med PDF-dokument, inklusive att lägga till och bädda in teckensnitt. Att bädda in teckensnitt när du skapar ett PDF-dokument är ett viktigt steg för att säkerställa att dokumentet visas korrekt på olika enheter, oavsett om de nödvändiga typsnitten är installerade på dessa enheter eller inte.

