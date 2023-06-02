---
title: Validera PDF UA Standard
linktitle: Validera PDF UA Standard
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du använder Aspose.PDF för .NET för att validera PDF/UA-standard med C#-kod. Steg-för-steg guide.
type: docs
weight: 400
url: /sv/net/programming-with-document/validatepdfuastandard/
---
Aspose.PDF för .NET är ett kraftfullt bibliotek som tillhandahåller olika funktioner för att arbeta med PDF-dokument. En av dess funktioner är möjligheten att validera PDF-dokument för PDF/UA-standardefterlevnad. I den här artikeln kommer vi att ge steg-för-steg-vägledning om hur man använder Aspose.PDF för .NET för att få och validera PDF/UA-standardefterlevnad med C#-kod.

## Steg 1: Definiera sökvägen till dokumentkatalogen

Därefter måste vi definiera sökvägen till katalogen där vårt PDF-dokument finns. Du kan göra detta genom att lägga till följande kodavsnitt:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

Ersätt "DIN DOKUMENTKATOLOG" med den faktiska sökvägen till din PDF-dokumentkatalog.

## Steg 2: Öppna PDF-dokumentet

Efter att ha definierat sökvägen till dokumentkatalogen kan vi öppna vårt PDF-dokument med följande kod:

```csharp
Document pdfDocument = new Document(dataDir + "ValidatePDFUAStandard.pdf");
```

 Denna kod skapar en ny`Document` objekt från vår PDF-fil som finns i den angivna katalogen.

## Steg 3: Validera PDF-filen för PDF/UA

Nu när vi har öppnat PDF-dokumentet kan vi använda Aspose.PDF för .NET för att validera dokumentet för PDF/UA-efterlevnad. Följande kodsnutt kommer att göra jobbet:

```csharp
bool isValidPdfUa = pdfDocument.Validate(dataDir + "validation-result-UA.xml", PdfFormat.PDF_UA_1);
```

Denna kod validerar PDF-dokumentet för PDF/UA-standardefterlevnad och genererar en valideringsrapport i den angivna XML-filen. Valideringsresultatet lagras i`isValidPdfUa` variabel, som är av boolesk datatyp.

### Exempel på källkod för Get Validate PDFUAstandard med Aspose.PDF för .NET

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";

// Öppna dokumentet
Document pdfDocument = new Document(dataDir + "ValidatePDFUAStandard.pdf");

// Validera PDF för PDF/UA
bool isValidPdfUa = pdfDocument.Validate(dataDir + "validation-result-UA.xml", PdfFormat.PDF_UA_1); 
```
