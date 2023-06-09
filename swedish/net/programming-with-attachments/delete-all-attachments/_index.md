---
title: Ta bort alla bilagor
linktitle: Ta bort alla bilagor
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du tar bort alla bilagor från en PDF-fil med Aspose.PDF för .NET. Steg-för-steg-guide för enkel hantering.
type: docs
weight: 20
url: /sv/net/programming-with-attachments/delete-all-attachments/
---
I den här handledningen går vi igenom följande C#-källkod steg för steg för att ta bort alla bilagor från en PDF-fil med Aspose.PDF för .NET.

Se till att du har installerat Aspose.PDF-biblioteket och ställt in din utvecklingsmiljö innan du börjar. Har även grundläggande kunskaper i C#-programmering.

### Steg 1: Installation av dokumentkatalog

den medföljande källkoden måste du ange katalogen där PDF-filen finns från vilken du vill ta bort bilagorna. Ändra variabeln "dataDir" till önskad katalog.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### Steg 2: Öppna det befintliga PDF-dokumentet

Vi öppnar det befintliga PDF-dokumentet med den angivna sökvägen.

```csharp
Document pdfDocument = new Document(dataDir + "DeleteAllAttachments.pdf");
```

### Steg 3: Ta bort alla bilagor

Vi tar bort alla bilagor från dokumentet.

```csharp
pdfDocument.EmbeddedFiles.Delete();
```

### Steg 4: Spara den uppdaterade filen

Slutligen sparar vi den uppdaterade PDF-filen med namnet "DeleteAllAttachments_out.pdf" i den angivna katalogen.

```csharp
pdfDocument.Save(dataDir + "DeleteAllAttachments_out.pdf");
```

### Exempel på källkod för Ta bort alla bilagor med Aspose.PDF för .NET 

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Öppna dokumentet
Document pdfDocument = new Document(dataDir + "DeleteAllAttachments.pdf");
// Ta bort alla bilagor
pdfDocument.EmbeddedFiles.Delete();
dataDir = dataDir + "DeleteAllAttachments_out.pdf";
// Spara uppdaterad fil
pdfDocument.Save(dataDir);
Console.WriteLine("\nAll attachments deleted successfully.\nFile saved at " + dataDir);

```

## Slutsats

I den här handledningen har vi förklarat hur du tar bort alla bilagor från en PDF-fil med Aspose.PDF för .NET. Du kan nu använda denna kunskap för att rensa upp dina PDF-dokument genom att ta bort alla oönskade bilagor.
