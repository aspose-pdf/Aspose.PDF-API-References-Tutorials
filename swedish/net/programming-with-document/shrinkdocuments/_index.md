---
title: Krympa dokument
linktitle: Krympa dokument
second_title: Aspose.PDF för .NET API-referens
description: Lär dig hur du använder Aspose.PDF för .NET för att krympa PDF-dokument med denna steg-för-steg-guide.
type: docs
weight: 350
url: /sv/net/programming-with-document/shrinkdocuments/
---
Aspose.PDF för .NET är ett kraftfullt bibliotek som gör det möjligt för utvecklare att skapa, manipulera och optimera PDF-dokument med C#. I den här handledningen kommer vi att gå igenom ett exempel på hur man använder Aspose.PDF för att förminska ett PDF-dokument.

## Steg 1: Ladda PDF-dokumentet

 För att krympa ett PDF-dokument måste vi först ladda det i vår C#-applikation med Aspose.PDF. I koden nedan anger vi sökvägen till vårt PDF-dokument och skapar en ny instans av`Document` klass.

```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Öppna dokumentet
Document pdfDocument = new Document(dataDir + "ShrinkDocument.pdf");
```

## Steg 2: Krympa PDF-dokumentet

 När vi har laddat in PDF-dokumentet kan vi använda`OptimizeResources` metod för`Document`klass för att optimera dokumentet och eventuellt krympa dess storlek. Observera att den här metoden inte kan garantera att dokument krymper, eftersom vissa PDF-dokument redan kan vara mycket optimerade.

```csharp
// Optimera PDF-dokument. Observera dock att den här metoden inte kan garantera att dokument krymper
pdfDocument.OptimizeResources();
```

## Steg 3: Spara det uppdaterade PDF-dokumentet

 Efter att vi har optimerat PDF-dokumentet kan vi spara den uppdaterade versionen till en ny fil med hjälp av`Save` metod för`Document` klass. I koden nedan anger vi sökvägen och filnamnet för utdatafilen.

```csharp
// Ange sökväg för utdatafil
string outputFilePath = dataDir + "ShrinkDocument_out.pdf";
// Spara uppdaterat dokument
pdfDocument.Save(outputFilePath);
```

### Exempel på källkod för Shrink Documents med Aspose.PDF för .NET

```csharp

	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Öppna dokumentet
	Document pdfDocument = new Document(dataDir + "ShrinkDocument.pdf");
	// Optimera PDF-dokument. Observera dock att den här metoden inte kan garantera att dokument krymper
	pdfDocument.OptimizeResources();
	dataDir = dataDir + "ShrinkDocument_out.pdf";
	// Spara uppdaterat dokument
	pdfDocument.Save(dataDir);
	
```
