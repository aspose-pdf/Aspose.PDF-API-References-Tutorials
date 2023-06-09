---
title: Ta bort bilder
linktitle: Ta bort bilder
second_title: Aspose.PDF för .NET API Referens
description: Radera enkelt bilder från en PDF-fil med Aspose.PDF för .NET.
type: docs
weight: 110
url: /sv/net/programming-with-images/delete-images/
---

Den här guiden tar dig steg för steg hur du tar bort bilder från en PDF-fil med Aspose.PDF för .NET. Se till att du redan har konfigurerat din miljö och följ stegen nedan:

## Steg 1: Definiera dokumentkatalogen

 Innan du börjar, se till att du ställer in rätt katalog för dokumenten. Byta ut`"YOUR DOCUMENT DIRECTORY"` i koden med sökvägen till katalogen där ditt PDF-dokument finns.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 2: Öppna PDF-dokumentet

 I det här steget kommer vi att öppna PDF-dokumentet med hjälp av`Document` klass av Aspose.PDF. Använd`Document` konstruktor och skicka sökvägen till PDF-dokumentet.

```csharp
Document pdfDocument = new Document(dataDir + "DeleteImages.pdf");

```

## Steg 3: Ta bort en specifik bild

 I det här steget kommer vi att ta bort en specifik bild från en viss sida. Använd`Delete` metod för sidresursen`Images` objekt för att ta bort bilden. I exemplet nedan tar vi bort bilden med index 1 från första sidan.

```csharp
pdfDocument.Pages[1].Resources.Images.Delete(1);
```

## Steg 4: Spara den uppdaterade PDF-filen

 Spara den uppdaterade PDF-filen med hjälp av`Save` metod för`pdfDocument` objekt. Ange utdatasökvägen för PDF-filen.

```csharp
dataDir = dataDir + "DeleteImages_out.pdf";
pdfDocument.Save(dataDir);
```

### Exempel på källkod för Ta bort bilder med Aspose.PDF för .NET 
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Öppna dokumentet
Document pdfDocument = new Document(dataDir+ "DeleteImages.pdf");
//Ta bort en viss bild
pdfDocument.Pages[1].Resources.Images.Delete(1);
dataDir = dataDir + "DeleteImages_out.pdf";
// Spara uppdaterad PDF-fil
pdfDocument.Save(dataDir);
Console.WriteLine("\nImages deleted successfully.\nFile saved at " + dataDir); 
```

## Slutsats

Grattis! Du har raderat bilder från en PDF-fil med Aspose.PDF för .NET. Den uppdaterade PDF-filen sparas i den angivna katalogen. Du kan nu använda denna PDF-fil utan de raderade bilderna.