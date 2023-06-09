---
title: Skapa miniatyrbilder
linktitle: Skapa miniatyrbilder
second_title: Aspose.PDF för .NET API Referens
description: Skapa enkelt bildminiatyrer från PDF-filer med Aspose.PDF för .NET.
type: docs
weight: 100
url: /sv/net/programming-with-images/create-thumbnail-images/
---

Den här guiden tar dig steg för steg hur du skapar miniatyrbilder från PDF-filer med Aspose.PDF för .NET. Se till att du redan har konfigurerat din miljö och följ stegen nedan:

## Steg 1: Definiera dokumentkatalogen

 Innan du börjar, se till att du ställer in rätt katalog för dokumenten. Byta ut`"YOUR DOCUMENT DIRECTORY"` i koden med sökvägen till katalogen som innehåller dina PDF-filer.

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 2: Hämta namnen på alla PDF-filer i en katalog

 I det här steget kommer vi att hämta namnen på alla PDF-filer som finns i den angivna katalogen med hjälp av C#`Directory`klass. Filer kommer att lagras i en rad strängar.

```csharp
string[] fileEntries = Directory.GetFiles(dataDir, "*.pdf");
```

## Steg 3: Bläddra igenom alla PDF-filer och deras sidor

 I det här steget kommer vi att gå igenom alla PDF-filer och deras sidor för att skapa miniatyrbilder. Vi kommer att använda en`for` loop för att iterera igenom alla filer.

```csharp
for (int counter = 0; counter < fileEntries.Length; counter++)
{
     // Öppna PDF-dokumentet
     Document pdfDocument = new Document(fileEntries[counter]);
    
     // Gå igenom alla sidor i dokumentet
     for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
     {
         // Skapa en stream för att spara miniatyrbilden
         using (FileStream imageStream = new FileStream(dataDir + "\\Thumbnails" + counter.ToString() + "_" + pageCount + ".jpg", FileMode.Create))
         {
             // Skapa ett Resolution-objekt
             Resolution resolution = new Resolution(300);
            
             // Skapa en JPEG-enhet med de angivna attributen
             JpegDevice jpegDevice = new JpegDevice(45, 59, resolution, 100);
            
             // Konvertera en specifik sida och spara bilden i strömmen
             jpegDevice.Process(pdfDocument.Pages[pageCount], imageStream);
            
             // Stäng strömmen
             imageStream.Close();
         }
     }
}
```

### Exempel på källkod för Skapa miniatyrbilder med Aspose.PDF för .NET 
```csharp
// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
// Hämta namn på alla PDF-filer i en viss katalog
string[] fileEntries = Directory.GetFiles(dataDir, "*.pdf");
// Iterera igenom alla filposter i arrayen
for (int counter = 0; counter < fileEntries.Length; counter++)
{
	//Öppna dokumentet
	Document pdfDocument = new Document(fileEntries[counter]);
	for (int pageCount = 1; pageCount <= pdfDocument.Pages.Count; pageCount++)
	{
		using (FileStream imageStream = new FileStream(dataDir + "\\Thumbanils" + counter.ToString() + "_" + pageCount + ".jpg", FileMode.Create))
		{
			//Skapa upplösningsobjekt
			Resolution resolution = new Resolution(300);
			//JpegDevice jpegDevice = new JpegDevice(500, 700, upplösning, 100);
			JpegDevice jpegDevice = new JpegDevice(45, 59, resolution, 100);
			//Konvertera en viss sida och spara bilden för att streama
			jpegDevice.Process(pdfDocument.Pages[pageCount], imageStream);
			//Stäng strömmen
			imageStream.Close();
		}
	}
}
System.Console.WriteLine("PDF pages are converted to thumbnails successfully!");
```

## Slutsats

Grattis! Du har skapat miniatyrbilder från PDF-filer med Aspose.PDF för .NET. Bildminiatyrer sparas i den angivna katalogen. Du kan nu använda dessa miniatyrer för att visa en visuell förhandsvisning av dina PDF-filer.