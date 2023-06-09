---
title: Ändra orientering
linktitle: Ändra orientering
second_title: Aspose.PDF för .NET API Referens
description: Steg-för-steg-guide för att ändra sidorientering för en PDF med Aspose.PDF för .NET. Lätt att följa och implementera i dina projekt.
type: docs
weight: 10
url: /sv/net/programming-with-pdf-pages/change-orientation/
---
I den här handledningen går vi igenom steg-för-steg-processen för att ändra sidriktningen för ett PDF-dokument med Aspose.PDF för .NET. Vi kommer att förklara den medföljande C#-källkoden och förse dig med en omfattande guide som hjälper dig att förstå och implementera den här funktionen i dina egna projekt. I slutet av denna handledning kommer du att veta hur du ändrar sidriktningen för dina PDF-dokument med Aspose.PDF för .NET.

## Förutsättningar
Innan du börjar, se till att du har följande:

- Grundläggande kunskaper i programmeringsspråket C#
- Aspose.PDF för .NET installerat i din utvecklingsmiljö

## Steg 1: Definiera dokumentkatalogen
Först måste du ställa in sökvägen till din dokumentkatalog. Det här är platsen där din indata-PDF-fil finns och där du vill spara din modifierade PDF-fil. Ersätt "DIN DOKUMENTKATOLOG" med lämplig sökväg.

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Steg 2: Ladda PDF-dokumentet
 Sedan kan du ladda PDF-dokumentet från inmatningsfilen med hjälp av`Document` klass av Aspose.PDF. Var noga med att ange rätt sökväg till PDF-filen.

```csharp
Document doc = new Document(dataDir + "input.pdf");
```

## Steg 3: Ändra sidriktning
Nu ska vi gå igenom varje sida i dokumentet och ändra dess orientering. För varje sida ändrar vi måtten på medialådan (`MediaBox`) genom att byta bredd och höjd justerar vi koordinaterna för mediaboxen för att behålla sidans position. Slutligen ställer vi in sidrotationen till 90 grader.

```csharp
foreach(Page page in doc.Pages)
{
Aspose.Pdf.Rectangle r = page.MediaBox;
double newHeight = r.Width;
double newWidth = r.Height;
double newLLX = r.LLX;
double newLLY = r.LLY + (r.Height - newHeight);
page.MediaBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
page.CropBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
page. Rotate = Rotate. on90;
}
```

## Steg 4: Spara det ändrade PDF-dokumentet
 Slutligen kan du spara det ändrade PDF-dokumentet till en utdatafil med hjälp av`Save()` metod för`Document`klass. Var noga med att ange rätt sökväg och filnamn.

```csharp
dataDir = dataDir + "ChangeOrientation_out.pdf";
doc.Save(dataDir);
```

### Exempel på källkod för Ändra Orientering med Aspose.PDF för .NET 

```csharp

// Sökvägen till dokumentkatalogen.
string dataDir = "YOUR DOCUMENT DIRECTORY";
Document doc = new Document(dataDir + "input.pdf");
foreach (Page page in doc.Pages)
{
	Aspose.Pdf.Rectangle r = page.MediaBox;
	double newHeight = r.Width;
	double newWidth = r.Height;
	double newLLX = r.LLX;
	// Vi måste flytta sidan uppåt för att kompensera för ändrad sidstorlek
	// (sidans nedre kant är 0,0 och information placeras vanligtvis från
	// Överst på sidan. Det är därför vi flyttar lover edge övre på skillnad mellan
	// Gammal och ny höjd.
	double newLLY = r.LLY + (r.Height - newHeight);
	page.MediaBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
	// Ibland måste vi också ställa in CropBox (om den var inställd i originalfilen)
	page.CropBox = new Aspose.Pdf.Rectangle(newLLX, newLLY, newLLX + newWidth, newLLY + newHeight);
	// Ställa in sidans rotationsvinkel
	page.Rotate = Rotation.on90;
}
dataDir = dataDir + "ChangeOrientation_out.pdf";
// Spara utdatafil
doc.Save(dataDir);
System.Console.WriteLine("\nPage orientation changed successfully.\nFile saved at " + dataDir);

```

## Slutsats
I den här handledningen lärde vi oss hur man ändrar sidriktningen för ett PDF-dokument med Aspose.PDF för .NET. Genom att följa stegen ovan kan du enkelt implementera denna funktion i dina egna projekt. Utforska gärna Aspose.PDF-dokumentationen ytterligare för att upptäcka andra användbara funktioner för att arbeta med PDF-filer.