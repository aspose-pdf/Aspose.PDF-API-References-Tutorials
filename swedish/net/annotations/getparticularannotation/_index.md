---
title: Få särskild anteckning
linktitle: Få särskild anteckning
second_title: Aspose.PDF för .NET API-referens
description: Lär dig hur du använder Aspose.PDF för .NET för att få speciell anteckning i ett PDF-dokument med denna steg-för-steg-guide.
type: docs
weight: 80
url: /sv/net/annotations/getparticularannotation/
---
Om du arbetar med PDF-filer i .NET kan du stöta på ett behov av att få en viss anteckning från ett PDF-dokument. I den här guiden kommer vi att visa dig hur du använder Aspose.PDF för .NET för att få en viss anteckning från ett PDF-dokument med C#.

Följ dessa enkla steg för att få en viss anteckning från ett PDF-dokument:

## Steg 1: Få särskild anteckning från PDF-dokument

Se först till att du har Aspose.PDF för .NET-biblioteket installerat och refererat till i ditt projekt.

Skapa sedan en ny instans av klassen Document och ladda ditt PDF-dokument med hjälp av sökvägen till dokumentkatalogen.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document pdfDocument = new Document(dataDir + "GetParticularAnnotation.pdf");
```

## Steg 2: Du kan få en viss anteckning med följande kod:

```csharp
TextAnnotation textAnnotation = (TextAnnotation)pdfDocument.Pages[1].Annotations[1];
```

Den här koden hämtar den andra anteckningen på den andra sidan i PDF-dokumentet.

## Steg 3: Slutligen kan du få egenskaperna för annoteringen med hjälp av följande kod:

```csharp
Console.WriteLine("Title : {0} ", textAnnotation.Title);
Console.WriteLine("Subject : {0} ", textAnnotation.Subject);
Console.WriteLine("Contents : {0} ", textAnnotation.Contents);
```

Den här koden visar titeln, ämnet och innehållet för anteckningen i konsolen.


### Exempel på källkod för Get Particular Annotation med Aspose.PDF för .NET

```csharp

	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";

	// Öppna dokumentet
	Document pdfDocument = new Document(dataDir + "GetParticularAnnotation.pdf");

	// Få en speciell kommentar
	TextAnnotation textAnnotation = (TextAnnotation)pdfDocument.Pages[1].Annotations[1];

	// Få anteckningsegenskaper
	Console.WriteLine("Title : {0} ", textAnnotation.Title);
	Console.WriteLine("Subject : {0} ", textAnnotation.Subject);
	Console.WriteLine("Contents : {0} ", textAnnotation.Contents);

```

