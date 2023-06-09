---
title: Ta bort visst bokmärke
linktitle: Ta bort visst bokmärke
second_title: Aspose.PDF för .NET API Referens
description: Ta enkelt bort ett visst bokmärke från dina PDF-filer med Aspose.PDF för .NET.
type: docs
weight: 40
url: /sv/net/programming-with-bookmarks/delete-particular-bookmark/
---

Det kan vara nödvändigt att ta bort ett visst bokmärke från ett PDF-dokument. Med Aspose.PDF för .NET kan du enkelt ta bort ett visst bokmärke genom att följa följande källkod:

## Steg 1: Importera nödvändiga bibliotek

Innan du börjar måste du importera de nödvändiga biblioteken för ditt C#-projekt. Här är det nödvändiga importdirektivet:

```csharp
using Aspose.Pdf;
```

## Steg 2: Ange sökväg till dokumentmappen

 I det här steget måste du ange sökvägen till mappen som innehåller PDF-filen från vilken du vill ta bort ett visst bokmärke. Byta ut`"YOUR DOCUMENT DIRECTORY"` i följande kod med den faktiska sökvägen till din dokumentmapp:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 3: Öppna PDF-dokumentet

Nu ska vi öppna PDF-dokumentet från vilket vi vill ta bort ett bokmärke med hjälp av följande kod:

```csharp
Document pdfDocument = new Document(dataDir + "DeleteParticularBookmark.pdf");
```

## Steg 4: Ta bort ett visst bokmärke

 I det här steget tar vi bort ett visst bokmärke med hjälp av`Delete` metod för`Outlines` fast egendom. Vi anger titeln på bokmärket som ska raderas. Här är motsvarande kod:

```csharp
pdfDocument.Outlines.Delete("Child Outline");
```

## Steg 5: Spara den uppdaterade filen

 Slutligen sparar vi den uppdaterade PDF-filen med hjälp av`Save` metod för`pdfDocument` objekt. Här är motsvarande kod:

```csharp
dataDir = dataDir + "DeleteParticularBookmark_out.pdf";
pdfDocument.Save(dataDir);
```

### Exempel på källkod för Ta bort särskilt bokmärke med Aspose.PDF för .NET 
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Öppna dokumentet
Document pdfDocument = new Document(dataDir + "DeleteParticularBookmark.pdf");
// Ta bort en viss kontur efter rubrik
pdfDocument.Outlines.Delete("Child Outline");
dataDir = dataDir + "DeleteParticularBookmark_out.pdf";
// Spara uppdaterad fil
pdfDocument.Save(dataDir);
Console.WriteLine("\nParticular bookmark deleted successfully.\nFile saved at " + dataDir);
```

## Slutsats

Grattis! Nu har du en steg-för-steg-guide för att ta bort ett visst bokmärke med Aspose.PDF för .NET. Du kan använda den här koden för att rikta in och ta bort specifika bokmärken från dina PDF-dokument.

Se till att kolla in den officiella Aspose.PDF-dokumentationen för mer information om avancerade bokmärkesmanipuleringsfunktioner.