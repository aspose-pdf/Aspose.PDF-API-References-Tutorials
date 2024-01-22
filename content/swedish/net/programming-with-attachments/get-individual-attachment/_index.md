---
title: Få individuell bilaga i PDF-fil
linktitle: Få individuell bilaga i PDF-fil
second_title: Aspose.PDF för .NET API-referens
description: Lär dig hur du får en enskild bilaga i PDF-fil med Aspose.PDF för .NET.
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
//Kontrollera om parameterobjektet innehåller parametrarna
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

I den här handledningen förklarade vi hur man får en enskild bilaga från en PDF-fil med Aspose.PDF för .NET. Du kan nu använda denna kunskap för att extrahera och spara bilagor från dina PDF-filer.

### Vanliga frågor för att få individuell bilaga i PDF-fil

#### F: Vad är syftet med att få en enskild bilaga från ett PDF-dokument?

S: Genom att få en enskild bilaga kan du extrahera och spara en specifik inbäddad fil i en PDF, vilket kan vara användbart för ytterligare analys eller manipulation.

#### F: Hur kan jag dra nytta av den här handledningen i mina PDF-relaterade uppgifter?

S: Denna handledning innehåller steg-för-steg-instruktioner och C#-källkod för att hämta och spara en viss bilaga från ett PDF-dokument med Aspose.PDF för .NET.

#### F: Vilka bifogade egenskaper kan jag komma åt med den här handledningen?

S: Du kan komma åt bifogade egenskaper som namn, beskrivning, MIME-typ, kontrollhash, skapandedatum, ändringsdatum och storleken på den specifika bilagan.

#### F: Kan jag ändra koden för att få andra bilagor än den första bilagan?

 A: Absolut, du kan justera indexet (t.ex.`pdfDocument.EmbeddedFiles[1]`) för att hämta bilagor vid olika index i PDF:en.

#### F: Hur sparar jag den hämtade bilagan till en fil?

S: Denna handledning tillhandahåller kod för att hämta bilagans innehåll och spara den i en textfil med ett angivet namn.

#### F: Vilken betydelse har egenskapen "Check Hash" i bifogad information?

S: Egenskapen "Check Hash" representerar kontrollhashvärdet för bilagan, som kan användas för att verifiera bilagans integritet.

#### F: Kan jag utöka denna kunskap till att extrahera bilagor med specifika kriterier, till exempel filtyp?

S: Ja, du kan förbättra koden för att filtrera bilagor baserat på specifika kriterier som filtyp eller andra egenskaper.

#### F: Hur förenklar Aspose.PDF för .NET processen att extrahera enskilda bilagor?

S: Aspose.PDF för .NET tillhandahåller ett användarvänligt API som underlättar extrahering och manipulering av bilagor i PDF-dokument.

#### F: Är denna handledning relevant för lösenordsskyddade PDF-filer också?

S: Ja, du kan anpassa liknande tekniker för att hämta enskilda bilagor från lösenordsskyddade PDF-filer med Aspose.PDF för .NET.
