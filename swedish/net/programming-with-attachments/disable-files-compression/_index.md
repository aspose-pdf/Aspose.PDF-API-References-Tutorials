---
title: Inaktivera filkomprimering
linktitle: Inaktivera filkomprimering
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du inaktiverar filkomprimering i en PDF-fil med Aspose.PDF för .NET. Steg-för-steg-guide för enkel hantering.
type: docs
weight: 30
url: /sv/net/programming-with-attachments/disable-files-compression/
---
den här handledningen går vi igenom följande C#-källkod steg för steg för att inaktivera filkomprimering i en PDF med Aspose.PDF för .NET.

Se till att du har installerat Aspose.PDF-biblioteket och ställt in din utvecklingsmiljö innan du börjar. Har även grundläggande kunskaper i C#-programmering.

### Steg 1: Installation av dokumentkatalog

I den medföljande källkoden måste du ange den katalog där PDF-filen finns som du vill inaktivera filkomprimering. Ändra variabeln "dataDir" till önskad katalog.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### Steg 2: Öppna det befintliga PDF-dokumentet

Vi öppnar det befintliga PDF-dokumentet med den angivna sökvägen.

```csharp
Document pdfDocument = new Document(dataDir + "GetAlltheAttachments.pdf");
```

### Steg 3: Konfigurera den nya filen för att lägga till som en bilaga

Vi konfigurerar den nya filen som vi vill lägga till som en bilaga. I det här exemplet lägger vi till en textfil med namnet "test_out.txt" och en beskrivning "Exempel på textfil".

```csharp
FileSpecification fileSpecification = new FileSpecification("test_out.txt", "Sample text file");
```

### Steg 4: Inaktivera filkomprimering

Vi inaktiverar filkomprimering genom att sätta egenskapen Encoding för FileSpecification-objektet till FileEncoding.None.

```csharp
fileSpecification.Encoding = FileEncoding.None;
```

### Steg 5: Lägga till bilagan till dokumentets samling av bilagor

Vi lägger till bilagan i dokumentets bilagasamling.

```csharp
pdfDocument.EmbeddedFiles.Add(fileSpecification);
```

### Steg 6: Spara den nya utdatafilen

Slutligen sparar vi den resulterande nya PDF-filen med namnet "DisableFilesCompression_out.pdf" i den angivna katalogen.

```csharp
pdfDocument.Save(dataDir + "DisableFilesCompression_out.pdf");
```


### Exempel på källkod för Inaktivera filkomprimering med Aspose.PDF för .NET 

```csharp

// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "GetAlltheAttachments.pdf");
// Konfigurera ny fil som ska läggas till som bilaga
FileSpecification fileSpecification = new FileSpecification("test_out.txt", "Sample text file");
// Ange Encoding proparty och ställ in den på FileEncoding.None
fileSpecification.Encoding = FileEncoding.None;
// Lägg till bilaga till dokumentets bilagasamling
pdfDocument.EmbeddedFiles.Add(fileSpecification);
dataDir = dataDir + "DisableFilesCompression_out.pdf";
// Spara ny utgång
pdfDocument.Save(dataDir);
Console.WriteLine("\nFile compression disabled successfully.\nFile saved at " + dataDir);

```

## Slutsats

I den här handledningen förklarade vi hur man inaktiverar filkomprimering i en PDF med Aspose.PDF för .NET. Du kan nu använda denna kunskap för att bibehålla integriteten för bifogade filer utan komprimering.