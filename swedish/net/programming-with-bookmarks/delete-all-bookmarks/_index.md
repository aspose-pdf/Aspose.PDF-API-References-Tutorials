---
title: Ta bort alla bokmärken
linktitle: Ta bort alla bokmärken
second_title: Aspose.PDF för .NET API Referens
description: Ta enkelt bort alla bokmärken från dina PDF-filer med Aspose.PDF för .NET.
type: docs
weight: 30
url: /sv/net/programming-with-bookmarks/delete-all-bookmarks/
---

# Ta bort alla bokmärken med Aspose.PDF för .NET

Att ta bort bokmärken från ett PDF-dokument kan vara nödvändigt i vissa fall. Med Aspose.PDF för .NET kan du enkelt ta bort alla bokmärken genom att följa följande källkod:

## Steg 1: Importera nödvändiga bibliotek

Innan du börjar måste du importera de nödvändiga biblioteken för ditt C#-projekt. Här är det nödvändiga importdirektivet:

```csharp
using Aspose.Pdf;
```

## Steg 2: Ange sökväg till dokumentmappen

 I det här steget måste du ange sökvägen till mappen som innehåller PDF-filen från vilken du vill ta bort bokmärken. Byta ut`"YOUR DOCUMENT DIRECTORY"` i följande kod med den faktiska sökvägen till din dokumentmapp:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 3: Öppna PDF-dokumentet

Nu ska vi öppna PDF-dokumentet från vilket vi vill ta bort bokmärkena med hjälp av följande kod:

```csharp
Document pdfDocument = new Document(dataDir + "DeleteAllBookmarks.pdf");
```

## Steg 4: Ta bort alla bokmärken

 I det här steget tar vi bort alla bokmärken från dokumentet med hjälp av`Delete` metod för`Outlines` fast egendom. Här är motsvarande kod:

```csharp
pdfDocument.Outlines.Delete();
```

## Steg 5: Spara den uppdaterade filen

 Slutligen sparar vi den uppdaterade PDF-filen med hjälp av`Save` metod för`pdfDocument` objekt. Här är motsvarande kod:

```csharp
dataDir = dataDir + "DeleteAllBookmarks_out.pdf";
pdfDocument.Save(dataDir);
```

### Exempel på källkod för Ta bort alla bokmärken med Aspose.PDF för .NET 
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Öppna dokumentet
Document pdfDocument = new Document(dataDir + "DeleteAllBookmarks.pdf");
// Ta bort alla bokmärken
pdfDocument.Outlines.Delete();
dataDir = dataDir + "DeleteAllBookmarks_out.pdf";
// Spara uppdaterad fil
pdfDocument.Save(dataDir);
Console.WriteLine("\nAll bookmarks deleted successfully.\nFile saved at " + dataDir);
```

## Slutsats

Grattis! Nu har du en steg-för-steg-guide för att ta bort alla bokmärken med Aspose.PDF för .NET. Du kan använda den här koden för att rensa dina PDF-dokument genom att ta bort alla befintliga bokmärken.

Se till att kolla in den officiella Aspose.PDF-dokumentationen för mer information om avancerade bokmärkesmanipuleringsfunktioner.