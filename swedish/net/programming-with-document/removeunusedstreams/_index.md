---
title: Ta bort oanvända strömmar
linktitle: Ta bort oanvända strömmar
second_title: Aspose.PDF för .NET API-referens
description: Lär dig hur du tar bort oanvända strömmar från PDF-filer med Aspose.PDF för .NET. Vår steg-för-steg guide.
type: docs
weight: 270
url: /sv/net/programming-with-document/removeunusedstreams/
---
I det här exemplet kommer vi att diskutera hur man tar bort oanvända strömmar från PDF-dokument med Aspose.PDF för .NET. Vi kommer att tillhandahålla en steg-för-steg-guide om hur du gör detta, inklusive hela källkoden med förklaringar.

## Steg 1: Sökvägen till dokumentkatalogen

Den första raden i koden anger sökvägen till katalogen där ditt PDF-dokument finns. Se till att ersätta "DIN DOKUMENTKATOGRAF" med den faktiska katalogsökvägen.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 2: Öppna dokumentet

Nästa kodrad öppnar PDF-dokumentet med Aspose.PDF för .NET-biblioteket.

```csharp
Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
```

## Steg 3: Ställ in alternativet RemoveUnusedStreams

Nästa steg är att ställa in alternativet RemoveUnusedStreams till sant. Detta tar bort alla oanvända strömmar från PDF-dokumentet.

```csharp
var optimizeOptions = new Pdf.Optimization.OptimizationOptions
{
	RemoveUnusedStreams = true
};
```

## Steg 4: Optimera PDF-dokument med OptimizationOptions

Nu när vi har ställt in optimeringsalternativen kan vi optimera PDF-dokumentet med hjälp av följande kodrad.

```csharp
pdfDocument.OptimizeResources(optimizeOptions);
```

## Steg 5: Spara uppdaterat dokument

Slutligen kan vi spara det uppdaterade dokumentet med hjälp av Spara-metoden i klassen Document.

```csharp
dataDir = dataDir + "OptimizeDocument_out.pdf";
pdfDocument.Save(dataDir);
```

### Exempel på källkod för Ta bort oanvända strömmar med Aspose.PDF för .NET

Nedan är exempel på källkoden för att ta bort oanvända strömmar med Aspose.PDF för .NET.

```csharp

	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Öppna dokumentet
	Document pdfDocument = new Document(dataDir + "OptimizeDocument.pdf");
	// Ställ in alternativet RemoveUsedStreams
	var optimizeOptions = new Pdf.Optimization.OptimizationOptions
	{
		RemoveUnusedStreams = true
	};
	// Optimera PDF-dokument med OptimizationOptions
	pdfDocument.OptimizeResources(optimizeOptions);
	dataDir = dataDir + "OptimizeDocument_out.pdf";
	// Spara uppdaterat dokument
	pdfDocument.Save(dataDir);

```
