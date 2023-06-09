---
title: Skaffa barnbokmärken
linktitle: Skaffa barnbokmärken
second_title: Aspose.PDF för .NET API Referens
description: Få enkelt barnbokmärken för dina PDF-filer med Aspose.PDF för .NET.
type: docs
weight: 80
url: /sv/net/programming-with-bookmarks/get-child-bookmarks/
---

Att hämta underordnade bokmärken från ett PDF-dokument kan vara användbart för att utforska bokmärkens hierarkiska struktur. Med Aspose.PDF för .NET kan du enkelt få de underordnade bokmärkena genom att följa följande källkod:

## Steg 1: Importera nödvändiga bibliotek

Innan du börjar måste du importera de nödvändiga biblioteken för ditt C#-projekt. Här är det nödvändiga importdirektivet:

```csharp
using Aspose.Pdf;
```

## Steg 2: Ange sökväg till dokumentmappen

 I det här steget måste du ange sökvägen till mappen som innehåller PDF-filen du vill extrahera bokmärkena från. Byta ut`"YOUR DOCUMENT DIRECTORY"` i följande kod med den faktiska sökvägen till din dokumentmapp:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 3: Öppna PDF-dokumentet

Nu ska vi öppna PDF-dokumentet från vilket vi vill extrahera bokmärkena med hjälp av följande kod:

```csharp
Document pdfDocument = new Document(dataDir + "GetChildBookmarks.pdf");
```

## Steg 4: Bläddra bland bokmärken och barnbokmärken

 det här steget kommer vi att iterera över alla bokmärken i dokumentet med hjälp av en`foreach`slinga. För varje bokmärke kommer vi att visa information som titel, kursiv stil, fet stil och färg. Om bokmärket har underordnade bokmärken visar vi dessa också. Här är motsvarande kod:

```csharp
foreach(OutlineItemCollection outlineItem in pdfDocument.Outlines)
{
     Console.WriteLine(outlineItem.Title);
     Console.WriteLine(outlineItem.Italic);
     Console.WriteLine(outlineItem.Bold);
     Console.WriteLine(outlineItem.Color);
    
     if (outlineItem.Count > 0)
     {
         Console.WriteLine("Child bookmarks");
        
         // Bläddra bland barnbokmärken också
         foreach(OutlineItemCollection childOutline in outlineItem)
         {
             Console.WriteLine(childOutline.Title);
             Console.WriteLine(childOutline.Italic);
             Console.WriteLine(childOutline.Bold);
             Console.WriteLine(childOutline.Color);
         }
     }
}
```

### Exempel på källkod för Get Child Bookmarks med Aspose.PDF för .NET 
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Öppna dokumentet
Document pdfDocument = new Document(dataDir + "GetChildBookmarks.pdf");
// Gå igenom alla bokmärken
foreach (OutlineItemCollection outlineItem in pdfDocument.Outlines)
{
	Console.WriteLine(outlineItem.Title);
	Console.WriteLine(outlineItem.Italic);
	Console.WriteLine(outlineItem.Bold);
	Console.WriteLine(outlineItem.Color);
	if (outlineItem.Count > 0)
	{
		Console.WriteLine("Child Bookmarks");
		// Det finns underordnade bokmärken och sedan gå igenom det också
		foreach (OutlineItemCollection childOutline in outlineItem)
		{
			Console.WriteLine(childOutline.Title);
			Console.WriteLine(childOutline.Italic);
			Console.WriteLine(childOutline.Bold);
			Console.WriteLine(childOutline.Color);
		}
	}
}
```

## Slutsats

Grattis! Nu har du en steg-för-steg-guide för att få barnbokmärken med Aspose.PDF för .NET. Du kan använda den här koden för att utforska bokmärkens hierarkiska struktur och få detaljerad information om varje bokmärke och dess underordnade bokmärken i dina PDF-dokument.

Se till att kolla in den officiella Aspose.PDF-dokumentationen för mer information om avancerade bokmärkesmanipuleringsfunktioner.