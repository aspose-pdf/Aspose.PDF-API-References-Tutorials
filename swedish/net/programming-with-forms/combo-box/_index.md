---
title: Kombinationsrutan
linktitle: Kombinationsrutan
second_title: Aspose.PDF för .NET API Referens
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

### Exempel på källkod för Combo Box med Aspose.Words för .NET 
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