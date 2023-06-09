---
title: Konvertera till BMP
linktitle: Konvertera till BMP
second_title: Aspose.PDF för .NET API Referens
description: Konvertera enkelt PDF till individuella BMP-bilder med Aspose.PDF för .NET.
type: docs
weight: 90
url: /sv/net/programming-with-images/convert-to-bmp/
---

Den här guiden tar dig steg för steg hur du konverterar en PDF-fil till individuella BMP-bilder med Aspose.PDF för .NET. Se till att du redan har konfigurerat din miljö och följ stegen nedan:

## Steg 1: Definiera dokumentkatalogen

 Innan du börjar, se till att du ställer in rätt katalog för dokumenten. Byta ut`"YOUR DOCUMENT DIRECTORY"` i koden med sökvägen till katalogen där ditt PDF-dokument finns.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 2: Öppna dokumentet

 I det här steget kommer vi att öppna PDF-dokumentet med hjälp av`Document` klass av Aspose.PDF. Använd`Document` konstruktor och skicka sökvägen till PDF-dokumentet.

```csharp
Document pdfDocument = new Document(dataDir + "AddImage.pdf");
```

## Steg 3: Konvertera varje sida till BMP

 I det här steget går vi igenom varje sida i PDF-dokumentet och konverterar dem till individuella BMP-bilder. Vi kommer att använda en`for`loop för att iterera genom alla sidor.

```csharp
for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
{
     // Skapa en ström för att spara BMP-bilden
     using (FileStream imageStream = new FileStream("image" + pageCount + "_out" + ".bmp", FileMode.Create))
     {
         // Skapa ett Resolution-objekt
         Resolution resolution = new Resolution(300);
        
         // Skapa en BMP-enhet med de angivna attributen
         //Bredd, höjd, upplösning, sidstorlek
         BmpDevice bmpDevice = new BmpDevice(resolution);
        
         // Konvertera en specifik sida och spara bilden i strömmen
         bmpDevice.Process(pdfDocument.Pages[pageCount], imageStream);
        
         // Stäng strömmen
         imageStream.Close();
     }
}
```

### Exempel på källkod för Konvertera till BMP med Aspose.PDF för .NET 
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Öppna dokumentet
Document pdfDocument = new Document(dataDir + "AddImage.pdf");
for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
{
	using (FileStream imageStream = new FileStream("image" + pageCount + "_out" + ".bmp", FileMode.Create))
	{
		// Skapa upplösningsobjekt
		Resolution resolution = new Resolution(300);
		// Skapa BMP-enhet med specificerade attribut
		// Bredd, höjd, upplösning, sidstorlek
		BmpDevice bmpDevice = new BmpDevice(resolution);
		// Konvertera en viss sida och spara bilden för att streama
		bmpDevice.Process(pdfDocument.Pages[pageCount], imageStream);
		// Stäng strömmen
		imageStream.Close();
	}
} 
Console.WriteLine("\nPDF file converted to bmp successfully!"); 
```

## Slutsats

Grattis! Du har framgångsrikt konverterat en PDF-fil till enskilda BMP-bilder med Aspose.PDF för .NET. BMP-bilder sparas i den angivna katalogen. Du kan nu använda dessa bilder i dina projekt eller applikationer.