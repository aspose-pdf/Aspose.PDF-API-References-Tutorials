---
title: Skapa dokument
linktitle: Skapa dokument
second_title: Aspose.PDF för .NET API-referens
description: Skapa enkelt ett dokument med alternativknappar med Aspose.PDF för .NET.
type: docs
weight: 40
url: /sv/net/programming-with-forms/create-doc/
---
I den här handledningen kommer vi att visa dig hur du skapar ett dokument med alternativknappar med Aspose.PDF för .NET. Vi kommer att förklara C#-källkoden steg för steg för att guida dig genom denna process.

##Steg 1: Förberedelser

Se först till att du har importerat de nödvändiga biblioteken och ställer in sökvägen till dokumentkatalogen:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 2: Skapa ett nytt dokument

Skapa ett nytt dokumentobjekt för att hålla PDF-dokumentet:

```csharp
Document doc = new Document();
```

## Steg 3: Lägg till en sida

Lägg till en ny sida i dokumentet:

```csharp
Page page = doc.Pages.Add();
```

## Steg 4: Lägg till ett alternativknappsfält

Skapa ett alternativknappsfält och ställ in dess position och storlek:

```csharp
RadioButtonField field = new RadioButtonField(page);
field.Rect = new Aspose.Pdf.Rectangle(40, 650, 100, 720);
field. PartialName = "NewField";
```

## Steg 5: Lägg till alternativ för alternativknappar

Lägg till önskade alternativ i alternativknappsfältet. Du kan ställa in koordinaterna och storleken för varje alternativ efter behov:

```csharp
RadioButtonOptionField opt1 = new RadioButtonOptionField();
opt1.Rect = new Aspose.Pdf.Rectangle(40, 650, 60, 670);
opt1.OptionName = "Item1";
opt1.Border = new Border(opt1);
opt1.Border.Width = 1;
opt1.Characteristics.Border = System.Drawing.Color.Black;

RadioButtonOptionField opt2 = new RadioButtonOptionField();
opt2.Rect = new Aspose.Pdf.Rectangle(60, 670, 80, 690);
opt2.OptionName = "Item2";
opt2.Border = new Border(opt2);
opt2.Border.Width = 1;
opt2.Characteristics.Border = System.Drawing.Color.Black;

RadioButtonOptionField opt3 = new RadioButtonOptionField();
opt3.Rect = new Aspose.Pdf.Rectangle(80, 690, 100, 710);
opt3.OptionName = "Item3";
opt3.Border = new Border(opt3);
opt3.Border.Width = 1;
opt3.Characteristics.Border = System.Drawing.Color.Black;

field. Add(opt1);
field. Add(opt2);
field. Add(opt3);
```

## Steg 6: Lägg till alternativknappsfältet i formuläret

Lägg till alternativknappsfältet i samlingen Document Form Fields:

```csharp
doc.Form.Add(field);
```

## Steg 7: Spara dokumentet

Spara PDF-dokumentet:

```csharp
dataDir = dataDir + "CreateDoc_out.pdf";
doc.Save(dataDir);
```

### Exempel på källkod för Skapa dokument med Aspose.PDF för .NET 
```csharp
try
{
	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Skapa ett nytt dokument
	Document doc = new Document();
	Page page = doc.Pages.Add();
	// Lägg till alternativknappsfält
	RadioButtonField field = new RadioButtonField(page);
	field.Rect = new Aspose.Pdf.Rectangle(40, 650, 100, 720);
	field.PartialName = "NewField";
	// Lägg till alternativ för alternativknappar. Observera att dessa alternativ finns
	// Varken horisontellt eller vertikalt.
	// Du kan försöka ställa in valfri koordinater (och jämn storlek) för dem.
	RadioButtonOptionField opt1 = new RadioButtonOptionField();
	opt1.Rect = new Aspose.Pdf.Rectangle(40, 650, 60, 670);
	opt1.OptionName = "Item1";
	opt1.Border = new Border(opt1);
	opt1.Border.Width = 1;
	opt1.Characteristics.Border = System.Drawing.Color.Black;
	RadioButtonOptionField opt2 = new RadioButtonOptionField();
	opt2.Rect = new Aspose.Pdf.Rectangle(60, 670, 80, 690);
	opt2.OptionName = "Item2";
	opt2.Border = new Border(opt2);
	opt2.Border.Width = 1;
	opt2.Characteristics.Border = System.Drawing.Color.Black;
	RadioButtonOptionField opt3 = new RadioButtonOptionField();
	opt3.Rect = new Aspose.Pdf.Rectangle(80, 690, 100, 710);
	opt3.OptionName = "Item3";
	opt3.Border = new Border(opt3);
	opt3.Border.Width = 1;
	opt3.Characteristics.Border = System.Drawing.Color.Black;
	field.Add(opt1);
	field.Add(opt2);
	field.Add(opt3);
	doc.Form.Add(field);
	dataDir = dataDir + "CreateDoc_out.pdf";
	// Spara PDF-dokumentet
	doc.Save(dataDir);
	Console.WriteLine("\nNew doc with 3 items radio button created successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Slutsats

den här handledningen lärde vi oss hur man skapar ett dokument med alternativknappar med Aspose.PDF för .NET. Genom att följa dessa steg kan du enkelt lägga till alternativknappar till dina PDF-dokument med Aspose.PDF.

### FAQ's

#### F: Kan jag anpassa utseendet på alternativknapparna i dokumentet med Aspose.PDF för .NET?

S: Ja, du kan anpassa utseendet på alternativknapparna i dokumentet med Aspose.PDF för .NET. Du kan ställa in egenskaper som storlek, färg, kantstil med mera för att anpassa utseendet på alternativknapparna.

#### F: Hur kan jag lägga till alternativknappsgrupper med ömsesidigt uteslutande alternativ?

S: För att skapa ömsesidigt uteslutande alternativ kan du lägga till flera alternativknappsfält med samma namn. Detta säkerställer att när ett alternativ väljs, kommer de andra alternativen med samma namn att automatiskt avmarkeras.

#### F: Är det möjligt att ställa in ett standardval för alternativknapparna?

S: Ja, du kan ställa in ett standardval för alternativknapparna med Aspose.PDF för .NET. Du kan använda`Selected` egendom av`RadioButtonOptionField` objekt för att markera ett alternativ som valt som standard.

#### F: Kan jag lägga till händelsehanterare till alternativknapparna?

 S: Ja, du kan lägga till händelsehanterare till alternativknapparna med Aspose.PDF för .NET. Du kan koppla JavaScript-åtgärder, som t.ex`OnValueChanged`, till alternativknapparna för att utföra specifika åtgärder när användaren väljer ett alternativ.

#### F: Hur kan jag hämta det valda alternativet från alternativknappsgruppen efter att användaren gjort ett val?

 S: Du kan hämta det valda alternativet från radioknappsgruppen med Aspose.PDF för .NET. När användaren har gjort ett val kan du komma åt`Selected` egendom av`RadioButtonOptionField` objekt för att kontrollera vilket alternativ som är valt.