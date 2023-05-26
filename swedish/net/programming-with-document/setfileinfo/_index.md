---
title: Ställ in filinformation
linktitle: Ställ in filinformation
second_title: Aspose.PDF för .NET API-referens
description: Lär dig hur du använder Aspose.PDF för .NET för att ställa in filinformation i dina PDF-dokument med denna steg-för-steg-guide.
type: docs
weight: 310
url: /sv/net/programming-with-document/setfileinfo/
---
Om du arbetar med ett projekt som kräver hantering av PDF-filer med Aspose.PDF för .NET, är en av funktionerna du kanske vill använda möjligheten att ställa in filinformation för ett PDF-dokument. Filinformationen innehåller olika detaljer som författare, datum för skapande, nyckelord, ändringsdatum, ämne och titel. Den här guiden leder dig genom processen att ställa in filinformation för ett PDF-dokument med C#-källkod med Aspose.PDF för .NET.

## Steg-för-steg-guide för att ställa in filinformation med Aspose.PDF för .NET

1. Skapa ett nytt C#-projekt i din Visual Studio IDE.
2. Lägg till en referens till Aspose.PDF för .NET-biblioteket i ditt projekt.
3. Skapa ett nytt PDF-dokument genom att ange sökvägen till PDF-filen som du vill ändra filinformationen för.

## Steg 1: Ange sökväg till dokumentkatalogen.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 2: Öppna PDF-dokumentet

```csharp
// Öppna dokumentet
Document pdfDocument = new Document(dataDir + "SetFileInfo.pdf");
```

## Steg 3: Använd DocumentInfo-objektet för att komma åt filinformationen för PDF-dokumentet.

```csharp
DocumentInfo docInfo = new DocumentInfo(pdfDocument);
```

## Steg 4: Ställ in önskade filinformationsvärden med hjälp av egenskaperna för DocumentInfo-objektet.

```csharp
docInfo.Author = "Aspose";
docInfo.CreationDate = DateTime.Now;
docInfo.Keywords = "Aspose.Pdf, DOM, API";
docInfo.ModDate = DateTime.Now;
docInfo.Subject = "PDF Information";
docInfo.Title = "Setting PDF Document Information";
```

## Steg 5: Spara det uppdaterade PDF-dokumentet på den angivna platsen.

```csharp
dataDir = dataDir + "SetFileInfo_out.pdf";
pdfDocument.Save(dataDir);
```

## Steg 6: Kontrollera att filinformationen har uppdaterats.

```csharp
Console.WriteLine("\nFile informations setup successfully.\nFile saved at " + dataDir);
```

Du har framgångsrikt angett filinformation för ett PDF-dokument med Aspose.PDF för .NET.

## Slutsats

Sammanfattningsvis erbjuder Aspose.PDF för .NET ett enkelt och effektivt sätt att ställa in filinformation för PDF-dokument. Genom att följa de ovan nämnda stegen kan du enkelt ställa in önskade filinformationsvärden för dina PDF-dokument med hjälp av C#-källkoden.

### Exempel på källkod för Set File Info med Aspose.PDF för .NET


```csharp

	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	// Öppna dokumentet
	Document pdfDocument = new Document(dataDir + "SetFileInfo.pdf");

	// Ange dokumentinformation
	DocumentInfo docInfo = new DocumentInfo(pdfDocument);

	docInfo.Author = "Aspose";
	docInfo.CreationDate = DateTime.Now;
	docInfo.Keywords = "Aspose.Pdf, DOM, API";
	docInfo.ModDate = DateTime.Now;
	docInfo.Subject = "PDF Information";
	docInfo.Title = "Setting PDF Document Information";

	dataDir = dataDir + "SetFileInfo_out.pdf";
	// Spara utdatadokument
	pdfDocument.Save(dataDir);
	
	Console.WriteLine("\nFile informations setup successfully.\nFile saved at " + dataDir);
	
```
