---
title: Konvertera alla sidor till PNG
linktitle: Konvertera alla sidor till PNG
second_title: Aspose.PDF för .NET API Referens
description: Konvertera enkelt alla sidor i ett PDF-dokument till PNG-filer med Aspose.PDF för .NET.
type: docs
weight: 60
url: /sv/net/programming-with-images/convert-all-pages-to-png/
---

Den här guiden tar dig steg för steg hur du konverterar alla sidor i ett PDF-dokument till PNG-filer med Aspose.PDF för .NET. Se till att du redan har konfigurerat din miljö och följ stegen nedan:

## Steg 1: Definiera dokumentkatalogen

 Innan du börjar, se till att du ställer in rätt katalog för dokumenten. Byta ut`"YOUR DOCUMENT DIRECTORY"` i koden med sökvägen till katalogen där ditt PDF-dokument finns.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 2: Öppna dokumentet

 I det här steget kommer vi att öppna PDF-dokumentet med hjälp av`Document` klass av Aspose.PDF. Använd`Document` konstruktor och skicka sökvägen till PDF-dokumentet.

```csharp
Document pdfDocument = new Document(dataDir + "ConvertAllPagesToPNG.pdf");
```

## Steg 3: Konvertera varje sida till PNG

 I det här steget kommer vi att gå igenom varje sida i PDF-dokumentet och konvertera dem till individuella PNG-filer. Vi kommer att använda en`for`loop för att iterera genom alla sidor.

```csharp
for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
{
     //Skapa en ström för att spara PNG-bilden
     using (FileStream imageStream = new FileStream(dataDir + "image" + pageCount + "_out" + ".png", FileMode.Create))
     {
         // Skapa en PNG-enhet med de angivna attributen
         // Bredd, höjd, upplösning, kvalitet
         // Kvalitet [0-100], 100 är max
         Resolution resolution = new Resolution(300);
         PngDevice pngDevice = new PngDevice(resolution);
        
         // Konvertera en specifik sida och spara bilden i strömmen
         pngDevice.Process(pdfDocument.Pages[pageCount], imageStream);
        
         // Stäng strömmen
         imageStream.Close();
     }
}
```

### Exempel på källkod för Konvertera alla sidor till PNG med Aspose.PDF för .NET 
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Öppna dokumentet
Document pdfDocument = new Document(dataDir + "ConvertAllPagesToPNG.pdf");
for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
{
	using (FileStream imageStream = new FileStream(dataDir + "image" + pageCount + "_out" + ".png", FileMode.Create))
	{
		// Skapa PNG-enhet med specificerade attribut
		// Bredd, höjd, upplösning, kvalitet
		// Kvalitet [0-100], 100 är max
		// Skapa upplösningsobjekt
		Resolution resolution = new Resolution(300);
		PngDevice pngDevice = new PngDevice(resolution);
		// Konvertera en viss sida och spara bilden för att streama
		pngDevice.Process(pdfDocument.Pages[pageCount], imageStream);
		// Stäng strömmen
		imageStream.Close();
	}
}
System.Console.WriteLine("PDF pages are converted to PNG successfully!");
```

## Slutsats

Grattis! Du har framgångsrikt konverterat alla sidor i ett PDF-dokument till PNG-filer med Aspose.PDF för .NET. Enskilda PNG-filer sparas i den angivna katalogen. Du kan nu använda dessa PNG-filer i dina projekt eller applikationer.