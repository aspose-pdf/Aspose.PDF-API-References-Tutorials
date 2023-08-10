---
title: Ta bort all text från PDF
linktitle: Ta bort all text från PDF
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du tar bort all text från ett PDF-dokument med Aspose.PDF för .NET.
type: docs
weight: 290
url: /sv/net/programming-with-text/remove-all-text-from-pdf/
---

 I den här handledningen kommer vi att förklara hur man tar bort all text från ett PDF-dokument med hjälp av Aspose.PDF-biblioteket för .NET. Vi kommer att gå igenom steg-för-steg-processen för att öppna en PDF, med hjälp av en`TextFragmentAbsorber` för att ta bort all text och spara den modifierade PDF-filen med den medföljande C#-källkoden.

## Krav

Innan du börjar, se till att du har följande:

- Aspose.PDF för .NET-biblioteket installerat.
- En grundläggande förståelse för C#-programmering.

## Steg 1: Konfigurera dokumentkatalogen

 Först måste du ställa in sökvägen till katalogen där dina PDF-filer finns. Byta ut`"YOUR DOCUMENT DIRECTORY"` i`dataDir` variabel med sökvägen till dina PDF-filer.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 2: Öppna PDF-dokumentet

 Därefter öppnar vi PDF-dokumentet med hjälp av`Document` klass från Aspose.PDF-biblioteket.

```csharp
Document pdfDocument = new Document(dataDir + "RemoveAllText.pdf");
```

## Steg 3: Ta bort all text

 Vi initierar en`TextFragmentAbsorber`objekt och använd det för att ta bort all absorberad text från PDF-dokumentet.

```csharp
TextFragmentAbsorber absorb = new TextFragmentAbsorber();
absorb. RemoveAllText(pdfDocument);
```

## Steg 4: Spara den modifierade PDF-filen

Slutligen sparar vi det modifierade PDF-dokumentet till den angivna utdatafilen.

```csharp
pdfDocument.Save(dataDir + "RemoveAllText_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

### Exempel på källkod för Ta bort all text från PDF med Aspose.PDF för .NET 
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Öppna dokumentet
Document pdfDocument = new Document(dataDir + "RemoveAllText.pdf");
// Initiera TextFragmentAbsorber
TextFragmentAbsorber absorber = new TextFragmentAbsorber();
// Ta bort all absorberad text
absorber.RemoveAllText(pdfDocument);
// Spara dokumentet
pdfDocument.Save(dataDir + "RemoveAllText_out.pdf", Aspose.Pdf.SaveFormat.Pdf);
```

## Slutsats

 I den här handledningen har du lärt dig hur du tar bort all text från ett PDF-dokument med Aspose.PDF-biblioteket för .NET. Genom att följa steg-för-steg-guiden och exekvera den medföljande C#-koden kan du öppna en PDF, ta bort all text med en`TextFragmentAbsorber`och spara den ändrade PDF-filen.