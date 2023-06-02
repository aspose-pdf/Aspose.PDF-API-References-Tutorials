---
title: Text till PDF
linktitle: Text till PDF
second_title: Aspose.PDF för .NET API Referens
description: Enkel och effektiv konvertering av textfiler till PDF med Aspose.PDF för .NET.
type: docs
weight: 300
url: /sv/net/document-conversion/text-to-pdf/
---

Denna handledning går igenom stegen för att konvertera en textfil till en PDF-fil med Aspose.PDF för .NET. Aspose.PDF erbjuder en enkel och effektiv lösning för att konvertera vanlig text till PDF samtidigt som textformatering och presentation bevaras. Följ stegen nedan för att utföra denna konvertering.

## Förutsättningar
Innan du börjar, se till att du uppfyller följande förutsättningar:

- Grundläggande kunskaper i programmeringsspråket C#.
- Aspose.PDF-bibliotek för .NET installerat på ditt system.
- En utvecklingsmiljö som Visual Studio.

## Steg 1: Läsa textfilen
 Det första steget är att läsa innehållet i textfilen med hjälp av`StreamReader` klass. Använd följande kod:

```csharp
// Sökväg till dokumentkatalogen.
string dataDir = "YOUR DOCUMENTS DIRECTORY";

// Läs textfilen
TextReader tr = new StreamReader(dataDir + "log.txt");
```

 Se till att byta ut`"YOUR DOCUMENTS DIRECTORY"` med den faktiska katalogen där din textfil finns.

## Steg 2: Skapa PDF-dokumentet
 Det andra steget är att skapa en`Document` objekt som kommer att representera det slutliga PDF-dokumentet. Använd följande kod:

```csharp
// Skapa ett dokumentobjekt
Document doc = new Document();
```

## Steg 3: Lägg till text i dokumentet
Det tredje steget är att lägga till den lästa texten på sidan i PDF-dokumentet. Använd följande kod:

```csharp
// Lägg till en ny sida i dokumentet
Page page = doc.Pages.Add();

//Skapa ett TextFragment-objekt och skicka den lästa texten som ett argument
TextFragment text = new TextFragment(tr.ReadToEnd());

// Lägg till textstycket på sidan
page.Paragraphs.Add(text);
```

## Steg 4: Spara PDF-filen
Spara slutligen den resulterande PDF-filen genom att ange önskad sökväg och filnamn. Använd följande kod:

```csharp
// Spara den resulterande PDF-filen
doc.Save(dataDir + "TexttoPDF_out.pdf");
```

Var noga med att ange önskad sökväg och filnamn för den resulterande PDF-filen.

### Exempel på källkod för text till PDF med Aspose.Words för .NET

```csharp
try
{
	
	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Läs källtextfilen
	TextReader tr = new StreamReader(dataDir + "log.txt");

	// Instantiera ett dokumentobjekt genom att anropa dess tomma konstruktor
	Document doc = new Document();

	// Lägg till en ny sida i Pages-samlingen av dokument
	Page page = doc.Pages.Add();

	// Skapa en instans av TextFragmet och skicka texten från läsarobjektet till dess konstruktor som argument
	TextFragment text = new TextFragment(tr.ReadToEnd());
	// Text.TextState.Font = FontRepository.FindFont("Arial Unicode MS");

	// Lägg till ett nytt textstycke i styckesamlingen och skicka TextFragment-objektet
	page.Paragraphs.Add(text);

	// Spara den resulterande PDF-filen
	doc.Save(dataDir + "TexttoPDF_out.pdf"); 
	
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Slutsats
den här handledningen lärde vi oss hur man konverterar en textfil till en PDF-fil med Aspose.PDF för .NET. Genom att följa stegen ovan kan du enkelt utföra denna konvertering. Använd den här metoden för att konvertera dina textfiler till PDF och njuta av flexibiliteten och kvaliteten hos Aspose.PDF.