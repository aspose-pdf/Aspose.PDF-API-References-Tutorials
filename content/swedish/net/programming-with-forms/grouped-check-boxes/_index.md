---
title: Grupperade kryssrutor i PDF-dokument
linktitle: Grupperade kryssrutor i PDF-dokument
second_title: Aspose.PDF för .NET API-referens
description: Skapa enkelt grupperade kryssrutor i PDF-dokument med Aspose.PDF för .NET.
type: docs
weight: 170
url: /sv/net/programming-with-forms/grouped-check-boxes/
---
I den här handledningen kommer vi att visa dig hur du skapar grupperade kryssrutor i ett PDF-dokument med Aspose.PDF för .NET. Vi kommer att förklara C#-källkoden steg för steg för att guida dig genom denna process.

## Steg 1: Förberedelser

Se till att du har importerat de nödvändiga biblioteken och ange sökvägen till din dokumentkatalog:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Steg 2: Instantiera ett dokumentobjekt

Instantiera ett dokumentobjekt:

```csharp
Document pdfDocument = new Document();
```

## Steg 3: Lägg till sida till PDF-dokument

Lägg till en sida i PDF-dokumentet:

```csharp
Page page = pdfDocument.Pages.Add();
```

## Steg 4: Instantiera ett RadioButtonField-objekt

Instantiera ett RadioButtonField-objekt med sidnumret som argument:

```csharp
RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
```

## Steg 5: Lägg till alternativ för alternativknappar

Lägg till alternativknappsalternativ med RadioButtonOptionField-objektet och ange deras position med hjälp av Rectangle-objektet:

```csharp
RadioButtonOptionField opt1 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(0, 0, 20, 20));
RadioButtonOptionField opt2 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(100, 0, 120, 20));
opt1.OptionName = "Test1";
opt2.OptionName = "Test2";
radio.Add(opt1);
radio.Add(opt2);
```

## Steg 6: Anpassa alternativ för alternativknappar

Anpassa alternativen för alternativknappar genom att ställa in deras stil, ram och utseende:

```csharp
opt1.Style = BoxStyle.Square;
opt2.Style = BoxStyle.Square;
opt1.Border = new Border(opt1);
opt1.Border.Style = BorderStyle.Solid;
opt1.Border.Width = 1;
opt2.Border = new Border(opt2);
opt2.Border.Width = 1;
opt2.Border.Style = BorderStyle.Solid;
```

## Steg 7: Lägg till alternativknapparna i formuläret

Lägg till alternativknapparna till dokumentformulärobjektet:

```csharp
pdfDocument.Form.Add(radio);
```

## Steg 8: Spara dokumentet

Spara PDF-dokumentet:

```csharp
dataDir = dataDir + "GroupedCheckBoxes_out.pdf";
pdfDocument.Save(dataDir);
```

### Exempel på källkod för grupperade kryssrutor med Aspose.PDF för .NET 
```csharp
try
{
	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Instantiera dokumentobjekt
	Document pdfDocument = new Document();
	// Lägg till en sida i PDF-filen
	Page page = pdfDocument.Pages.Add();
	// Instatera RadioButtonField-objekt med sidnummer som argument
	RadioButtonField radio = new RadioButtonField(pdfDocument.Pages[1]);
	// Lägg till första alternativknappsalternativet och ange även dess ursprung med Rectangle-objektet
	RadioButtonOptionField opt1 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(0, 0, 20, 20));
	RadioButtonOptionField opt2 = new RadioButtonOptionField(page, new Aspose.Pdf.Rectangle(100, 0, 120, 20));
	opt1.OptionName = "Test1";
	opt2.OptionName = "Test2";
	radio.Add(opt1);
	radio.Add(opt2);
	opt1.Style = BoxStyle.Square;
	opt2.Style = BoxStyle.Square;
	opt1.Style = BoxStyle.Cross;
	opt2.Style = BoxStyle.Cross;
	opt1.Border = new Border(opt1);
	opt1.Border.Style = BorderStyle.Solid;
	opt1.Border.Width = 1;
	opt1.Characteristics.Border = System.Drawing.Color.Black;
	opt2.Border = new Border(opt2);
	opt2.Border.Width = 1;
	opt2.Border.Style = BorderStyle.Solid;
	opt2.Characteristics.Border = System.Drawing.Color.Black;
	// Lägg till alternativknapp för att bilda objekt av dokumentobjekt
	pdfDocument.Form.Add(radio);
	dataDir = dataDir + "GroupedCheckBoxes_out.pdf";
	// Spara PDF-dokumentet
	pdfDocument.Save(dataDir);
	Console.WriteLine("\nGrouped checkboxes added successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Slutsats

I den här handledningen lärde vi oss hur man skapar grupperade kryssrutor i ett PDF-dokument med Aspose.PDF för .NET. Genom att följa dessa steg kan du enkelt lägga till anpassade alternativ för alternativknappar och bunta dem i dina PDF-dokument med Aspose.PDF.

### FAQ's

#### F: Vad är grupperade kryssrutor i ett PDF-dokument?

S: Grupperade kryssrutor i ett PDF-dokument hänvisar till en uppsättning alternativknappar som är grupperade. Radioknappar tillåter användare att bara välja ett alternativ från en grupp av ömsesidigt uteslutande val. När en alternativknapp väljs avmarkeras de andra i samma grupp automatiskt. Detta grupperingsbeteende är användbart när du vill ge användarna flera alternativ men begränsa deras val till endast ett val.

#### F: Kan jag anpassa utseendet på grupperade kryssrutor i Aspose.PDF för .NET?

S: Ja, du kan anpassa utseendet på grupperade kryssrutor i Aspose.PDF för .NET. API:et tillhandahåller olika alternativ för att ställa in stil, ram och utseende för alternativknappsalternativ. Du kan definiera positionen för varje alternativ, välja mellan olika boxstilar (t.ex. kvadrat, cirkel, kors) och justera gränsegenskaperna för att uppnå önskad visuell representation.

#### F: Hur lägger jag till grupperade kryssrutor på en specifik sida i ett PDF-dokument?

S: För att lägga till grupperade kryssrutor till en specifik sida i ett PDF-dokument måste du instansiera en`RadioButtonField` objekt med önskat sidnummer som argument. Skapa sedan`RadioButtonOptionField` objekt som representerar varje alternativknapp och ange deras position med hjälp av`Rectangle` objekt. Lägg slutligen till dessa alternativ till`RadioButtonField` och anpassa deras utseende efter behov innan du lägger till`RadioButtonField` till dokumentformuläret.

#### F: Kan jag lägga till flera grupper av kryssrutor i ett enda PDF-dokument?

 S: Ja, du kan lägga till flera grupper av kryssrutor i ett enda PDF-dokument. Varje grupp ska ha en unik`RadioButtonField` objekt och`RadioButtonOptionField` objekt inom varje grupp ska dela samma sida och unika namn för sina alternativ. Detta säkerställer att radioknapparna inom varje grupp fungerar korrekt och att valen utesluter varandra.

#### F: Stöds grupperade kryssrutor i alla PDF-läsare och applikationer?

S: Ja, grupperade kryssrutor stöds i alla standardkompatibla PDF-läsare och applikationer. PDF-specifikationen definierar alternativknappar och deras grupperingsbeteende, vilket gör dem allmänt igenkända i PDF-formatet. Det är dock viktigt att testa funktionaliteten i olika PDF-läsare för att säkerställa konsekvent beteende på olika plattformar.