---
title: Få individuell bilaga
linktitle: Få individuell bilaga
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du får en enskild bilaga i en PDF-fil med Aspose.PDF för .NET.
type: docs
weight: 60
url: /sv/net/programming-with-attachments/get-individual-attachment/
---
I den här handledningen går vi igenom följande C#-källkod steg för steg för att få en individuell bifogad PDF-fil med Aspose.PDF för .NET.

Se till att du har installerat Aspose.PDF-biblioteket och ställt in din utvecklingsmiljö innan du börjar. Har även grundläggande kunskaper i C#-programmering.

### Steg 1: Installation av dokumentkatalog

I den medföljande källkoden måste du ange den katalog där PDF-filen finns från vilken du vill hämta den enskilda bilagan. Ändra variabeln "dataDir" till önskad katalog.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### Steg 2: Öppna det befintliga PDF-dokumentet

Vi öppnar det befintliga PDF-dokumentet med den angivna sökvägen.

```csharp
Document pdfDocument = new Document(dataDir + "GetIndividualAttachment.pdf");
```

### Steg 3: Skaffa en specifik bilaga

Vi hämtar en specifik bilaga från dokumentets bilagasamling. I det här exemplet får vi den första bilagan med hjälp av index 1.

```csharp
FileSpecification fileSpecification = pdfDocument.EmbeddedFiles[1];
```

### Steg 4: Hämta filegenskaper

Vi visar bifogade egenskaper som namn, beskrivning, MIME-typ, kontrollhash, datum skapat, ändringsdatum och storlek.

```csharp
Console.WriteLine("Name: {0}", fileSpecification.Name);
Console.WriteLine("Description: {0}", fileSpecification.Description);
Console.WriteLine("MIME Type: {0}", fileSpecification.MIMEType);

// Kontrollera om objektparametrar innehåller ytterligare information
if (fileSpecification.Params != null)
{
Console.WriteLine("Check Hash: {0}", fileSpecification.Params.CheckSum);
Console.WriteLine("Creation date: {0}", fileSpecification.Params.CreationDate);
Console.WriteLine("Modified date: {0}", fileSpecification.Params.ModDate);
Console.WriteLine("Size: {0}", fileSpecification.Params.Size);
}
```

### Steg 5: Hämta bilaga och spara till fil

Vi hämtar innehållet i bilagan och sparar den i en textfil. I det här exemplet sparas filen med namnet "test_out.txt".

```csharp
byte[] fileContent = new byte[fileSpecification.Contents.Length];
fileSpecification.Contents.Read(fileContent, 0, fileContent.Length);
FileStream fileStream = new FileStream(dataDir + "test_out" + ".txt", FileMode.Create);
fileStream.Write(fileContent, 0, fileContent.Length);
fileStream.Close();
```

### Exempel på källkod för Get Individual Attachment med Aspose.PDF för .NET 

```csharp

// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Öppna dokumentet
Document pdfDocument = new Document(dataDir + "GetIndividualAttachment.pdf");
// Skaffa en speciell inbäddad fil
FileSpecification fileSpecification = pdfDocument.EmbeddedFiles[1];
// Hämta filegenskaperna
Console.WriteLine("Name: {0}", fileSpecification.Name);
Console.WriteLine("Description: {0}", fileSpecification.Description);
Console.WriteLine("Mime Type: {0}", fileSpecification.MIMEType);
// Kontrollera om parameterobjektet innehåller parametrarna
if (fileSpecification.Params != null)
{
	Console.WriteLine("CheckSum: {0}",
	fileSpecification.Params.CheckSum);
	Console.WriteLine("Creation Date: {0}",
	fileSpecification.Params.CreationDate);
	Console.WriteLine("Modification Date: {0}",
	fileSpecification.Params.ModDate);
	Console.WriteLine("Size: {0}", fileSpecification.Params.Size);
}
// Hämta bilagan och skriv till fil eller stream
byte[] fileContent = new byte[fileSpecification.Contents.Length];
fileSpecification.Contents.Read(fileContent, 0, fileContent.Length);
FileStream fileStream = new FileStream(dataDir + "test_out" + ".txt", FileMode.Create);
fileStream.Write(fileContent, 0, fileContent.Length);
fileStream.Close();

```

## Slutsats

den här handledningen förklarade vi hur man får en enskild bilaga från en PDF-fil med Aspose.PDF för .NET. Du kan nu använda denna kunskap för att extrahera och spara bilagor från dina PDF-filer.
