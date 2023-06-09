---
title: Få alla bilagor
linktitle: Få alla bilagor
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du hämtar alla bilagor från en PDF-fil med Aspose.PDF för .NET. Steg-för-steg-guide för enkel hantering.
type: docs
weight: 40
url: /sv/net/programming-with-attachments/get-all-the-attachments/
---
I den här handledningen går vi igenom följande C#-källkod steg för steg för att få alla bilagor från en PDF-fil med Aspose.PDF för .NET.

Se till att du har installerat Aspose.PDF-biblioteket och ställt in din utvecklingsmiljö innan du börjar. Har även grundläggande kunskaper i C#-programmering.

### Steg 1: Installation av dokumentkatalog

I den medföljande källkoden måste du ange katalogen där PDF-filen finns från vilken du vill hämta bilagorna. Ändra variabeln "dataDir" till önskad katalog.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

### Steg 2: Öppna det befintliga PDF-dokumentet

Vi öppnar det befintliga PDF-dokumentet med den angivna sökvägen.

```csharp
Document pdfDocument = new Document(dataDir + "GetAlltheAttachments.pdf");
```

### Steg 3: Skaffa bilagasamlingen

Vi hämtar insamlingen av bilagor från dokumentet.

```csharp
EmbeddedFileCollection embeddedFiles = pdfDocument.EmbeddedFiles;
```

### Steg 4: Hämta bilagor

Vi går igenom samlingen för att få alla bilagor och visa deras information. Vi sparar även bilagor i enskilda filer.

```csharp
int count = 1;
foreach(FileSpecification fileSpecification in embeddedFiles)
{
Console.WriteLine("Name: {0}", fileSpecification.Name);
Console.WriteLine("Description: {0}", fileSpecification.Description);
Console.WriteLine("MIME Type: {0}", fileSpecification.MIMEType);

// Kontrollera om objektparametrar innehåller ytterligare information
if (fileSpecification.Params != null)
{
Console.WriteLine("CheckSum: {0}", fileSpecification.Params.CheckSum);
Console.WriteLine("Creation date: {0}", fileSpecification.Params.CreationDate);
Console.WriteLine("Modified date: {0}", fileSpecification.Params.ModDate);
Console.WriteLine("Size: {0}", fileSpecification.Params.Size);
}

// Hämta bilagan och spara i en fil
byte[] fileContent = new byte[fileSpecification.Contents.Length];
fileSpecification.Contents.Read(fileContent, 0, fileContent.Length);
FileStream fileStream = new FileStream(dataDir + count + "_out" + ".txt", FileMode.Create);
fileStream.Write(fileContent, 0, fileContent.Length);
fileStream.Close();

count += 1;
}
```


### Exempel på källkod för Get Allthe Attachments med Aspose.PDF för .NET 

```csharp

// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Öppna dokumentet
Document pdfDocument = new Document(dataDir + "GetAlltheAttachments.pdf");
// Få inbäddade filer samling
EmbeddedFileCollection embeddedFiles = pdfDocument.EmbeddedFiles;
// Få räkning av de inbäddade filerna
Console.WriteLine("Total files : {0}", embeddedFiles.Count);
int count = 1;
// Gå igenom samlingen för att få alla bilagor
foreach (FileSpecification fileSpecification in embeddedFiles)
{
	Console.WriteLine("Name: {0}", fileSpecification.Name);
	Console.WriteLine("Description: {0}",
	fileSpecification.Description);
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
	fileSpecification.Contents.Read(fileContent, 0,
	fileContent.Length);
	FileStream fileStream = new FileStream(dataDir + count + "_out" + ".txt",
	FileMode.Create);
	fileStream.Write(fileContent, 0, fileContent.Length);
	fileStream.Close();
	count+=1;
}

```

## Slutsats

I den här handledningen förklarade vi hur man hämtar alla bilagor från en PDF-fil med Aspose.PDF för .NET. Du kan nu använda denna kunskap för att extrahera och manipulera bilagor från dina PDF-filer.