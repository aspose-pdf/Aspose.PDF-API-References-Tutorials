---
title: Länka dubbletter av strömmar
linktitle: Länka dubbletter av strömmar
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du använder funktionen Aspose.PDF för .NET Link Duplicate Streams för att optimera dina PDF-dokument med denna steg-för-steg-guide.
type: docs
weight: 230
url: /sv/net/programming-with-document/linkduplicatestreams/
---
Aspose.PDF för .NET är ett omfattande och kraftfullt bibliotek som tillhandahåller en mängd olika funktioner för att arbeta med PDF-filer. En av dess nyckelfunktioner är möjligheten att optimera PDF-filer. I den här artikeln kommer vi att förklara hur du använder funktionen Link Duplicate Streams i Aspose.PDF för .NET för att optimera PDF-filer. Vi kommer att tillhandahålla steg-för-steg-instruktioner och inkludera ett komplett källkodsexempel för att göra det enkelt för utvecklare att följa med.

## Steg 1: Öppna PDF-dokumentet

För att öppna PDF-dokumentet med Aspose.PDF för .NET, följ dessa steg:

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Öppna dokumentet
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

I koden ovan, ersätt "DIN DOKUMENTKATOLOG" med sökvägen till din projektkatalog.

## Steg 2: Ställa in alternativet LinkDuplicateStreams

Följ dessa steg för att ställa in alternativet LinkDuplicateStreams:

```csharp
// Ställ in alternativet LinkDuplcateStreams
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
    LinkDuplcateStreams = true
};
```

I koden ovan skapade vi en ny instans av OptimizationOptions och satte alternativet LinkDuplicateStreams till sant.

## Steg 3: Optimera PDF-dokumentet

För att optimera PDF-dokumentet, följ dessa steg:

```csharp
// Optimera PDF-dokument med OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
```

I koden ovan använde vi OptimizeResources-metoden för pdfDocument-objektet för att optimera PDF-dokumentet med hjälp av OptimizationOptions vi skapade tidigare.

## Steg 4: Spara det uppdaterade dokumentet

För att spara det uppdaterade dokumentet, följ dessa steg:

```csharp
dataDir = dataDir + "OptimizeDocument_out.pdf";
// Spara uppdaterat dokument
pdfDocument.Save(dataDir);
```

I koden ovan använde vi Save-metoden för pdfDocument-objektet för att spara det uppdaterade dokumentet till en ny fil med namnet "OptimizeDocument_out.pdf" i projektkatalogen.

### Exempel på källkod för länkduplikatströmmar med Aspose.PDF för .NET

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Öppna dokumentet
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
// Ställ in alternativet LinkDuplcateStreams
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	LinkDuplcateStreams = true
};
// Optimera PDF-dokument med OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
dataDir = dataDir + "OptimizeDocument_out.pdf";
// Spara uppdaterat dokument
pdfDocument.Save(dataDir);
```
