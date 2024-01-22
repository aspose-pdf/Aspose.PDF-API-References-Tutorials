---
title: Horisontellt Och Vertikalt Radioknappar
linktitle: Horisontellt Och Vertikalt Radioknappar
second_title: Aspose.PDF för .NET API-referens
description: Skapa enkelt horisontella och vertikala alternativknappar i dina PDF-dokument med Aspose.PDF för .NET.
type: docs
weight: 180
url: /sv/net/programming-with-forms/horizontally-and-vertically-radio-buttons/
---
I den här handledningen kommer vi att visa dig hur du skapar horisontellt och vertikalt arrangerade radioknappar i ett PDF-dokument med Aspose.PDF för .NET. Vi kommer att förklara C#-källkoden steg för steg för att guida dig genom denna process.

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
formEditor. RadioHoriz = true; //Horisontell layout av radioknappar
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

den här handledningen lärde vi oss hur man skapar horisontellt och vertikalt arrangerade radioknappar i ett PDF-dokument med Aspose.PDF för .NET. Genom att följa dessa steg kan du enkelt anpassa layouten för alternativknappar och lägga till dem i dina PDF-dokument med Aspose.PDF.

### FAQ's

#### F: Vad är horisontellt och vertikalt arrangerade alternativknappar i ett PDF-dokument?

S: Horisontellt och vertikalt arrangerade alternativknappar i ett PDF-dokument hänvisar till layoutorienteringen för alternativknappsalternativ. Horisontell layout placerar alternativknapparna sida vid sida, så att användarna kan välja från vänster till höger. Vertikal layout, å andra sidan, staplar alternativen för alternativknappar ovanpå varandra, vilket gör det möjligt för användare att göra ett urval uppifrån och ner.

#### F: Hur anpassar jag utseendet på alternativknappsalternativ i Aspose.PDF för .NET?

S: Du kan anpassa utseendet på alternativknapparna i Aspose.PDF för .NET genom att justera flera egenskaper. API ger alternativ för att ställa in avståndet mellan två alternativknappsalternativ (`RadioGap`), layoutens orientering (`RadioHoriz`), storleken på alternativknappsobjekt (`RadioButtonItemSize`), kantbredden och färgen på alternativknappar med mera.

#### F: Kan jag lägga till både horisontella och vertikala alternativknappar i samma PDF-dokument?

S: Ja, du kan lägga till både horisontella och vertikala alternativknappar till samma PDF-dokument med Aspose.PDF för .NET. Exempelkällkoden som tillhandahålls i handledningen visar hur man först lägger till radioknappar anordnade horisontellt och sedan lägger till ytterligare en uppsättning alternativknappar arrangerade vertikalt i samma PDF-dokument.

#### F: Kan jag ställa in olika alternativ för alternativknappar för varje grupp av alternativknappar?

 S: Ja, du kan ställa in olika alternativ för alternativknappar för varje grupp av alternativknappar. Varje grupp ska ha en unik`RadioButtonField` objekt och`RadioButtonOptionField` objekt inom varje grupp ska dela samma sida och unika namn för sina alternativ. Detta säkerställer att radioknapparna inom varje grupp fungerar korrekt och att valen utesluter varandra.

#### F: Stöds layout- och utseendeinställningarna för alternativknappar i alla PDF-läsare och applikationer?

S: Ja, layout- och utseendeinställningarna för alternativknappar stöds i alla standardkompatibla PDF-läsare och applikationer. PDF-specifikationen definierar alternativknappar och deras olika attribut, vilket gör dem allmänt igenkända i PDF-formatet. Det är dock viktigt att testa utseendet och beteendet hos alternativknappar i olika PDF-visare för att säkerställa konsekvent rendering på olika plattformar.