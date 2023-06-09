---
title: Horisontellt Och Vertikalt Radioknappar
linktitle: Horisontellt Och Vertikalt Radioknappar
second_title: Aspose.PDF för .NET API Referens
description: Skapa enkelt horisontella och vertikala alternativknappar i dina PDF-dokument med Aspose.PDF för .NET.
type: docs
weight: 180
url: /sv/net/programming-with-forms/horizontally-and-vertically-radio-buttons/
---

den här handledningen kommer vi att visa dig hur du skapar horisontellt och vertikalt arrangerade radioknappar i ett PDF-dokument med Aspose.PDF för .NET. Vi kommer att förklara C#-källkoden steg för steg för att guida dig genom denna process.

## Steg 1: Förberedelser

Se till att du har importerat de nödvändiga biblioteken och ange sökvägen till din dokumentkatalog:

```csharp
string dataDir = "YOUR DOCUMENTS DIRECTORY";
```

## Steg 2: Ladda dokumentet

Ladda det befintliga PDF-dokumentet:

```csharp
FormEditor formEditor = new FormEditor();
formEditor.BindPdf(dataDir + "input.pdf");
```

## Steg 3: Anpassa alternativ för alternativknappar

Anpassa alternativknappsalternativ genom att ställa in följande egenskaper:

```csharp
formEditor. RadioGap = 4; // Avstånd mellan två alternativ för alternativknappar
formEditor. RadioHoriz = true; // Horisontell layout av radioknappar
formEditor.RadioButtonItemSize = 20; // Storlek på radioknappar
formEditor.Facade.BorderWidth = 1; // Bredd på radioknappskant
formEditor.Facade.BorderColor = System.Drawing.Color.Black; // Radioknapp kantfärg
```

## Steg 4: Lägg till horisontella radioknappar

Lägg till radioknappar ordnade horisontellt genom att ange alternativen och positionen för fältet:

```csharp
formEditor.Items = new string[] { "First", "Second", "Third" };
formEditor.AddField(FieldType.Radio, "NewField1", 1, 40, 600, 120, 620);
```

## Steg 5: Lägg till vertikala radioknappar

Lägg till alternativknappar anordnade vertikalt genom att ange alternativen och positionen för fältet:

```csharp
formEditor. RadioHoriz = false; // Vertikal layout av radioknappar
formEditor.Items = new string[] { "First", "Second", "Third" };
formEditor.AddField(FieldType.Radio, "NewField2", 1, 40, 500, 60, 550);
```

## Steg 6: Spara dokumentet

Spara det ändrade PDF-dokumentet:

```csharp
dataDir = dataDir + "HorizontallyAndVerticallyRadioButtons_out.pdf";
formEditor.Save(dataDir);
```

### Exempel på källkod för radioknappar horisontellt och vertikalt med Aspose.PDF för .NET 
```csharp
try
{
	// Sökvägen till dokumentkatalogen.
	string dataDir = "YOUR DOCUMENT DIRECTORY";
	// Ladda det tidigare sparade dokumentet
	FormEditor formEditor = new FormEditor();
	formEditor.BindPdf(dataDir + "input.pdf");
	// RadioGap är avståndet mellan två alternativ för alternativknappar.
	formEditor.RadioGap = 4;
	// Lägg till horisontell alternativknapp
	formEditor.RadioHoriz = true;
	// RadioButtonItemSize om storleken på alternativknappsobjektet.
	formEditor.RadioButtonItemSize = 20;
	formEditor.Facade.BorderWidth = 1;
	formEditor.Facade.BorderColor = System.Drawing.Color.Black;
	formEditor.Items = new string[] { "First", "Second", "Third" };
	formEditor.AddField(FieldType.Radio, "NewField1", 1, 40, 600, 120, 620);
	// Lägg till annan alternativknapp som är placerad vertikalt
	formEditor.RadioHoriz = false;
	formEditor.Items = new string[] { "First", "Second", "Third" };
	formEditor.AddField(FieldType.Radio, "NewField2", 1, 40, 500, 60, 550);
	dataDir = dataDir + "HorizontallyAndVerticallyRadioButtons_out.pdf";
	// Spara PDF-dokumentet
	formEditor.Save(dataDir);
	Console.WriteLine("\nHorizontally and vertically laid out radio buttons successfully.\nFile saved at " + dataDir);
}
catch (Exception ex)
{
	Console.WriteLine(ex.Message);
}
```

## Slutsats

I den här handledningen lärde vi oss hur man skapar horisontellt och vertikalt arrangerade radioknappar i ett PDF-dokument med Aspose.PDF för .NET. Genom att följa dessa steg kan du enkelt anpassa layouten för alternativknappar och lägga till dem i dina PDF-dokument med Aspose.PDF.