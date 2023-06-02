---
title: Ta bort oanvända objekt
linktitle: Ta bort oanvända objekt
second_title: Aspose.PDF för .NET API Referens
description: Lär dig hur du använder Aspose.PDF för .NET för att ta bort oanvända objekt från PDF-dokument med denna steg-för-steg-guide.
type: docs
weight: 260
url: /sv/net/programming-with-document/removeunusedobjects/
---
Om du letar efter ett sätt att ta bort oanvända objekt i dina PDF-dokument med Aspose.PDF för .NET, har du kommit rätt. Denna steg-för-steg-guide visar dig hur du använder C#-källkoden som tillhandahålls för att utföra denna uppgift.

## Steg 1: Ställ in katalogsökvägen

Först måste du ställa in sökvägen till din dokumentkatalog genom att ersätta "DIN DOKUMENTKATOGRAF" med lämplig sökväg.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 2: Öppna PDF-dokumentet

Därefter måste du öppna PDF-dokumentet som du vill optimera genom att använda följande kod:

```csharp
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## Steg 3: Ställ in alternativet RemoveUnusedObjects

För att ta bort oanvända objekt i ditt PDF-dokument måste du ställa in alternativet RemoveUnusedObjects till "true" enligt följande:

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	RemoveUnusedObjects = true
};
```

## Steg 4: Optimera PDF-dokument med OptimizationOptions

Nu kan du optimera ditt PDF-dokument genom att använda OptimizeResources-metoden med de optimeringsalternativ du just ställt in:

```csharp
pdfDocument.OptimizeResources(optimizeOptions);
```

## Steg 5: Spara det uppdaterade dokumentet

Slutligen kan du spara det uppdaterade dokumentet med följande kod:

```csharp
dataDir = dataDir + "OptimizeDocument_out.pdf";
pdfDocument.Save(dataDir);
```

Det är allt! Du har framgångsrikt tagit bort oanvända objekt från ditt PDF-dokument med Aspose.PDF för .NET.

### Exempel på källkod för Ta bort oanvända objekt med Aspose.PDF för .NET:

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Öppna dokumentet
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
// Ställ in alternativet RemoveUsedObject
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	RemoveUnusedObjects = true
};
// Optimera PDF-dokument med OptimizationOptions
pdfDocument.OptimizeResources(optimizeOptions);
dataDir = dataDir + "OptimizeDocument_out.pdf";
// Spara uppdaterat dokument
pdfDocument.Save(dataDir);
```
