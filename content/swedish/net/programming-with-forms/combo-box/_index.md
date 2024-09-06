---
title: Combo Box
linktitle: Combo Box
second_title: Aspose.PDF för .NET API-referens
description: Skapa enkelt kombinationsruta i dina PDF-dokument med Aspose.PDF för .NET.
type: docs
weight: 30
url: /sv/net/programming-with-forms/combo-box/
---
I den här handledningen kommer vi att visa dig hur du skapar en kombinationsrutalista med Aspose.PDF för .NET. Vi kommer att förklara C#-källkoden steg för steg för att guida dig genom denna process.

## Steg 1: Förberedelser

Se först till att du har importerat de nödvändiga biblioteken och ställer in sökvägen till dokumentkatalogen:

```csharp
string dataDir = "YOUR DOCUMENT DIRECTORY";
```

## Steg 2: Skapa ett dokumentobjekt

Skapa ett dokumentobjekt för att hålla PDF-formuläret:

```csharp
Document doc = new Document();
```

## Steg 3: Lägg till en sida

Lägg till en sida i dokumentet:

```csharp
doc.Pages.Add();
```

## Steg 4: Instantiera ett ComboBoxField-objekt

Instantiera ett ComboBoxField-objekt med önskade dimensioner:

```csharp
ComboBoxField combo = new ComboBoxField(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 600, 150, 616));
```

## Steg 5: Lägg till alternativ i rullgardinsmenyn

Lägg till önskade alternativ i rullgardinsmenyn:

```csharp
combo.AddOption("Red");
combo.AddOption("Yellow");
combo.AddOption("Green");
combo.AddOption("Blue");
```

## Steg 6: Lägg till kombinationsrutan i formuläret

Lägg till ComboBoxField-objektet i samlingen Document Form Fields:

```csharp
doc.Form.Add(combo);
```

## Steg 7: Spara dokumentet

Spara PDF-dokumentet:

```csharp
dataDir = dataDir + "ComboBox_out.pdf";
doc.Save(dataDir);
```

### Exempel på källkod för Combo Box med Aspose.PDF för .NET 
```csharp
try
{
	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Skapa dokumentobjekt
	Document doc = new Document();
	// Lägg till sida till dokumentobjekt
	doc.Pages.Add();
	// Instantiera ComboBox Field-objekt
	ComboBoxField combo = new ComboBoxField(doc.Pages[1], new Aspose.Pdf.Rectangle(100, 600, 150, 616));
	// Lägg till alternativ till ComboBox
	combo.AddOption("Red");
	combo.AddOption("Yellow");
	combo.AddOption("Green");
	combo.AddOption("Blue");
	// Lägg till kombinationsrutaobjekt till formulärfältsamling av dokumentobjekt
	doc.Form.Add(combo);
	dataDir = dataDir + "ComboBox_out.pdf";
	// Spara PDF-dokumentet
	doc.Save(dataDir);
	Console.WriteLine("\nCombobox field added successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Slutsats

den här handledningen lärde vi oss hur man skapar en kombinationsrutalista med Aspose.PDF för .NET. Genom att följa dessa steg kan du enkelt lägga till en kombinationsrutalista till dina PDF-dokument med Aspose.PDF.

### FAQ's

#### F: Kan jag anpassa utseendet på kombinationsrutelistan med Aspose.PDF för .NET?

S: Ja, du kan anpassa utseendet på kombinationsrutelistan med Aspose.PDF för .NET. Du kan ställa in egenskaper som teckenstorlek, färg, bakgrundsfärg, kantstil med mera för att matcha ditt önskade utseende och känsla.

#### F: Kan jag ställa in standardvalda alternativ i kombinationsrutan?

 S: Ja, du kan ställa in standardvalda alternativ i kombinationsrutan med Aspose.PDF för .NET. Du kan använda`Selected` egendom av`ComboBoxField` objekt för att markera ett eller flera alternativ som valda som standard.

#### F: Hur kan jag hämta det valda värdet från kombinationsrutan efter att användaren gjort ett val?

 S: Du kan hämta det valda värdet från kombinationsrutan med Aspose.PDF för .NET. När användaren har gjort ett val kan du komma åt`Value` egendom av`ComboBoxField`objekt för att få det valda värdet.

#### F: Är det möjligt att lägga till händelsehanterare eller åtgärder till kombinationsrutelistan?

 S: Ja, Aspose.PDF för .NET låter dig lägga till händelsehanterare eller åtgärder till listan med kombinationsrutor. Du kan koppla JavaScript-åtgärder, som t.ex`OnValueChanged`, till kombinationsrutan för att utföra specifika åtgärder när användaren väljer ett alternativ.

#### F: Kan jag lägga till verktygstips eller beskrivningar till alternativen i kombinationsrutan?

 S: Ja, du kan lägga till verktygstips eller beskrivningar till alternativen i kombinationsrutan med Aspose.PDF för .NET. Du kan ställa in`AlternateName` egenskapen för varje alternativ för att tillhandahålla ett verktygstips eller en beskrivning som kommer att visas när användaren håller muspekaren över alternativet.