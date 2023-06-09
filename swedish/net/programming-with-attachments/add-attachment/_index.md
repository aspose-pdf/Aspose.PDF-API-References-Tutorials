---
title: Bifoga fil
linktitle: Bifoga fil
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du lägger till bilagor till dina PDF-filer med Aspose.PDF för .NET. Steg-för-steg-guide för enkel hantering.
type: docs
weight: 10
url: /sv/net/programming-with-attachments/add-attachment/
---

den här handledningen går vi igenom följande C#-källkod steg för steg för att lägga till en bilaga till en PDF-fil med Aspose.PDF för .NET.

Se till att du har installerat Aspose.PDF-biblioteket och ställt in din utvecklingsmiljö innan du börjar. Har även grundläggande kunskaper i C#-programmering.

### Steg 1: Installation av dokumentkatalog

I den medföljande källkoden måste du ange katalogen där PDF-filen som du vill lägga till bilagan finns. Ändra variabeln "dataDir" till önskad katalog.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### Steg 2: Öppna det befintliga PDF-dokumentet

Vi öppnar det befintliga PDF-dokumentet med den angivna sökvägen.

```csharp
Document pdfDocument = new Document(dataDir + "AddAttachment.pdf");
```

### Steg 3: Konfigurera den nya filen för att lägga till som en bilaga

Vi konfigurerar den nya filen som vi vill lägga till som en bilaga. I det här exemplet lägger vi till en textfil med namnet "test.txt" och en beskrivning "Exempeltextfil".

```csharp
FileSpecification fileSpecification = new FileSpecification(dataDir + "test.txt", "Sample text file");
```

### Steg 4: Lägga till bilagan i dokumentets samling av bilagor

Vi lägger till bilagan i dokumentets bilagasamling.

```csharp
pdfDocument.EmbeddedFiles.Add(fileSpecification);
```

### Steg 5: Spara den nya utdatafilen

Slutligen sparar vi den resulterande nya PDF-filen med namnet "AddAttachment_out.pdf" i den angivna katalogen.

```csharp
pdfDocument.Save(dataDir + "AddAttachment_out.pdf");
```

### Exempel på källkod för Lägg till bilaga med Aspose.PDF för .NET
 
```csharp

// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Öppna dokumentet
Document pdfDocument = new Document(dataDir + "AddAttachment.pdf");
// Konfigurera ny fil som ska läggas till som bilaga
FileSpecification fileSpecification = new FileSpecification(dataDir + "test.txt", "Sample text file");
// Lägg till bilaga till dokumentets bilagasamling
pdfDocument.EmbeddedFiles.Add(fileSpecification);
dataDir = dataDir + "AddAttachment_out.pdf";
// Spara ny utgång
pdfDocument.Save(dataDir);
Console.WriteLine("\nSample text file attached successfully.\nFile saved at " + dataDir);

```

## Slutsats

I den här handledningen förklarade vi hur man lägger till en bilaga till en PDF-fil med Aspose.PDF för .NET. Du kan nu använda denna kunskap för att lägga till ytterligare filer som bilagor till dina PDF-dokument.
